# Options: OTP / SMS
- Status: chosen (ADR-0002)
- Related FR: FR-2

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes |
|---|---|---|---|---|---|---|---|
| Local PK SMS aggregator | 4 | 5 | 5 | 3 | 3 | 20 | Cheapest per SMS; pick vendor at T-007 |
| Twilio Verify | 4 | 4 | 2 | 5 | 4 | 19 | Easy; costly per SMS to PK |
| Firebase phone auth | 4 | 4 | 4 | 4 | 3 | 19 | |
| WhatsApp OTP | 3 | 4 | 4 | 3 | 3 | 17 | Later |

## Recommendation
Twilio Verify for development (fast), local aggregator before launch — both behind the OTP adapter.
