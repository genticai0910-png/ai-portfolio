<div align="center">

# Gabe Acosta | Governed MCP Spine

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Postgres](https://img.shields.io/badge/Postgres-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-24B47E?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![MLX](https://img.shields.io/badge/MLX-000000?style=flat-square&logo=apple&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-ffffff?style=flat-square&logoColor=black)
![Pipecat](https://img.shields.io/badge/Pipecat-111827?style=flat-square)

I build a governed MCP spine for cost-controlled AI agents, voice workflows, and business automation.

[Receipts](receipts/) | [Case Studies](CASE_STUDIES.md) | [Resume](RESUME.md) | [How I Work](HOW_I_WORK.md)

</div>

---

## Start Here

This account is organized around one core system: a governed MCP spine.

The spine is the control layer that decides which agents can use which tools, under which policy, budget, approval, and audit constraints.

Start here:

1. **Governed MCP spine** - policy, budget, approval, and audit boundaries for agent/tool execution
2. **Voice orchestration** - `voxmaestro` as a deterministic voice workflow layer
3. **Cost-controlled inference** - `smart-ai-router` as a routing utility on the spine

If you are reviewing the work technically, start with the spine model first, then inspect VoxMaestro and the router as concrete modules.

---

## What I Build

| Domain | What to look for | Evidence status |
|---|---|---|
| Governed MCP spine | Tool access, policy checks, budget limits, approvals, receipts, and audit trails | Public-safe architecture surface |
| Voice-agent orchestration | Deterministic state control, filler gates, handoff protocol | Public alpha in `voxmaestro` |
| Cost-controlled inference | Local-first routing, provider fallback, budget-aware model choice | Scaffold in `smart-ai-router`; receipts needed |
| Workflow automation | n8n workflow categories and tool bridges | Redacted inventory planned |
| Business scoring interfaces | Public-safe contracts only, no formulas or private data | Placeholder receipts only |

This portfolio is a public trust surface, not a complete source dump. Proprietary scoring formulas, customer data, credentials, private URLs, internal IPs, and private infrastructure details are intentionally excluded.

---

## Repo Truth Map

| Type | Meaning |
|---|---|
| Owned product | Built or actively shaped as part of the governed MCP and automation stack |
| Public-safe scaffold | Exposes contracts/tests without proprietary business logic |
| Reference/fork | Used for learning, integration research, or upstream experimentation |
| Archived/research | Not part of the active product surface |

This distinction matters because this account contains both original product work and reference repositories.

| Category | Repos |
|---|---|
| Owned product | governed MCP spine, `voxmaestro`, `smart-ai-router`, `ai-portfolio` |
| Business IP / public-safe scaffold | redacted scoring and qualification contracts |
| Workflow infrastructure | `n8n-ollama-agents`, `awesome-n8n-templates` |
| Voice research/reference | `pipecat`, `voice-ui-kit`, `voicemode`, `wyoming-piper` |
| Research/reference forks | `gpt-researcher`, `autogpt`, `llm.c`, `trufflehog` |

---

## Flagship Work

| Project | What it proves | Status |
|---|---|---|
| Governed MCP spine | Agents use tools through policy, budget, approval, and audit boundaries | Public-safe architecture surface |
| VoxMaestro | YAML-driven voice orchestration, deterministic state machines, filler gates, handoff protocol | Alpha, runnable |
| smart-ai-router | Cost-aware multi-provider LLM routing concept | Public scaffold; needs package hardening |
| ai-portfolio | Architecture, receipts, and public proof map | Active portfolio |

---

## Proof Receipts Needed

See [`receipts/`](receipts/) for public-safe proof artifacts.

Current receipt backlog:

| Receipt | Purpose | Status |
|---|---|---|
| VSAI eval summary | Show evaluation method and headline accuracy without private datasets | Placeholder |
| Local inference cost model | Show cloud-to-local cost comparison | Placeholder |
| n8n inventory redacted | Show workflow categories without credentials or webhook URLs | Placeholder |
| Score receipt example | Show deterministic scoring metadata without proprietary formulas | Placeholder |
| Security sweep redacted | Show hardening workflow without exposing infrastructure | Placeholder |

Claims that are not linked to receipts should be treated as architecture context, not audited production proof.

---

## How It Fits Together

```text
Ingestion
  Voice transcripts, web forms, CRM events, workflow triggers

Intelligence
  Intent classification, public-safe scoring contracts, RAG, local/cloud LLM routing

Coordination
  Governed MCP spine, policy scopes, budget controls, approval boundaries

Orchestration
  n8n workflows, Postgres state, Redis queues/cache, provider fallback paths

Action
  Voice agents, SMS/email handoff, CRM updates, reporting, alerts
```

The strategy is local-first where possible, cloud where useful, and governed execution wherever a model or agent can affect money, customer communication, or business records.

---

## Case Studies

Case studies should be read as architecture and operating narratives unless a linked receipt proves the metric.

- [Conversation Engine](CASE_STUDIES.md#conversation-engine)
- [Cloud to Local Inference](CASE_STUDIES.md#case-study-1-replacing-cloud-ai-with-local-inference)
- [Cloud to Local TTS](CASE_STUDIES.md#case-study-2-zero-cost-tts-for-multi-language-voice-agents)
- [Manual to Automated Qualification](CASE_STUDIES.md#case-study-3-from-manual-lead-qualification-to-full-automation)
- [Operating Cost Analysis](CASE_STUDIES.md#case-study-4-ai-agent-operating-cost-vs-revenue)

---

## Contact

- GitHub: [github.com/genticai0910-png](https://github.com/genticai0910-png)
- Email: gabriel@gentic.pro
- Focus: governed MCP infrastructure, tool routing, cost controls, voice agents
