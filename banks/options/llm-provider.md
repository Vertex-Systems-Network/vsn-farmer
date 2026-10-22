# Options: LLM provider
- Status: needs-verification
- Related FR: FR-6, FR-12.7
- Decision ADR: —

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes / source |
|---|---|---|---|---|---|---|---|
| Anthropic Claude | | | | | | | |
| OpenAI GPT | | | | | | | |
| Google Gemini | | | | | | | |
| Open model self-hosted (Llama/Qwen) | | | | | | | |
| Agri-tuned model (e.g. KissanAI Dhenu) | | | | | | | |

## Recommendation
Start with a hosted frontier model for quality + a cheaper model for routing/simple answers; benchmark Urdu quality on our eval set.
