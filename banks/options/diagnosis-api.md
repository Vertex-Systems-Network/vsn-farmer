# Options: Photo diagnosis API
- Status: shortlisted (ADR-0002) — needs quotes
- Related FR: FR-7

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes / source |
|---|---|---|---|---|---|---|---|
| Plantix Crop Health API | 5 | 5 | 2 | 4 | 3 | 19 | 69 crops, 1,100+ pests/diseases, REST, 4–6 wk onboarding, price on request ([source](https://plantix.net/en/b2b-solutions/api-toolkit)) |
| Kindwise crop.health | 4 | 3 | 3 | 5 | 3 | 18 | Free test credits on request ([source](https://www.kindwise.com/post/crop-health-curing-crops-empowering-farmers)) |
| Multimodal LLM vision | 3 | 3 | 4 | 5 | 3 | 18 | Already have it via LLM adapter; less accurate |
| Own model | 4 | 5 | 2 | 1 | 3 | 15 | After we have labelled data |

## Recommendation
MVP: LLM vision as fallback + Kindwise trial; request Plantix quote. Choose after testing 200 labelled PK photos.
