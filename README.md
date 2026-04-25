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
| **Workflow Automation** | n8n (50+ workflows), webhooks, PostgreSQL, Redis | Production |
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

## Notable Builds

> Everything here is live, deployed, and processing real data. Not demos.

<table>
<tr>
<td width="50%">

#### Arachne Swarm Dashboard
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Next.js](https://img.shields.io/badge/Next.js-14-000?style=flat-square&logo=nextdotjs&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-realtime-blue?style=flat-square)

Full agent orchestration platform with **animated spider web visualization** showing agents as spiders crawling a web in real-time. Kanban pipeline, budget gauge, activity feed, multi-tenant isolation, Stripe billing.

**[swarm.gentic.pro](https://swarm.gentic.pro)**

</td>
<td width="50%">

#### Arachne Claw Landing Page
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Glassmorphism](https://img.shields.io/badge/design-glassmorphism-8B5CF6?style=flat-square)
![Canvas](https://img.shields.io/badge/canvas-animated_web-22c55e?style=flat-square)

$50/mo agent sandbox. **Apple-style glassmorphism cards**, animated spider web background with 22 crawling spiders (HiDPI canvas), chat demo with visual report card, 3-tier pricing.

**[swarm.gentic.pro/claw](https://swarm.gentic.pro/claw)**

</td>
</tr>
<tr>
<td width="50%">

#### Markspace Coordination Protocol
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Novel](https://img.shields.io/badge/architecture-novel-f59e0b?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.14-3776AB?style=flat-square&logo=python&logoColor=white)

**Stigmergy-based multi-agent coordination**. Agents write marks (intents, actions, observations) into a shared space. Guard enforces identity, scopes, and conflict policies. 4-tier autonomy model controls what agents can do without human approval.

</td>
<td width="50%">

#### VSAI Intent Classifier
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Accuracy](https://img.shields.io/badge/accuracy-96.6%25-22c55e?style=flat-square)
![Cost](https://img.shields.io/badge/cost-$0%2Fmo-22c55e?style=flat-square)

**Fine-tuned Qwen 2.5 1.5B** with LoRA for voice call intent classification. 9 classes, runs on Apple Silicon via MLX. 3-tier cascade with Ollama and cloud fallback. Replaced $300-500/mo cloud APIs.

</td>
</tr>
<tr>
<td width="50%">

#### Conversation Engine v5
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Architecture](https://img.shields.io/badge/inline-directives-8B5CF6?style=flat-square)
![Training](https://img.shields.io/badge/1500%2B-synthetic_convos-f59e0b?style=flat-square)

**Inline directive architecture** for AI phone conversations. State tracker injects dynamic prompts per-turn. Synthetic training pipeline with adversarial seller personas (evasive, emotional, resistant). 10-question coverage tracking.

</td>
<td width="50%">

#### iRELOP Lead Scoring
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Proprietary](https://img.shields.io/badge/IP-proprietary-f59e0b?style=flat-square)
![100pt](https://img.shields.io/badge/score-100_point-22c55e?style=flat-square)

**Proprietary 100-point scoring model**. Motivation (40) + Opportunity (35) + Profile (25). Powers automated routing: HOT >= 80 (voice), WARM >= 60 (SMS), COOL >= 40 (email), PASS < 40 (archive). GAN pipeline with Strategist + Auditor agents.

</td>
</tr>
<tr>
<td width="50%">

#### OpenClaw / Clue AI Agent
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Tools](https://img.shields.io/badge/30%2B-tools-22c55e?style=flat-square)

Private AI orchestrator powering daily operations across three businesses. 30+ integrated tools (web search, scraping, RAG, voice, CRM, scoring). Cost-optimized LLM chain (Grok → Gemini → Haiku). Voice input/output with TTS. Planning engine with persistent multi-step plans. Surfaces and access intentionally not public.

*Private interface — handle not public.*

</td>
<td width="50%">

#### n8n Workflow Engine
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Workflows](https://img.shields.io/badge/66-workflows-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![Webhooks](https://img.shields.io/badge/auth-HMAC%2BAPI_key-f59e0b?style=flat-square)

66 production workflows: lead ingestion, iRELOP scoring, voice dispatch, CRM sync (HubSpot), drip campaigns, revenue reconciliation, content distribution, Telegram alerting. All webhook-authenticated.

</td>
</tr>
<tr>
<td width="50%">

#### Hybrid Compute Architecture
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Cost](https://img.shields.io/badge/cost-$15%2Fmo-22c55e?style=flat-square)
![Uptime](https://img.shields.io/badge/failover-3_tier-22c55e?style=flat-square)

Local compute (ML, TTS, scraping, agent brain) + cloud Docker (n8n, databases, proxy, voice relay). Replaces $200-500/mo cloud infrastructure. SSL, reverse proxy, SSH tunnels, LaunchAgent management.

</td>
<td width="50%">

#### Multi-Language TTS
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Cost](https://img.shields.io/badge/cost-$0%2Fmo-22c55e?style=flat-square)
![Languages](https://img.shields.io/badge/langs-EN%2FES%2FZH-22c55e?style=flat-square)

Piper + Edge TTS + espeak. Three-layer failover, cross-node recovery. Processes hundreds of voice interactions weekly. Replaced $200-400/mo projected cloud TTS costs with zero.

</td>
</tr>
<tr>
<td width="50%">

#### J-Neutron Brain API
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![MCP](https://img.shields.io/badge/MCP-6_tools-8B5CF6?style=flat-square)
![Qdrant](https://img.shields.io/badge/Qdrant-12_collections-24B47E?style=flat-square)

6-tool MCP brain API: pull, push, prune, guard, score, query. Query planner across 12 Qdrant collections with score fusion reranker. Voicemail upload/serve endpoint. Traefik-fronted.

</td>
<td width="50%">

#### Agentic CRM OS
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Tables](https://img.shields.io/badge/schema-15_tables-4169E1?style=flat-square)
![Tenants](https://img.shields.io/badge/tenants-3-22c55e?style=flat-square)

Multi-tenant CRM with **state machine** (`fn_transition_lead`, 12 states, FOR UPDATE locking). 9 n8n workflows, 3 active tenants (DealiQ, Gentic AI, VSAI). Lead lifecycle from ingestion to disposition.

</td>
</tr>
<tr>
<td width="50%">

#### Custom Model Training Pipeline
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Models](https://img.shields.io/badge/models-7_trained-f59e0b?style=flat-square)
![MLX](https://img.shields.io/badge/MLX-LoRA-000?style=flat-square&logo=apple&logoColor=white)

Full fine-tuning pipeline: synthetic data generation (adversarial personas), LoRA training on Qwen 2.5, MLX quantization, eval framework. **7 production models** across intent classification, deal qualification, and conversation engine.

</td>
<td width="50%">

#### DealiQ Market Harvester
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Python](https://img.shields.io/badge/Python-harvester-3776AB?style=flat-square&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-containerized-2496ED?style=flat-square)

Automated real estate market data harvester. Property extraction with defuddle + site templates, iRELOP enrichment pipeline. Feeds DealiQ analytics and lead scoring.

</td>
</tr>
<tr>
<td width="50%">

#### GenticOS
![Status](https://img.shields.io/badge/status-built-f59e0b?style=flat-square)
![BullMQ](https://img.shields.io/badge/BullMQ-workers-DC382D?style=flat-square)
![OPA](https://img.shields.io/badge/OPA-policies-7D9199?style=flat-square)

Full AI-powered RE operating system. Node 20, TypeScript, BullMQ job queue (8 tools, 5 concurrency), OPA runtime policies. Worker handles Twilio, Bland AI, email dispatch.

</td>
<td width="50%">

#### MegaMindZ Knowledge Graph
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Supabase](https://img.shields.io/badge/Supabase-backend-3FCF8E?style=flat-square&logo=supabase&logoColor=white)

Supabase-backed knowledge graph for cross-domain intelligence. Powers J-Neutron query planner and Clue's long-term memory.

</td>
</tr>
<tr>
<td width="50%">

#### Pipecat Voice Pipeline
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![WebRTC](https://img.shields.io/badge/WebRTC-LiveKit-blue?style=flat-square)
![Cost](https://img.shields.io/badge/cost-$0.01%2Fcall-22c55e?style=flat-square)

Real-time voice AI pipeline replacing Bland AI for lower-cost calls. LiveKit relay on cloud, Pipecat on local. **$0.01/call** vs $0.07+ on Bland.

</td>
<td width="50%">

#### SearXNG Self-Hosted Search
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Privacy](https://img.shields.io/badge/privacy-zero_tracking-22c55e?style=flat-square)

Self-hosted meta-search engine with proxy. Powers web search tools across Clue, KORA, and n8n workflows. Zero API costs, zero tracking, zero rate limits.

</td>
</tr>
<tr>
<td width="50%">

#### AccompAgent Gateway
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Auth](https://img.shields.io/badge/auth-HMAC%2BIP-f59e0b?style=flat-square)
![Tools](https://img.shields.io/badge/bridge-12_tools-22c55e?style=flat-square)

HMAC + IP allowlist gateway for Accomplish task automation. MCP stdio bridge with 12 tools and 38 job types. Supabase backend.

</td>
<td width="50%">

#### Scrapling Infrastructure
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Stealth](https://img.shields.io/badge/stealth-anti--bot-f59e0b?style=flat-square)
![Dual](https://img.shields.io/badge/deploy-local%2Bcloud-22c55e?style=flat-square)

Dual-deployment web scraping: local (native + MCP) + cloud Docker (HTTP for n8n). StealthyFetcher for anti-bot/Cloudflare bypass. Adaptive DOM parsing self-heals on site changes.

</td>
</tr>
<tr>
<td width="50%">

#### Gumroad Digital Product Store
![Status](https://img.shields.io/badge/status-live-22c55e?style=flat-square)
![Products](https://img.shields.io/badge/products-18-f59e0b?style=flat-square)
![Store](https://img.shields.io/badge/store-genticai.gumroad.com-ff90e8?style=flat-square)

**18 digital products** across 4 categories: n8n automation blueprints ($12-$97), social media content packs for 6 verticals ($12-$77), AI content creator bundles ($17-$47), and lead generation systems ($49-$97). Auto-delivered via Resend.

**[genticai.gumroad.com](https://genticai.gumroad.com)**

</td>
<td width="50%">

#### Revenue Infrastructure
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Stripe](https://img.shields.io/badge/Stripe-reconciliation-635BFF?style=flat-square&logo=stripe&logoColor=white)

Stripe event tracking, subscription management, MRR snapshots, daily revenue reconciliation (1 PM UTC cron). PG schema `revenue` with targets and actuals.

</td>
</tr>
</table>

<tr>
<td width="50%">

#### KORA Tactical Agent
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![LLM](https://img.shields.io/badge/chain-gemma4_>_kimi_>_gemini-22c55e?style=flat-square)

Autonomous operations agent. Owns voice ops, Gumroad, pipeline execution. Peer to the orchestrator agent (not subordinate). Private interface. $0 LLM chain (gemma4:e4b > kimi-k2 > gemini-flash-lite). Zombie prevention, port-check before launch.

</td>
<td width="50%">

#### OpenClaw Broker v1
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![API](https://img.shields.io/badge/REST-gateway-26A5E4?style=flat-square)
![Tiers](https://img.shields.io/badge/pricing-$50--$5997-f59e0b?style=flat-square)

SaaS REST API gateway at broker.gentic.pro. Multi-tenant agent execution engine with governance gates (AuthN, AuthZ, Policy, Budget, Redact, Audit). Sandbox to Enterprise pricing.

</td>
</tr>
<tr>
<td width="50%">

#### Gentic Lead Pipeline
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![HubSpot](https://img.shields.io/badge/HubSpot-auto_deals-FF7A59?style=flat-square)
![Pipeline](https://img.shields.io/badge/webhook-to_CRM-22c55e?style=flat-square)

Webhook > validate > iRELOP score > PostgreSQL > Telegram alert > HubSpot auto-deal creation. HOT/WARM/COOL leads auto-create contacts + deals with AI-generated strategies.

</td>
<td width="50%">

#### Gentic Conversation Engine
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![WebSocket](https://img.shields.io/badge/WebSocket-realtime-blue?style=flat-square)
![SMS](https://img.shields.io/badge/Twilio-SMS-F22F46?style=flat-square)

AI advisor "Alex" via WebSocket (wss://api.gentic.pro/ws). SMS conversation engine with 10-question state tracker, session management per phone number (1hr TTL). Twilio toll-free integrated.

</td>
</tr>
<tr>
<td width="50%">

#### Outreach Dispatch Pipeline
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Cron](https://img.shields.io/badge/cron-every_5min-f59e0b?style=flat-square)
![Channels](https://img.shields.io/badge/SMS_%2B_Email-drip-22c55e?style=flat-square)

n8n cron every 5 min (8AM-8PM Pacific). WARM: 4-stage SMS drip (days 1,3,7,14). COOL: 4-stage email drip (days 1,5,10,20). Twilio SMS + Resend email.

</td>
<td width="50%">

#### GAN Lead Pipeline
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Architecture](https://img.shields.io/badge/agents-Strategist_%2B_Auditor-8B5CF6?style=flat-square)

iRELOP GAN Pipeline: Strategist agent generates offer strategies, Auditor validates. Follow-up scheduling. 5 PG tables. Contract-based qualification with disposition tracking.

</td>
</tr>
<tr>
<td width="50%">

#### Property Extractor
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Defuddle](https://img.shields.io/badge/defuddle-extraction-22c55e?style=flat-square)

DealiQ property data extractor using defuddle + site-specific templates. Pulls property details from listing URLs, enriches with iRELOP scoring. Feeds deal analysis pipeline.

</td>
<td width="50%">

#### Security Sweep Tool
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Phases](https://img.shields.io/badge/phases-7-DC382D?style=flat-square)
![Nuclei](https://img.shields.io/badge/Nuclei_%2B_Trivy-scanners-f59e0b?style=flat-square)

Production security sweep (`~/bin/security-sweep`). 7-phase audit: port scan, container audit, SSL check, dependency scan, secret detection, Nuclei vuln scan, Trivy image scan. Telegram alerts.

</td>
</tr>
<tr>
<td width="50%">

#### Social Content Funnel
![Status](https://img.shields.io/badge/status-built-f59e0b?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-4_workflows-EA4B71?style=flat-square)

Content distribution pipeline: Distributor v2, Generate, Approval (Airtable), Lead Capture. HubSpot integration, Telegram notifications. Automated social media content across platforms.

</td>
<td width="50%">

#### Smart AI Router
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-webhook-EA4B71?style=flat-square)
![Models](https://img.shields.io/badge/routes-multi_model-8B5CF6?style=flat-square)

General-purpose LLM routing workflow. Receives requests via webhook, selects optimal model based on task complexity and cost constraints. Returns unified response format.

</td>
</tr>
<tr>
<td width="50%">

#### OpenClaw Guardian
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Watchdog](https://img.shields.io/badge/type-watchdog-DC382D?style=flat-square)

Spend monitor + health checker + auto-kill. Tracks hourly/daily LLM spend, kills gateway if thresholds exceeded ($5/hr, $20/day). VPS container health via SSH. Max 3 kills/day with cooldown.

</td>
<td width="50%">

#### Memory Writer + Watchdog
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![LaunchAgent](https://img.shields.io/badge/managed-launchd-000?style=flat-square)

Automated memory persistence pipeline. Syncs conversation learnings, feedback, and project state to persistent storage. Watchdog ensures memory services stay healthy.

</td>
</tr>
<tr>
<td width="50%">

#### Claw-Kanban
![Status](https://img.shields.io/badge/status-built-f59e0b?style=flat-square)
![Multi-Agent](https://img.shields.io/badge/routes-Claude_%2B_Codex_%2B_Gemini-8B5CF6?style=flat-square)

Multi-agent task routing kanban board. Routes tasks to Claude, Codex, Gemini, and other AI agents based on task type and model capability. Visual pipeline management.

</td>
<td width="50%">

#### SSH Tunnel Architecture
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Tunnels](https://img.shields.io/badge/tunnels-4_active-22c55e?style=flat-square)

4 persistent SSH tunnels (J-Neutron, PostgreSQL, MLX, Extractor) connecting local compute to cloud control plane. LaunchAgent-managed with auto-reconnect. Cloudflared tunnel for additional routing.

</td>
</tr>
<tr>
<td width="50%">

#### prop-enricher: $0/mo Lead Enrichment
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Cost](https://img.shields.io/badge/cost-$0%2Fmo-22c55e?style=flat-square)
![Markets](https://img.shields.io/badge/markets-NV%2FAZ%2FFL%2FNC%2FSC%2FTX-f59e0b?style=flat-square)

FastAPI service wrapping HomeHarvest (Realtor.com). Returns estimated value, equity (30yr amortization model), years owned, tax annual — no API key required. Deployed as VPS Docker container with semaphore-serialized rate limiting. Feeds iRELOP pipeline at $0/month vs $200+/mo BatchData.

</td>
<td width="50%">

#### Operator Memory Architecture
![Status](https://img.shields.io/badge/status-live-22c55e?style=flat-square)
![Tiers](https://img.shields.io/badge/tiers-5_memory-8B5CF6?style=flat-square)
![MCP](https://img.shields.io/badge/MCP-4_tools-22c55e?style=flat-square)

Production blueprint for tiered agent cognition: Working / Episodic / Semantic / Financial / Risk memory. Includes schemas, poisoning defenses, reflection prompts, cost model, and MCP integration spec. Interactive reference at [stack.gentic.pro/stack](https://stack.gentic.pro/stack).

</td>
</tr>
<tr>
<td width="50%">

#### Ceiba Core: Agent Execution Control Plane
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Gateway](https://img.shields.io/badge/ceiba.agency-live-22c55e?style=flat-square)
![Policies](https://img.shields.io/badge/policies-10-f59e0b?style=flat-square)

Policy-enforced execution control plane for autonomous agents. Redis-backed gateway, 6 DB tables, 10 active policies, 2 tenants. Telegram webhook for approval-gated actions. Prevents agents from executing without policy clearance.

**[ceiba.agency](https://ceiba.agency)**

</td>
<td width="50%">

#### Langfuse v3: LLM Observability
![Status](https://img.shields.io/badge/status-production-22c55e?style=flat-square)
![Self-Hosted](https://img.shields.io/badge/self--hosted-trace.gentic.pro-22c55e?style=flat-square)

Self-hosted Langfuse v3 at `trace.gentic.pro`. Full LLM tracing, cost tracking, and prompt versioning wired into OpenClaw + KORA. Zero vendor dependency, all traces on-prem.

**[trace.gentic.pro](https://trace.gentic.pro)**

</td>
</tr>
</table>

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
66 production workflows handling lead ingestion, qualification, voice agent orchestration, CRM sync (HubSpot), drip campaigns, revenue reconciliation, and real-time Telegram alerting across multiple business verticals.

### [prop-enricher: $0/mo Property Enrichment](projects/prop-enricher.md)
FastAPI microservice wrapping HomeHarvest (Realtor.com). No API key, no cost. Returns estimated value, equity via 30yr amortization model, years owned, tax data. Deployed on VPS Docker, semaphore-serialized. Feeds iRELOP scoring pipeline across NV, AZ, FL, NC, SC, TX.

### [Operator Memory Architecture](https://stack.gentic.pro/stack)
Production blueprint for tiered agent cognition. 5-tier model (Working / Episodic / Semantic / Financial / Risk) with schemas, poisoning defenses, reflection prompts, cost model, and MCP integration spec. Live at [stack.gentic.pro/stack](https://stack.gentic.pro/stack).

### [Scrapling Infrastructure](projects/scrapling-infra.md)
Dual-deployment web scraping: local node (native + MCP server) + cloud Docker (HTTP MCP for n8n). StealthyFetcher for anti-bot/Cloudflare bypass. Adaptive parsing self-heals on DOM changes.

---

## Technical Philosophy

[Full engineering principles in How I Work](HOW_I_WORK.md)

**Local-first, cost-zero where possible.** Every system starts with the question: *can this run on my own hardware at $0/month?* Custom model training, TTS, inference, scraping all run locally before touching cloud APIs.

**Fallback chains, not single points of failure.** LLM routing: `local MLX -> Ollama -> Grok -> Gemini -> Haiku`. TTS: `Piper -> Edge TTS -> espeak`. Compute: `Local -> Cloud`. Every critical path has a backup.

**Revenue-generating from day one.** Nothing ships as a demo. Every system processes real leads, serves real customers, or reduces real costs the day it goes live.

---

## Business Context

**By the numbers:** 45+ production services, 32 cloud containers, 18 local managed services, 66 n8n workflows, 7 custom-trained models, 15+ PG schemas, 12 Qdrant collections, 18 digital products.

These systems power three active businesses:

- **DealiQ**. AI-powered real estate investment (Phoenix, Vegas, AZ, UT) processing 100+ leads/week
- **Gentic AI**. AI automation platform for local SMBs ($1,497-$2,497/mo tiers, $57K MRR target)
- **VoiceScheduleAI**. AI appointment scheduling with custom voice agents

Plus one SaaS product:
- **Arachne Claw**. $50/mo self-serve AI agent sandbox (top-of-funnel for Gentic AI)

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

Currently coordinating **Clue** (orchestrator) and **KORA** (executor) across lead processing, voice calls, and deal analysis.

</td>
<td width="40%" align="center">

![Architecture](https://img.shields.io/badge/architecture-novel-8B5CF6?style=for-the-badge)

![Agents](https://img.shields.io/badge/agents-Clue_%2B_KORA-22c55e?style=for-the-badge)

![Scopes](https://img.shields.io/badge/scopes-6_domains-26A5E4?style=for-the-badge)

![Autonomy](https://img.shields.io/badge/autonomy-4_tiers-f59e0b?style=for-the-badge)

![Sync](https://img.shields.io/badge/sync-HMAC_peer-DC382D?style=for-the-badge)

</td>
</tr>
</table>

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
| [Zero-Cost Lead Enrichment](CASE_STUDIES.md#case-study-6-zero-cost-lead-enrichment-pipeline) | $200+/mo BatchData API | **$0/mo HomeHarvest + equity model** |

[Read full case studies](CASE_STUDIES.md)

---

## Quick Links

[Resume](RESUME.md) | [Case Studies](CASE_STUDIES.md) | [Open Source](open-source/) | [How I Work](HOW_I_WORK.md) | [Arachne Claw: swarm.gentic.pro/claw](https://swarm.gentic.pro/claw) | [Secure AI Stack: stack.gentic.pro/stack](https://stack.gentic.pro/stack)

---

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

<div align="center">

gabe@gentic.pro | [Arachne Swarm](https://swarm.gentic.pro) | [Gentic AI](https://gentic.pro)

<sub>All systems described are live in production. Proprietary model weights, scoring formulas, and business logic are not included in this repo. Open source modules are MIT licensed.</sub>

</div>
