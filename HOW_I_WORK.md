<div align="center">

# How I Work

### 8 Engineering Principles

> Engineering principles that drive every system I build.

[![Back to Portfolio](https://img.shields.io/badge/Back_to-Portfolio-22c55e?style=flat-square)](README.md)
[![Resume](https://img.shields.io/badge/Resume-view-000?style=flat-square)](RESUME.md)
[![Case Studies](https://img.shields.io/badge/Case_Studies-view-f59e0b?style=flat-square)](CASE_STUDIES.md)

</div>

---

## 1. Local-First, Cloud-Fallback
![Principle](https://img.shields.io/badge/principle-cost_zero-22c55e?style=flat-square)

Every system starts with the question: **can this run on my own hardware?**

Not because cloud is bad. Because dependency is expensive. When your voice AI pipeline depends on 4 cloud APIs, you inherit 4 SLAs, 4 pricing models, and 4 points of failure. Local-first means I control latency, cost, and uptime. Cloud becomes a fallback, not a crutch.

**Example:** The VSAI Intent Classifier runs on a local Apple Silicon node at $0/month. If the local node goes down, Ollama takes over locally. If local fails, the cloud mirror takes over. Three layers deep before I touch a paid API.

---

## 2. Fallback Chains, Not Hope
![Principle](https://img.shields.io/badge/principle-redundancy-26A5E4?style=flat-square)

Every critical path gets a fallback chain. Not "we should add redundancy later." It's part of the initial architecture.

```
LLM:      Local MLX -> Local Ollama -> Cloud Grok -> Cloud Gemini -> Cloud Haiku
TTS:      Piper -> Edge TTS -> espeak
Compute:  Local compute -> Cloud Docker
Scraping:  Local Scrapling -> Firecrawl
```

Each layer degrades gracefully. The user never knows a failover happened.

---

## 3. Ship Revenue, Not Demos
![Principle](https://img.shields.io/badge/principle-production_first-f59e0b?style=flat-square)

Nothing goes into production as a proof-of-concept. Every system processes real leads, serves real customers, or reduces real costs from day one.

This means building ugly-but-functional before pretty-but-theoretical. It means the scoring model ships with 4 tiers and a simple rules engine before spending 3 months training an ML model. It means the TTS stack runs on espeak (robotic but functional) while Piper voices are being evaluated.

**Iterate in production, not in a notebook.**

---

## 4. Small Models, Big Results
![Principle](https://img.shields.io/badge/principle-efficiency-22c55e?style=flat-square)

The industry defaults to "use the biggest model you can afford." I default to "use the smallest model that solves the problem."

A 1.5B parameter model fine-tuned on your data beats a 70B general model on your task and costs nothing to run. The VSAI Intent Classifier proves this: 96.6% accuracy on a model that fits alongside a dozen other services on a single local node.

**Model selection framework:**
1. Can a 1-3B model do this with fine-tuning? Use it.
2. Does it need general reasoning? Use a 7B model.
3. Does it need broad knowledge + reasoning? Cloud API, cheapest tier.
4. Is it customer-facing creative output? Cloud API, premium tier.

---

## 5. Tiered Autonomy for AI Agents
![Principle](https://img.shields.io/badge/principle-safety-8B5CF6?style=flat-square)

Not everything should require human approval. Not everything should be autonomous. The answer is tiers.

```
Tier 1 AUTONOMOUS:  Scoring, monitoring, analysis. No approval needed.
Tier 2 NOTIFY:      Deployments, restarts, offers. Notify human, then act.
Tier 3 APPROVAL:    Outbound calls, SMS, email. Blocked until human approves.
Tier 4 BLOCKED:     Kill processes, delete data. Never autonomous.
```

This framework means AI agents can operate at speed on safe actions while maintaining hard gates on actions with real-world consequences.

---

## 6. Observability Is Not Optional
![Principle](https://img.shields.io/badge/principle-visibility-DC382D?style=flat-square)

If I can't see what a system is doing, I don't ship it. Every pipeline gets:
- **State tracking** for every item in the pipeline
- **Error classification** that explains why something failed, not just that it failed
- **Dead letter queues** so nothing gets silently dropped
- **Audit trails** for every lead state transition and agent action

The n8n execution logs, PostgreSQL audit tables, and Telegram alerts form a monitoring layer that catches issues before customers notice.

---

## 7. The 80/20 of Automation
![Principle](https://img.shields.io/badge/principle-leverage-f59e0b?style=flat-square)

Not everything should be automated. The goal is to automate the 80% of work that's repetitive and keep humans in the loop for the 20% that requires judgment.

**Automated:** Lead scoring, initial outreach, CRM updates, follow-up scheduling, data normalization, report generation.

**Human-in-the-loop:** Final deal negotiation, complex objection handling, relationship-critical communication, financial transactions.

The automation handles volume. The human handles nuance.

---

## 8. Own Your Infrastructure
![Principle](https://img.shields.io/badge/principle-independence-22c55e?style=flat-square)

SaaS tools are rentals. When the rental price goes up or the landlord changes the terms, you're stuck.

I self-host n8n, databases, vector stores, TTS, and ML inference. Not because it's easy (it's not), but because it gives me:
- **Pricing control** that doesn't scale with someone else's pricing model
- **Feature control** to modify anything, anytime
- **Data control** so customer data never leaves my infrastructure
- **Uptime control** without checking someone else's status page

The only external dependencies are telephony (Twilio/Bland) and cloud LLMs (fallback only). Everything else runs on hardware I own.

---

<div align="center">

[![Back to Portfolio](https://img.shields.io/badge/Back_to-Portfolio-22c55e?style=for-the-badge)](README.md)
[![Case Studies](https://img.shields.io/badge/Case_Studies-view-f59e0b?style=for-the-badge)](CASE_STUDIES.md)

</div>
