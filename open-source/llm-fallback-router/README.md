# LLM Fallback Router

Multi-provider LLM routing with automatic failover, latency tracking, and cost-aware selection.

## Why This Exists

Single-provider LLM calls are a single point of failure. Rate limits, outages, and cost spikes happen constantly. This router wraps multiple providers in a priority chain with automatic failover.

## Usage

```python
from llm_router import LLMRouter

router = LLMRouter([
    {"provider": "local", "base_url": "http://localhost:LOCAL_PORT/v1", "model": "qwen2.5:1.5b", "priority": 1},
    {"provider": "openai_compat", "base_url": "http://localhost:LOCAL_PORT/v1", "model": "qwen2.5:1.5b", "priority": 2},
    {"provider": "xai", "api_key": "...", "model": "grok-4-fast", "priority": 3},
    {"provider": "google", "api_key": "...", "model": "gemini-flash-lite", "priority": 4},
    {"provider": "anthropic", "api_key": "...", "model": "claude-haiku-4.5", "priority": 5},
])

response = router.complete(
    messages=[{"role": "user", "content": "Classify this intent..."}],
    max_tokens=200,
    timeout=5.0
)

print(response.text)
print(response.provider_used)      # Which provider actually served it
print(response.latency_ms)         # End-to-end latency
print(response.fallback_count)     # How many providers were tried
```

## Install

```bash
pip install httpx  # Only dependency
```

---

## `llm_router.py`

