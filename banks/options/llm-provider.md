# Options: LLM provider
- Status: chosen (ADR-0002)
- Related FR: FR-6, FR-12.7
- Decision ADR: docs/decisions/0002-ai-providers.md

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes / source |
|---|---|---|---|---|---|---|---|
| Anthropic Claude | 5 | 4 | 3 | 5 | 4 | 21 | Strong reasoning, safety, good Urdu; smaller model for cheap routing |
| OpenAI GPT | 5 | 4 | 3 | 5 | 4 | 21 | Used by Digital Green FarmerChat (GPT-4o mini) |
| Google Gemini | 4 | 4 | 4 | 5 | 4 | 21 | Good multimodal + cheap |
| Open model self-hosted | 3 | 3 | 4 | 2 | 3 | 15 | Needs GPU ops; later |
| Agri-tuned model | 3 | 2 | 4 | 3 | 2 | 14 | India-focused |

## Recommendation
Use an adapter so any of the top 3 works. Start with Claude (main answers) + a small cheap model for classification; run the Urdu eval set (T-013) on all three before launch and switch if another wins.
