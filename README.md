# Gabe | AI Infrastructure & Automation Portfolio

> **Building production-grade AI systems that generate revenue at zero marginal cost.**

I design, deploy, and operate end-to-end AI infrastructure from fine-tuned local models to multi-platform voice agents to full lead-processing pipelines. Everything below is **live in production**, processing real leads and serving real customers.

---

## What I Build

| Domain | Stack | Status |
|--------|-------|--------|
| **AI Agent Orchestration** | Arachne Swarm dashboard, Markspace coordination protocol, tiered autonomy | Production |
| **Voice AI** | Bland AI, Twilio, Custom TTS (Piper/Edge TTS), intent classification | Production |
| **Custom Model Training** | Qwen 2.5 1.5B + LoRA, MLX inference, Ollama fallback, synthetic data pipelines | Production |
| **Workflow Automation** | n8n (50+ workflows), webhooks, PostgreSQL, Redis | Production |
| **Cost-Optimized LLM Routing** | Multi-provider fallback chains, local-first inference, complexity-based routing | Production |
| **Lead Intelligence** | Proprietary scoring (iRELOP), RAG pipelines, Qdrant vector search | Production |
| **Web Intelligence** | Scrapling, Firecrawl, Crawl4AI, anti-bot bypass, structured extraction | Production |
| **Self-Hosted Infrastructure** | local compute node + cloud Docker (control plane), reverse proxy with SSL | Production |

---

## Featured Projects

