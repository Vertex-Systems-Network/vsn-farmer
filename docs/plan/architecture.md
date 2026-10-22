# Architecture (initial — confirm via ADR-0001)

```
[PWA Next.js] ──REST──> [FastAPI]
[WhatsApp BSP webhook] ─┘   ├─ auth/roles (OTP)
                            ├─ farm memory (Postgres)
                            ├─ advisory pipeline: context builder → retriever (pgvector) → LLM → safety check → route (farmer | expert queue)
                            ├─ adapters/: llm, weather, diagnosis, otp_sms, payments, messaging, storage, stt_tts
                            └─ jobs: alerts, calendar, follow-ups (queue worker)
```

Principles
- Context builder decides what farm data the LLM sees (privacy, FR-5.5).
- Every answer stores: sources used, model, cost, safety verdict (FR-12.1 cost/advisory, FR-12.7).
- Safety check = rules (dose/chemical keywords, low retrieval confidence, diagnosis confidence) + LLM self-check → escalate.
- Eval set: curated Q&A per crop, reviewed by experts; run on every prompt/model change.
