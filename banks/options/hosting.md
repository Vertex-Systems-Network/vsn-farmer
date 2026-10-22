# Options: Hosting
- Status: chosen (ADR-0002)
- Related FR: NFR availability

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes |
|---|---|---|---|---|---|---|---|
| Vercel (web) + Railway/Render (api + Postgres) | 4 | 4 | 4 | 5 | 3 | 20 | Simplest for small team |
| AWS (Bahrain / Mumbai) | 5 | 4 | 3 | 2 | 4 | 18 | Later at scale |
| GCP | 4 | 4 | 3 | 3 | 4 | 18 | |
| Local PK DC | 3 | 5 | 3 | 1 | 2 | 14 | Only if data law requires |

## Recommendation
Managed platforms + Docker; move to AWS when needed.
