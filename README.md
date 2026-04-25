<div align="center">

# Gabe | AI Infrastructure & Automation

![Python](https://img.shields.io/badge/Python-3.14-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-14-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-66_workflows-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![MLX](https://img.shields.io/badge/MLX-Apple_Silicon-000000?style=flat-square&logo=apple&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-Local_LLM-white?style=flat-square)

**Building production-grade AI systems that generate revenue at zero marginal cost.**

[![Arachne Claw](https://img.shields.io/badge/Arachne_Claw-Live-22c55e?style=for-the-badge)](https://swarm.gentic.pro/claw)
[![Arachne Swarm](https://img.shields.io/badge/Arachne_Swarm-Live-22c55e?style=for-the-badge)](https://swarm.gentic.pro)
[![Stack](https://img.shields.io/badge/Secure_AI_Stack-Live-8B5CF6?style=for-the-badge)](https://stack.gentic.pro/stack)

</div>

---

> **Built and operated by [Gabe Acosta](https://github.com/genticai0910-png).** Operations leader (10+ years retail, automotive, federal disaster recovery) running three businesses on one self-built AI stack. Every system below is in production — no demos, no experiments.

> **Open to:** AI infrastructure roles, founding engineer / staff IC positions, technical advisory engagements, and Gentic AI partner conversations.
> **Contact:** gabriel@gentic.pro

---

## What I Build

| Domain | Stack | Status |
|--------|-------|--------|
| **AI Agent Orchestration** | Arachne Swarm dashboard, Markspace coordination protocol, tiered autonomy | Production |
| **Voice AI** | Bland AI, Twilio, Custom TTS (Piper/Edge TTS), intent classification | Production |
| **Custom Model Training** | Qwen 2.5 1.5B + LoRA, MLX inference, Ollama fallback, synthetic data pipelines | Production |
| **Workflow Automation** | n8n (66 workflows), webhooks, PostgreSQL, Redis | Production |
| **Cost-Optimized LLM Routing** | Multi-provider fallback chains, local-first inference, complexity-based routing | Production |
| **Lead Intelligence** | Proprietary scoring (iRELOP), RAG pipelines, Qdrant vector search | Production |
| **Web Intelligence** | Scrapling, Firecrawl, Crawl4AI, anti-bot bypass, structured extraction | Production |
| **Self-Hosted Infrastructure** | local compute node + cloud Docker (control plane), reverse proxy with SSL | Production |

---

## How It Fits Together

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
  Orchestrator <-> Executor agent peer sync
                            |
                   ORCHESTRATION LAYER
  n8n Workflows, PostgreSQL, Redis, Budget Management
                            |
                      ACTION LAYER
  Voice Agents (Bland/Twilio), TTS, CRM Sync, Email (Resend)
  Arachne Swarm Dashboard, Real-time Alerting
```

> Five layers, one operator. Local-first inference where possible, cloud for control plane and customer-facing surfaces, fallback chains on every critical path.

---

## Flagship Systems

> Three systems that show how I think. Each has a dedicated case study with architecture, decision history, and outcomes.

### 1. Conversation Engine + iRELOP Lead Scoring

**The work:** Proprietary 100-point lead qualification model (Motivation 40, Opportunity 35, Profile 25) feeding an inline-directive conversation engine. State tracker injects per-turn directives to handle evasive, emotional, and resistant callers across 1,500+ synthetic training conversations.

**Why it matters:** Most "AI sales agents" are wrappers around GPT-4 reading a script. This is a trained, evaluated, state-aware system that scores in real-time and routes HOT/WARM/COOL/PASS to voice/SMS/email/archive automatically.

**Stack:** Qwen 2.5, LoRA, MLX, n8n state machine, Postgres FOR UPDATE locking, Twilio, Bland AI

[Full case study →](./CASE_STUDIES.md#conversation-engine)

---

### 2. Ceiba Core — Agent Execution Control Plane

**The work:** Policy-enforced execution gateway for autonomous agents. Redis-backed, 6 DB tables, 10 active runtime policies. Telegram approval webhooks for high-stakes actions. Prevents agents from executing without policy clearance.

**Why it matters:** As agents get more capable, the bottleneck shifts from "can the agent do it" to "should the agent do it without asking." Ceiba is a working answer to that — a policy plane that lets agents move fast on cleared work and pauses for approval on the rest.

**Stack:** Redis, Postgres, OPA-style policy DSL, HMAC-signed approvals

**Live:** [ceiba.agency](https://ceiba.agency)

[Full case study →](./CASE_STUDIES.md#ceiba-core)

---

### 3. Arachne Swarm — Agent Orchestration Dashboard

**The work:** Real-time multi-agent dashboard with animated visualization, Kanban pipeline, budget gauge, multi-tenant isolation, Stripe billing. Built on top of Markspace, a stigmergy-based coordination protocol where agents write marks (intents/actions/observations) into a shared space rather than direct webhook messaging.

**Why it matters:** Most agent platforms hardcode agent-to-agent communication via webhooks, which doesn't scale beyond 3-4 agents. Stigmergy lets you grow the agent fleet without rewriting routing every time.

**Stack:** Next.js, WebSocket, Postgres, Stripe, custom canvas rendering

**Live:** [swarm.gentic.pro](https://swarm.gentic.pro) · **Sandbox:** [swarm.gentic.pro/claw](https://swarm.gentic.pro/claw)

[Full case study →](./CASE_STUDIES.md#arachne-swarm)

---

## Other Production Systems

<details>
<summary><b>Custom model training, voice infrastructure, lead pipelines, observability — click to expand</b></summary>

| System | What It Does | Stack |
|---|---|---|
| **VSAI Intent Classifier** | Fine-tuned 9-class voice intent model, 96.6% accuracy, $0/mo inference | Qwen 2.5, LoRA, MLX |
| **Hybrid Compute Architecture** | Local Apple Silicon + cloud Docker, 3-tier failover | Docker, SSH tunnels, LaunchAgent |
| **n8n Workflow Engine** | 66 production workflows: ingestion, scoring, voice dispatch, CRM, drip, reconciliation | n8n, Postgres, Redis |
| **Multi-Language TTS** | EN/ES/ZH text-to-speech with three-layer failover | Piper, Edge TTS, espeak |
| **prop-enricher** | $0/mo property data enrichment across 6 states (NV/AZ/FL/NC/SC/TX) | FastAPI, HomeHarvest |
| **Scrapling Infrastructure** | Anti-bot/Cloudflare bypass with adaptive parsing, dual local/cloud | Scrapling, MCP |
| **Agentic CRM OS** | Multi-tenant CRM with state machine (12 states, FOR UPDATE locking) | Postgres, n8n |
| **Langfuse v3 (self-hosted)** | LLM tracing, cost tracking, prompt versioning, zero vendor dependency | Langfuse, Postgres |
| **7-Phase Security Sweep** | Port scan, container audit, SSL, deps, secrets, Nuclei, Trivy | Bash, alerting integrations |
| **Spend Guardian** | Auto-kill on $5/hr or $20/day LLM spend, max 3 kills/day | Custom watchdog |
| **J-Neutron Brain API** | 6-tool MCP brain: pull/push/prune/guard/score/query across 12 Qdrant collections | FastAPI, MCP, Qdrant |
| **Gumroad Digital Store** | 18 products: n8n blueprints, content packs, AI bundles, lead-gen systems | Gumroad, Resend |
| **Revenue Infrastructure** | Stripe events, MRR snapshots, daily reconciliation cron | Stripe, Postgres |

</details>

---


## Business Context

**By the numbers:** 45+ production services, 32 cloud containers, 18 local managed services, 66 n8n workflows, 7 custom-trained models, 15+ PG schemas, 12 Qdrant collections, 18 digital products.

---

## LLM Engineering

<table>
<tr>
<td width="50%">

#### Custom Model Training
![LoRA](https://img.shields.io/badge/LoRA-fine--tuning-FF6F00?style=flat-square)
![Qwen](https://img.shields.io/badge/Qwen_2.5-1.5B%2F7B-22c55e?style=flat-square)
![Models](https://img.shields.io/badge/7-models_trained-f59e0b?style=flat-square)

7 production models fine-tuned on Qwen 2.5 with LoRA. Full pipeline: synthetic data generation with adversarial personas, MLX training on Apple Silicon, quantization (Q4/Q8), eval framework with pass gates.

</td>
<td width="50%">

#### Multi-Provider LLM Routing
![Chain](https://img.shields.io/badge/fallback-5_tier-26A5E4?style=flat-square)
![Cost](https://img.shields.io/badge/cost-optimized-22c55e?style=flat-square)
![Complexity](https://img.shields.io/badge/routing-complexity_based-8B5CF6?style=flat-square)

`Local MLX > Ollama > Grok > Gemini > Haiku`. Complexity-based routing: simple queries to cheap models, complex to premium. Circuit breakers, latency tracking. **$0 for 80%+ of queries.**

**[Open Source: LLM Fallback Router](open-source/llm-fallback-router/)**

</td>
</tr>
<tr>
<td width="50%">

#### Local Inference ($0/mo)
![MLX](https://img.shields.io/badge/MLX-Apple_Silicon-000?style=flat-square&logo=apple&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-local-white?style=flat-square)
![Latency](https://img.shields.io/badge/latency-%3C200ms-22c55e?style=flat-square)

MLX server (Ollama-compatible API) running custom models at $0/mo. 3-tier cascade: MLX (<200ms), Ollama, cloud. Handles intent classification, deal qualification, and conversation engine simultaneously.

</td>
<td width="50%">

#### RAG + Vector Search
![Qdrant](https://img.shields.io/badge/Qdrant-12_collections-24B47E?style=flat-square)
![Embedding](https://img.shields.io/badge/nomic--embed-768d-f59e0b?style=flat-square)

12 Qdrant collections for semantic search across leads, deals, competitors, knowledge. J-Neutron query planner with score fusion reranker. Inline directive architecture for conversation state injection.

</td>
</tr>
<tr>
<td width="50%">

#### Synthetic Data Generation
![Samples](https://img.shields.io/badge/samples-5000%2B-f59e0b?style=flat-square)
![Pipeline](https://img.shields.io/badge/pipeline-automated-22c55e?style=flat-square)

Larger models generate domain-specific training data. Adversarial seller personas (evasive, emotional, cooperative, tire-kicker). 1,500+ multi-turn conversations. Metadata tracking for quality analysis.

</td>
<td width="50%">

#### Eval Framework
![Accuracy](https://img.shields.io/badge/best-96.6%25-22c55e?style=flat-square)
![Automated](https://img.shields.io/badge/eval-automated-8B5CF6?style=flat-square)

Automated eval with pass gates: accuracy thresholds, latency benchmarks, cost per variant. Cold test sets, confusion matrices, per-class metrics. Tracks regression across versions.

</td>
</tr>
</table>

---

## Markspace: Multi-Agent Coordination

<table>
<tr>
<td width="60%">

A **novel stigmergy-based protocol** for coordinating autonomous AI agents in production. Instead of direct messaging, agents write marks (intents, actions, observations, warnings) into a shared space. A Guard enforces identity, scopes, and conflict policies.

**Key innovations:**
- **6 scoped domains**: scoring, voice, deals, ops, control, outreach
- **4-tier autonomy**: autonomous > notify > approval > blocked
- **Conflict resolution**: FIRST_WRITER (voice/deals), HIGHEST_CONFIDENCE (scoring/ops)
- **Approval gates**: outbound calls/SMS require human Telegram approval
- **Peer sync**: HMAC-authenticated mark replication between agents
- **Audit trail**: every Action mark persisted to PostgreSQL

Currently coordinating two production agents — an orchestrator and a tactical executor — across lead processing, voice calls, and deal analysis.

</td>
<td width="40%" align="center">

![Architecture](https://img.shields.io/badge/architecture-novel-8B5CF6?style=for-the-badge)

![Agents](https://img.shields.io/badge/agents-orchestrator_%2B_executor-22c55e?style=for-the-badge)

![Scopes](https://img.shields.io/badge/scopes-6_domains-26A5E4?style=for-the-badge)

![Autonomy](https://img.shields.io/badge/autonomy-4_tiers-f59e0b?style=for-the-badge)

![Sync](https://img.shields.io/badge/sync-HMAC_peer-DC382D?style=for-the-badge)

</td>
</tr>
</table>

---

## Open Source

Production-tested modules. MIT licensed.

| Module | What It Does |
|--------|-------------|
| **[LLM Fallback Router](open-source/llm-fallback-router/)** | Multi-provider routing with circuit breakers and latency tracking |
| **[Conversation State Tracker](open-source/conversation-state-tracker/)** | Real-time question coverage, evasion detection, and inline directive generation |

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
| [Zero-Cost Lead Enrichment](CASE_STUDIES.md#case-study-6-zero-cost-lead-enrichment-pipeline) | $200+/mo BatchData API | **$0/mo HomeHarvest + equity model** |

[Read full case studies](CASE_STUDIES.md)

---

## Quick Links

[Resume](RESUME.md) | [Case Studies](CASE_STUDIES.md) | [Open Source](open-source/) | [How I Work](HOW_I_WORK.md) | [Arachne Claw: swarm.gentic.pro/claw](https://swarm.gentic.pro/claw) | [Secure AI Stack: stack.gentic.pro/stack](https://stack.gentic.pro/stack)

---

## Tech Stack

<div align="center">

#### Models & Inference
![Qwen](https://img.shields.io/badge/Qwen_2.5-LoRA-FF6F00?style=flat-square)
![MLX](https://img.shields.io/badge/MLX-Apple_Silicon-000?style=flat-square&logo=apple&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-Local-white?style=flat-square)
![Grok](https://img.shields.io/badge/xAI-Grok-000?style=flat-square)
![Gemini](https://img.shields.io/badge/Google-Gemini-4285F4?style=flat-square&logo=google&logoColor=white)
![Claude](https://img.shields.io/badge/Anthropic-Claude-d4a574?style=flat-square)

#### Voice & Communication
![Bland AI](https://img.shields.io/badge/Bland_AI-Voice-5046E5?style=flat-square)
![Twilio](https://img.shields.io/badge/Twilio-SMS%2FVoice-F22F46?style=flat-square&logo=twilio&logoColor=white)
![Piper](https://img.shields.io/badge/Piper-TTS-22c55e?style=flat-square)
![Edge TTS](https://img.shields.io/badge/Edge_TTS-Neural-0078D4?style=flat-square)

#### Data & Infrastructure
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?style=flat-square&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-Vector-24B47E?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-66_flows-EA4B71?style=flat-square&logo=n8n&logoColor=white)

#### Frontend & Tools
![Next.js](https://img.shields.io/badge/Next.js-14-000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind](https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-Billing-635BFF?style=flat-square&logo=stripe&logoColor=white)

</div>

---

## About

I spent 10+ years running operations — high-volume retail, automotive sales, and federal disaster recovery (FEMA Public Assistance) — before going full-time on AI infrastructure in 2023. The combination matters: I've sat in P&L meetings *and* I ship the code. Most AI consultants can do one or the other.

Today I run three businesses on one self-built stack:
- **DealiQ** — AI-powered real estate investment (Phoenix, Vegas, AZ, UT)
- **Gentic AI** — AI automation platform for local SMBs
- **VoiceScheduleAI** — AI appointment scheduling

The portfolio above is the infrastructure that powers them.

---

## Engagement

**Hire me / partner with me / advise:** gabriel@gentic.pro
**Code:** [github.com/genticai0910-png](https://github.com/genticai0910-png)
**Resume:** [RESUME.md](./RESUME.md)
**Engineering principles:** [HOW_I_WORK.md](./HOW_I_WORK.md)

If you're building AI infrastructure for SMBs, real estate, or any vertical where cost-per-inference matters more than model size, I'd like to talk.

---

<div align="center">

<sub>All systems described are live in production. Proprietary model weights, scoring formulas, and business logic are not included in this repo. Open source modules are MIT licensed.</sub>

</div>
