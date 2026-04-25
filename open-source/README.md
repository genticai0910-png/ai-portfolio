# Open Source

Production utilities extracted from a live AI automation stack. Each module is a standalone component — no framework required, copy what you need.

---

## Modules

| Module | Description |
|--------|-------------|
| **[LLM Fallback Router](llm-fallback-router/)** | Multi-provider LLM routing with automatic failover, circuit breakers, and latency tracking. Handles both OpenAI-compatible and Anthropic APIs. Single dependency: `httpx`. |
| **[Conversation State Tracker](conversation-state-tracker/)** | Tracks question coverage, detects caller evasion, reads emotional state, and generates per-turn inline directives for AI-guided conversations. Zero dependencies. |

---

## Design Philosophy

These modules were built to solve production problems, not to be frameworks. They are:

- **Dependency-light** — use what the module needs, nothing else
- **Copy-paste friendly** — each module is a single file you can drop into any project
- **Production-tested** — running in live voice AI and lead qualification systems

---

[← Back to Portfolio](../README.md)
