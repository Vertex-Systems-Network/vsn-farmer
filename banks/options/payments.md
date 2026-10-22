# Options: Payments
- Status: chosen (ADR-0002) — phase 6
- Related FR: FR-13

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes |
|---|---|---|---|---|---|---|---|
| Aggregator (Safepay / PayFast) | 5 | 5 | 3 | 4 | 4 | 21 | One integration → JazzCash, Easypaisa, cards (vendor claims; verify official docs) |
| JazzCash direct | 4 | 5 | 4 | 2 | 3 | 18 | |
| Easypaisa direct | 4 | 5 | 4 | 2 | 3 | 18 | |
| International card gateway | 2 | 1 | 3 | 4 | 3 | 13 | |

## Recommendation
Aggregator (Safepay or PayFast) — decide by merchant onboarding ease when we reach T-019.
