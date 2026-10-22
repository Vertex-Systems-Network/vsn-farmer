# ADR-0001: Base stack
- Status: accepted
- Date: 2026-10-22
- Options considered: banks/options/hosting.md, banks/options/vector-db.md
## Context
SRS §2.1 fixes Next.js + TypeScript, FastAPI, PostgreSQL.
## Decision
Keep SRS stack. Monorepo (`apps/web`, `apps/api`, `packages/`). pgvector for RAG to avoid a second DB at MVP.
## Consequences
One database to back up; can move to dedicated vector DB later behind the retriever adapter.
