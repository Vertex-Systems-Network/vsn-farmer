# AGENTS.md — VSN Farmer (AI Farmer Advisory)

> Single source of truth for ALL AI coding tools (Claude Code, Cursor, Copilot, Gemini, Codex, Windsurf…).
> Tool-specific files (CLAUDE.md, GEMINI.md, .cursor/rules, .github/copilot-instructions.md, .windsurfrules) only point here.
> Owner is non-technical: make technical decisions yourself (record them in banks + ADRs) and explain results in simple Roman Urdu. Owner tasks: `docs/OWNER-GUIDE.md`.

## What we are building
Urdu/English, mobile-first AI advisory for Pakistani farmers: Farm Memory + Crop Timeline, RAG answers from approved sources,
photo diagnosis, weather alerts, crop calendar, Expert review of risky answers, Admin panel. Full spec: `docs/srs/AI_Farmer_Advisory_SRS.md`.

## Start here (every session, every tool)
1. Read this file.
2. Read `tasks/CURRENT.md` → it says what is in progress and what to pick next.
3. Open the task card in `tasks/BACKLOG.md` (goal, FR refs, done-criteria).
4. Before choosing any tech/vendor/design: check `banks/options-bank.md`. Before designing a feature: check `banks/systems-bank.md` for how others do it.
5. If a decision is needed: add/score options in `banks/options/<topic>.md`, then write an ADR in `docs/decisions/`.
6. Implement. Keep changes inside the task scope.
7. Update `tasks/CURRENT.md`, the task status in `BACKLOG.md`, and any bank entry status. Commit with the task ID: `T-004: scaffold monorepo`.

## Where things live
| Path | Purpose |
|---|---|
| `docs/srs/` | Requirements (FR-x.y IDs) |
| `docs/research/` | Assumptions review, market comparison |
| `docs/plan/` | Roadmap, architecture |
| `docs/decisions/` | ADRs (numbered, never edited after accepted — supersede instead) |
| `banks/options/` | Options Bank: researched choices per decision point, scored |
| `banks/systems/` | Systems Bank: studied competitor/reference systems + "improve on it" ideas |
| `tasks/` | Backlog, current work, task template |
| `apps/web` (planned) | Next.js + TypeScript PWA (public, /app, /expert, /admin) |
| `apps/api` (planned) | Python FastAPI backend |

## Rules
- Requirements trace: reference FR IDs in tasks, PRs and code comments where useful.
- AI safety: answers only from approved sources, show source + date + uncertainty, escalate risky cases (FR-6.3–6.8). Never hard-code pesticide doses.
- Privacy: the LLM only receives backend-selected authorised farm data.
- Providers (LLM, weather, diagnosis, OTP, payments, messaging) always behind an adapter interface — swappable.
- Everything user-facing must be i18n (Urdu RTL + English); no hard-coded strings.
- Config over code for country, region, crops, units, languages.
- Do not mark research facts as certain: use `status: needs-verification` until sourced.
