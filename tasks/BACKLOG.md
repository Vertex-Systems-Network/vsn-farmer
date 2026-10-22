# Backlog

Format: see `_template.md`. Pick in order unless CURRENT.md says otherwise.

### T-001: Resolve SRS open questions
- Status: doing (defaults proposed; farmer validation by owner)
- Phase: 0
- FR refs: §10 Open Questions
- Banks to read: revenue-model
- Done when: Answers recorded in docs/research/open-questions.md (crops, districts, sources, providers, free limit, experts/SLA, field agent)

### T-002: Verify & extend Systems Bank
- Status: done
- Phase: 0
- FR refs: —
- Banks to read: systems/*
- Done when: Each system has sources + dates; status updated; new PK competitors added

### T-003: Choose providers
- Status: done
- Phase: 0
- FR refs: FR-6, FR-7, FR-8, FR-2, FR-13
- Banks to read: llm-provider, diagnosis-api, weather-api, otp-sms, payments, vector-db
- Done when: Options scored; ADRs written

### T-004: Scaffold monorepo + CI
- Status: todo
- Phase: 1
- FR refs: §2.1
- Banks to read: hosting
- Done when: apps/web, apps/api run locally; lint/test in CI

### T-005: DB schema + migrations
- Status: todo
- Phase: 1
- FR refs: §7
- Banks to read: —
- Done when: All §7 tables + subscriptions, assignments, notifications, audit_logs

### T-006: i18n Urdu RTL / English
- Status: todo
- Phase: 1
- FR refs: FR-1.5, §5
- Banks to read: —
- Done when: Locale switch, RTL layout, no hard-coded strings

### T-007: OTP login + roles
- Status: todo
- Phase: 1
- FR refs: FR-2.1–2.5, §8
- Banks to read: otp-sms
- Done when: Login works, rate limited, role routing /app /expert /admin

### T-008: Landing page
- Status: todo
- Phase: 1
- FR refs: FR-1.1–1.4
- Banks to read: —
- Done when: Mobile-first page in both languages

### T-009: Onboarding + farms/crops
- Status: todo
- Phase: 2
- FR refs: FR-3, FR-5.1–5.3, FR-5.6
- Banks to read: —
- Done when: <4 screens, calendar generated

### T-010: Dashboard, Timeline, Calendar
- Status: todo
- Phase: 2
- FR refs: FR-4, FR-5.4, FR-8.5
- Banks to read: —
- Done when: Timeline shows all events by date

### T-011: Knowledge ingestion + RAG
- Status: todo
- Phase: 3
- FR refs: FR-6.3, FR-12.4
- Banks to read: vector-db, llm-provider
- Done when: Approved docs searchable with citations

### T-012: Advisory pipeline + safety check
- Status: todo
- Phase: 3
- FR refs: FR-6.1–6.9, FR-5.5
- Banks to read: llm-provider
- Done when: Structured answer, sources+date, escalation rules, eval set passing

### T-013: AI eval set
- Status: todo
- Phase: 3
- FR refs: §6 AI safety
- Banks to read: —
- Done when: ≥100 expert-reviewed Q&A, run in CI on prompt/model changes

### T-014: Expert panel
- Status: todo
- Phase: 4
- FR refs: FR-11.1–11.4
- Banks to read: —
- Done when: Queue, case detail, approve/edit/reject/ask

### T-015: Admin core
- Status: todo
- Phase: 4
- FR refs: FR-12.1–12.8
- Banks to read: —
- Done when: Users, experts, knowledge, crops/regions, AI settings, audit log

### T-016: Weather + alert rules
- Status: todo
- Phase: 5
- FR refs: FR-8.1–8.4
- Banks to read: weather-api
- Done when: Alerts per stage/location; no auto treatment

### T-017: Photo diagnosis
- Status: todo
- Phase: 5
- FR refs: FR-7
- Banks to read: diagnosis-api
- Done when: Quality check, probable result, escalation, timeline save

### T-018: WhatsApp + Urdu voice
- Status: todo
- Phase: 5b
- FR refs: FR-8.4, FR-14
- Banks to read: whatsapp-bsp, voice-stt-tts
- Done when: Ask via WhatsApp voice note, Urdu voice/summary reply

### T-019: Plans + payments
- Status: todo
- Phase: 6
- FR refs: FR-13, FR-6.10
- Banks to read: payments, revenue-model
- Done when: Limits, upgrade, JazzCash/Easypaisa

### T-020: B2B organization pilot
- Status: todo
- Phase: 6
- FR refs: §2.2 later roles
- Banks to read: revenue-model
- Done when: One partner dashboard with consented aggregate data

### T-021: Follow-up, expenses, analytics
- Status: todo
- Phase: 7
- FR refs: FR-9, FR-10
- Banks to read: —
- Done when: Outcomes stored and in admin reports

### T-022: Mobile app (Expo, Android first)
- Status: todo
- Phase: 6c
- FR refs: §5, NFR compatibility
- Banks to read: mobile-app
- Done when: Login, dashboard, Ask AI, timeline work on cheap Android; Play Store internal test

