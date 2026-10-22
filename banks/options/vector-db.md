# Options: Vector store / RAG
- Status: chosen (ADR-0001)
- Related FR: FR-6.3, FR-12.4

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes |
|---|---|---|---|---|---|---|---|
| pgvector | 4 | 5 | 5 | 5 | 4 | 23 | Same Postgres DB |
| Qdrant | 4 | 5 | 4 | 4 | 4 | 21 | |
| Pinecone | 4 | 4 | 2 | 4 | 3 | 17 | |
| Weaviate | 4 | 4 | 3 | 3 | 4 | 18 | |

## Recommendation
pgvector.