```python
"""
LLM Fallback Router
Multi-provider LLM routing with automatic failover and latency tracking.

MIT License
"""

import time
import json
import logging
from dataclasses import dataclass, field
from typing import Optional

import httpx

logger = logging.getLogger(__name__)


@dataclass
class LLMResponse:
    text: str
    provider_used: str
    model_used: str
    latency_ms: float
    fallback_count: int
    raw: dict = field(default_factory=dict)


@dataclass
class ProviderConfig:
    name: str
    base_url: str
    model: str
    priority: int
    api_key: Optional[str] = None
    headers: dict = field(default_factory=dict)
    consecutive_failures: int = 0
    cooldown_until: float = 0.0
    avg_latency_ms: float = 0.0
    total_calls: int = 0

    # Circuit breaker settings
    max_failures: int = 3
    cooldown_seconds: float = 60.0

    @property
    def is_available(self) -> bool:
        if self.consecutive_failures >= self.max_failures:
            if time.time() < self.cooldown_until:
                return False
            # Cooldown expired, allow retry
            self.consecutive_failures = 0
        return True

    def record_success(self, latency_ms: float):
        self.consecutive_failures = 0
        self.total_calls += 1
        # Exponential moving average
        alpha = 0.3
        if self.avg_latency_ms == 0:
            self.avg_latency_ms = latency_ms
        else:
            self.avg_latency_ms = alpha * latency_ms + (1 - alpha) * self.avg_latency_ms

    def record_failure(self):
        self.consecutive_failures += 1
        if self.consecutive_failures >= self.max_failures:
            self.cooldown_until = time.time() + self.cooldown_seconds
            logger.warning(
                f"Provider {self.name} circuit breaker OPEN "
                f"(cooldown {self.cooldown_seconds}s)"
            )


class LLMRouter:
    def __init__(self, providers: list[dict], default_timeout: float = 10.0):
        self.providers = []
        self.default_timeout = default_timeout

        for p in sorted(providers, key=lambda x: x.get("priority", 99)):
            config = ProviderConfig(
                name=p.get("provider", p.get("name", "unknown")),
                base_url=p["base_url"].rstrip("/"),
                model=p["model"],
                priority=p.get("priority", 99),
                api_key=p.get("api_key"),
                headers=p.get("headers", {}),
                max_failures=p.get("max_failures", 3),
                cooldown_seconds=p.get("cooldown_seconds", 60.0),
            )

            # Build auth headers
            if config.api_key:
                if "anthropic" in config.name.lower():
                    config.headers["x-api-key"] = config.api_key
                    config.headers["anthropic-version"] = "2023-06-01"
                else:
                    config.headers["Authorization"] = f"Bearer {config.api_key}"

            config.headers["Content-Type"] = "application/json"
            self.providers.append(config)

    def complete(
        self,
        messages: list[dict],
        max_tokens: int = 500,
        temperature: float = 0.0,
        timeout: Optional[float] = None,
        required_provider: Optional[str] = None,
    ) -> LLMResponse:
        """
        Route a completion request through the provider chain.
        Falls through to next provider on any failure.
        """
        timeout = timeout or self.default_timeout
        fallback_count = 0
        errors = []

        candidates = self.providers
        if required_provider:
            candidates = [p for p in self.providers if p.name == required_provider]
            if not candidates:
                raise ValueError(f"Provider '{required_provider}' not found")

        for provider in candidates:
            if not provider.is_available:
                logger.debug(f"Skipping {provider.name} (circuit breaker open)")
                fallback_count += 1
                continue

            try:
                start = time.perf_counter()
                response = self._call_provider(
                    provider, messages, max_tokens, temperature, timeout
                )
                latency_ms = (time.perf_counter() - start) * 1000

                provider.record_success(latency_ms)

                return LLMResponse(
                    text=response["text"],
                    provider_used=provider.name,
                    model_used=provider.model,
                    latency_ms=round(latency_ms, 1),
                    fallback_count=fallback_count,
                    raw=response.get("raw", {}),
                )

            except Exception as e:
                provider.record_failure()
                fallback_count += 1
                errors.append(f"{provider.name}: {type(e).__name__}: {e}")
                logger.warning(f"Provider {provider.name} failed: {e}")
                continue

        raise RuntimeError(
            f"All providers exhausted. Errors:\n" + "\n".join(errors)
        )

    def _call_provider(
        self,
        provider: ProviderConfig,
        messages: list[dict],
        max_tokens: int,
        temperature: float,
        timeout: float,
    ) -> dict:
        """Make the actual API call. Handles OpenAI and Anthropic formats."""

        is_anthropic = "anthropic" in provider.name.lower()

        if is_anthropic:
            # Anthropic Messages API format
            body = {
                "model": provider.model,
                "max_tokens": max_tokens,
                "temperature": temperature,
                "messages": messages,
            }
            endpoint = f"{provider.base_url}/v1/messages"
        else:
            # OpenAI-compatible format (works for local, xAI, Google, etc.)
            body = {
                "model": provider.model,
                "max_tokens": max_tokens,
                "temperature": temperature,
                "messages": messages,
            }
            endpoint = f"{provider.base_url}/chat/completions"

        with httpx.Client(timeout=timeout) as client:
            resp = client.post(endpoint, headers=provider.headers, json=body)
            resp.raise_for_status()
            data = resp.json()

        # Extract text from response
        if is_anthropic:
            text = data.get("content", [{}])[0].get("text", "")
        else:
            text = data.get("choices", [{}])[0].get("message", {}).get("content", "")

        return {"text": text, "raw": data}

    def get_stats(self) -> list[dict]:
        """Return provider health stats."""
        return [
            {
                "name": p.name,
                "model": p.model,
                "priority": p.priority,
                "available": p.is_available,
                "avg_latency_ms": round(p.avg_latency_ms, 1),
                "total_calls": p.total_calls,
                "consecutive_failures": p.consecutive_failures,
            }
            for p in self.providers
        ]


# --- Quick test ---
if __name__ == "__main__":
    # Example: local-only setup
    router = LLMRouter([
        {
            "provider": "mlx_local",
            "base_url": "http://localhost:LOCAL_PORT/v1",
            "model": "qwen2.5:1.5b",
            "priority": 1,
        },
        {
            "provider": "ollama_local",
            "base_url": "http://localhost:LOCAL_PORT/v1",
            "model": "qwen2.5:1.5b",
            "priority": 2,
        },
    ])

    try:
        result = router.complete(
            messages=[{"role": "user", "content": "Say hello in one word."}],
            max_tokens=10,
        )
        print(f"Response: {result.text}")
        print(f"Provider: {result.provider_used}")
        print(f"Latency: {result.latency_ms}ms")
    except RuntimeError as e:
        print(f"All providers failed: {e}")

    print("\nProvider stats:", json.dumps(router.get_stats(), indent=2))
```

## Features

- **Priority-ordered routing** — tries providers in order, falls to next on failure
- **Circuit breaker** — after N consecutive failures, provider enters cooldown
- **Latency tracking** — exponential moving average per provider
- **Multi-format** — handles both OpenAI-compatible and Anthropic APIs
- **Zero lock-in** — works with any OpenAI-compatible endpoint (Ollama, vLLM, LiteLLM, MLX, etc.)

## Production Notes

- Set `timeout` per your latency budget (voice AI needs <2s, batch can tolerate 30s+)
- Use `required_provider` to pin specific requests (e.g., fine-tuned model for classification)
- Monitor `get_stats()` to detect degrading providers before they circuit-break
- The circuit breaker cooldown prevents hammering a failing provider

---

[← Back to Open Source Index](../README.md)
