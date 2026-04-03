# Case Studies

> Real outcomes from production systems. No demos, no proofs-of-concept.

---

## Case Study 1: Replacing Cloud AI with Local Inference

### Challenge
Voice AI operations processing 100+ calls/week were spending $300-500/month on cloud LLM APIs for intent classification alone. Latency averaged 800ms-1.2s per classification, creating awkward pauses in live calls.

### Solution
Fine-tuned Qwen 2.5 1.5B with LoRA on domain-specific voice transcripts. Deployed on local compute node using MLX inference with Ollama as failback. 3-tier cascade: MLX (primary), Ollama (local fallback), VPS Ollama (remote fallback).

### Results
| Metric | Before | After |
|--------|--------|-------|
| Monthly inference cost | $300-500 | **$0** |
| Classification latency | 800ms-1.2s | **<200ms** |
| Accuracy | ~88% (generic model) | **96.6%** |
| Uptime | Dependent on API provider | **Self-controlled, 3-tier fallback** |

### Key Insight
Small models fine-tuned on domain data consistently beat large general models for classification tasks. The 1.5B parameter model outperforms models 10-50x its size because it learned the specific vocabulary and patterns of real estate lead calls.

---

## Case Study 2: Zero-Cost TTS for Multi-Language Voice Agents

### Challenge
Cloud TTS services (Google, AWS Polly, ElevenLabs) were charging $0.004-0.016 per 1,000 characters. At scale across EN/ES/ZH calls, monthly TTS costs were projected to hit $200-400/month.

### Solution
Self-hosted Piper + Edge TTS with espeak fallback. Cross-node failover between Mac Mini and VPS.

### Results
| Metric | Before (Cloud) | After (Self-Hosted) |
|--------|----------------|---------------------|
| Monthly cost | $200-400 projected | **$0** |
| Languages | Depends on provider | **EN, ES, ZH** |
| Failover layers | 1 (provider SLA) | **3 (Piper, Edge TTS, espeak)** |
| Vendor lock-in | High | **None** |

### Key Insight
TTS is a solved problem at the open-source level. Piper voices are indistinguishable from cloud voices in phone-quality audio. Edge TTS provides neural quality at zero cost as a secondary layer.

---

## Case Study 3: From Manual Lead Qualification to Full Automation

### Challenge
A solo real estate investor was manually reviewing 100+ inbound leads per week. Each lead required 5-10 minutes of research and a phone call to qualify. Effective capacity: ~40 leads/week actually contacted, 60+ going cold.

### Solution
End-to-end automated pipeline: webhook ingestion, data normalization, iRELOP scoring (100-point proprietary model), tier-based routing, automated voice agent outreach for warm/cool tiers, immediate callback routing for hot leads. CRM sync to HubSpot with auto-deal creation.

### Results
| Metric | Before | After |
|--------|--------|-------|
| Leads contacted/week | ~40 | **100+** |
| Time to first contact | 2-48 hours | **<15 minutes (hot), <2 hours (warm)** |
| Manual qualification time | 5-10 min/lead | **0 (automated)** |
| Lead leakage (uncontacted) | ~60% | **<5%** |

### Key Insight
Speed-to-contact is the single biggest predictor of deal conversion in real estate. Automating the qualification and first-touch process fundamentally changes conversion rates because leads are contacted while still motivated.

---

## Case Study 4: AI Agent Operating Cost vs. Revenue

### Challenge
Demonstrate that a full AI automation stack can operate at costs low enough to serve SMBs profitably at accessible price points.

### Solution
Architect everything local-first with cloud as fallback only. Own compute hardware, use open-source models, self-host all services.

### Monthly Operating Cost Breakdown
| Service | Cost |
|---------|------|
| VPS hosting | ~$12 |
| Domain/SSL | ~$1 |
| Cloud LLM (fallback only) | ~$5-15 |
| Voice (Bland AI/Twilio, per-use) | Variable |
| Everything else | $0 (self-hosted) |
| **Total fixed infrastructure** | **~$15-30/month** |

### Revenue per Client
| Product | Monthly |
|---------|---------|
| Growth Engine | $1,497 |
| Lead Recovery | $2,497 |
| Arachne Claw (self-serve) | $50 |

### Margin
Infrastructure cost is <2% of revenue per client. Even at a single client, the unit economics work. At 30 clients ($57K MRR target), infrastructure is a rounding error.

### Key Insight
The competitive moat is the cost structure, not the AI itself. Competitors running on cloud-everything pay 10-20x more in infrastructure, which either eats their margin or forces higher prices. Local-first architecture turns infrastructure into a profit center.

---

## Case Study 5: Multi-Agent Coordination with Tiered Autonomy

### Challenge
Two AI agents (Clue as orchestrator, KORA as executor) needed to coordinate on lead processing, voice calls, and deal analysis without stepping on each other. Direct webhook messaging was fragile, with no conflict resolution or approval gates for sensitive actions.

### Solution
Built Markspace, a stigmergy-based coordination protocol. Agents write "marks" (intents, actions, observations) into a shared space. A Guard enforces identity and permissions per scope. Outbound calls/SMS require human approval via Telegram inline keyboard. Four autonomy tiers control what agents can do without human oversight.

### Results
| Metric | Before | After |
|--------|--------|-------|
| Coordination method | Direct webhooks | **Stigmergy (decoupled)** |
| Conflict resolution | None (race conditions) | **FIRST_WRITER / HIGHEST_CONFIDENCE policies** |
| Outbound call safety | Manually triggered | **Tiered: autonomous for scoring, approval-gated for calls** |
| Audit trail | Partial logs | **Every action mark persisted to PostgreSQL** |

### Key Insight
Agent coordination is an infrastructure problem, not an AI problem. The agents don't need to "understand" each other. They need a shared space with enforced rules. Stigmergy (indirect coordination through environment marks) is simpler and more robust than direct agent-to-agent messaging.

---

[Back to Portfolio](README.md)
