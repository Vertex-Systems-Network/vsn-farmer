# Roadmap (revised from SRS §9)

Changes vs SRS: WhatsApp + Urdu voice moved earlier (MVP-lite) because of low literacy/app-install friction; B2B revenue track added because farmer subscriptions are the riskiest assumption.

| Phase | Scope | SRS refs | Tasks |
|---|---|---|---|
| 0 Research & decisions | Open questions, systems bank, provider choices, farmer interviews | §10 Open Questions | T-001…T-003 |
| 1 Foundation | Monorepo, CI, DB schema, i18n/RTL, OTP login, roles | FR-1, FR-2, FR-15.1 | T-004…T-007 |
| 2 Farm core | Onboarding, farms, crops, activities, Crop Timeline, calendar | FR-3, FR-4, FR-5, FR-8.5 | T-008…T-010 |
| 3 AI advisory | RAG over approved sources, safety check, history, follow-up questions | FR-6 | T-011…T-013 |
| 4 Expert + Admin | Review queue, knowledge upload, crops/regions, AI settings, audit log | FR-11, FR-12 | T-014…T-015 |
| 5 Signals | Weather + alerts, photo diagnosis | FR-7, FR-8 | T-016…T-017 |
| 5b Reach (moved up) | WhatsApp channel + Urdu voice in/out | FR-8.4, FR-14 | T-018 |
| 6 Money | Plans, JazzCash/Easypaisa, B2B org dashboard pilot | FR-13 | T-019…T-020 |
| 7 Outcomes | Follow-up tracking, expenses, analytics | FR-9, FR-10 | T-021 |
