# ADR-0002: First providers (AI, weather, OTP, diagnosis, payments, hosting)
- Status: accepted
- Date: 2026-10-22
- Options considered: banks/options/*.md

**Simple matlab:** Har bahar ki service ke liye sab se aasan aur munasib option chuna hai. Sab "adapter" ke peeche hain, yani baad me badalna aasan hai.

## Decision
| Area | Choice now | Revisit |
|---|---|---|
| LLM | Claude (main) + small model for routing; eval vs GPT/Gemini | T-013 |
| Diagnosis | LLM vision fallback + Kindwise trial; Plantix quote | T-017 |
| Weather | Open-Meteo (commercial plan at launch) | — |
| OTP | Twilio Verify (dev) → local SMS aggregator (launch) | T-007 |
| Payments | Aggregator (Safepay / PayFast) | T-019 |
| Hosting | Vercel + Railway/Render, Docker | scale |
| Vector DB | pgvector (ADR-0001) | — |
## Consequences
Low cost and fast start; all providers swappable via backend adapters.