### [Arachne Swarm: AI Agent Orchestration Dashboard](projects/arachne-swarm.md)
Full-stack agent orchestration platform. Real-time spider web visualization, Kanban pipeline management, budget controls, multi-tenant isolation. Next.js + WebSocket + PostgreSQL. **Live at [swarm.gentic.pro](https://swarm.gentic.pro)**

### [Arachne Claw: Self-Serve AI Agent Sandbox](projects/arachne-claw.md)
$50/mo product: 7 AI agents (research, lead scoring, competitor intel, content briefs, outreach, reviews, SEO audit). Dashboard + email delivery + REST API. Stripe billing, automated provisioning, upgrade funnel to enterprise tiers. **Live at [swarm.gentic.pro/claw](https://swarm.gentic.pro/claw)**

### [Markspace Protocol: Multi-Agent Coordination](projects/markspace.md)
Stigmergy-based coordination protocol replacing direct webhook messaging between AI agents. Guard-enforced scopes, 4-tier autonomy model (autonomous / notify / approval / blocked), conflict resolution, peer sync via HMAC. Novel architecture for production agent fleets.

### [VSAI Intent Classifier: Custom Fine-Tuned Model](projects/vsai-intent-model.md)
Fine-tuned **Qwen 2.5 1.5B with LoRA** for real-time voice call intent classification. 9-class model running locally on MLX at $0/month with Ollama failover. 3-tier cascade: MLX, Ollama, cloud fallback.

### [Hybrid Compute Architecture](architecture/hybrid-compute.md)
Local compute node + cloud control plane. Runs n8n, Qdrant RAG, PostgreSQL, Redis, reverse proxy with SSL, custom MCP servers. All orchestrated for zero-downtime failover.

### [Local TTS Infrastructure](projects/local-tts.md)
Multi-language text-to-speech (EN/ES/ZH) via Piper/Edge TTS with espeak fallback. Full local + cloud failover. **$0/month operating cost.**

### [iRELOP Lead Scoring Engine](projects/irelop-scoring.md)
Proprietary 100-point lead qualification model weighting Motivation (40), Opportunity (35), and Profile (25) signals. Powers automated routing across HOT/WARM/COOL/PASS tiers with voice agent dispatch.

### [Conversation Engine v5](projects/conversation-engine.md)
Inline directive architecture for AI-guided phone conversations. State tracker injects dynamic prompts per-turn. Synthetic training pipeline generating 1,500+ multi-turn conversations with adversarial seller personas. Handles evasive, emotional, and resistant callers.

### [n8n Workflow Engine](projects/n8n-workflows.md)
50+ production workflows handling lead ingestion, qualification, voice agent orchestration, CRM sync (HubSpot), drip campaigns, revenue reconciliation, and real-time Telegram alerting across multiple business verticals.

### [Scrapling Infrastructure](projects/scrapling-infra.md)
Dual-deployment web scraping: local node (native + MCP server) + cloud Docker (HTTP MCP for n8n). StealthyFetcher for anti-bot/Cloudflare bypass. Adaptive parsing self-heals on DOM changes.

---

## Architecture Overview

```
                        INGESTION LAYER
  Webhooks, Scrapling, Firecrawl, Voice Transcripts, Web Forms
                            |
                    INTELLIGENCE LAYER
  VSAI Intent Model, iRELOP Scoring, RAG (Qdrant), CE State Tracker
  LLM Routing: Local MLX -> Ollama -> Cloud (Grok -> Gemini -> Haiku)
                            |
                   COORDINATION LAYER
  Markspace Protocol, Tiered Autonomy, Guard-Enforced Scopes
  Clue (orchestrator) <-> KORA (executor) peer sync
                            |
                   ORCHESTRATION LAYER
  n8n Workflows, PostgreSQL, Redis, Budget Management
                            |
                      ACTION LAYER
  Voice Agents (Bland/Twilio), TTS, CRM Sync, Email (Resend)
  Arachne Swarm Dashboard, Telegram Alerts
```

---

## Technical Philosophy

[Full engineering principles in How I Work](HOW_I_WORK.md)

**Local-first, cost-zero where possible.** Every system starts with the question: *can this run on my own hardware at $0/month?* Custom model training, TTS, inference, scraping all run locally before touching cloud APIs.

**Fallback chains, not single points of failure.** LLM routing: `local MLX -> Ollama -> Grok -> Gemini -> Haiku`. TTS: `Piper -> Edge TTS -> espeak`. Compute: `Local -> Cloud`. Every critical path has a backup.

**Revenue-generating from day one.** Nothing ships as a demo. Every system processes real leads, serves real customers, or reduces real costs the day it goes live.

---

## Business Context

These systems power three active businesses:

- **DealiQ**. AI-powered real estate investment (Phoenix, Vegas, AZ, UT) processing 100+ leads/week
- **Gentic AI**. AI automation platform for local SMBs ($1,497-$2,497/mo tiers, $57K MRR target)
- **VoiceScheduleAI**. AI appointment scheduling with custom voice agents

Plus one SaaS product:
- **Arachne Claw**. $50/mo self-serve AI agent sandbox (top-of-funnel for Gentic AI)

---

## What I'm Looking For

I'm open to roles and contracts involving:
- AI/ML infrastructure engineering (full stack, own the pipeline)
- Voice AI and conversational AI systems
- AI agent development and multi-agent orchestration
- Automation architecture and workflow design
- Technical leadership for AI-first products

---

## Open Source

Production-tested modules. MIT licensed.

| Module | What It Does |
|--------|-------------|
| **[LLM Fallback Router](open-source/llm-fallback-router/)** | Multi-provider routing with circuit breakers and latency tracking |
| **[Conversation State Tracker](open-source/conversation-state-tracker/)** | Real-time question coverage, evasion detection, and inline directive generation |
| **[n8n Patterns](open-source/n8n-patterns/)** | Webhook receivers, LLM+JSON extraction, retry logic, dead letter queues |

[Browse all open source modules](open-source/)

---

## Case Studies

Real outcomes, real numbers. No demos.

| Case | Before | After |
|------|--------|-------|
| [Cloud to Local Inference](CASE_STUDIES.md#case-study-1-replacing-cloud-ai-with-local-inference) | $300-500/mo, 88% accuracy | **$0/mo, 96.6% accuracy** |
| [Cloud to Local TTS](CASE_STUDIES.md#case-study-2-zero-cost-tts-for-multi-language-voice-agents) | $200-400/mo projected | **$0/mo** |
| [Manual to Automated Qualification](CASE_STUDIES.md#case-study-3-from-manual-lead-qualification-to-full-automation) | ~40 leads/week contacted | **100+ leads/week, <15min response** |
| [Operating Cost Analysis](CASE_STUDIES.md#case-study-4-ai-agent-operating-cost-vs-revenue) | Cloud-everything | **<2% of revenue per client** |

[Read full case studies](CASE_STUDIES.md)

---

## Quick Links

[Resume](RESUME.md) | [Case Studies](CASE_STUDIES.md) | [Open Source](open-source/) | [How I Work](HOW_I_WORK.md) | [Live Demo: t.me/[CLUE_BOT]](https://t.me/[CLUE_BOT]) | [Arachne Claw: swarm.gentic.pro/claw](https://swarm.gentic.pro/claw)

---

gabe@gentic.pro | [Arachne Swarm](https://swarm.gentic.pro) | [Gentic AI](https://gentic.pro)

<sub>All systems described are live in production. Proprietary model weights, scoring formulas, and business logic are not included in this repo. Open source modules are MIT licensed.</sub>
