# ADR-0003: Platform surfaces & monorepo layout
- Status: accepted
- Date: 2026-10-22
- Options considered: banks/options/mobile-app.md

**Simple matlab:** Website, farmer app, mobile app, dashboards aur payments sab ek hi system ke hisse hain, ek hi jagah (repo) me banenge.

## Decision
```
apps/web      Next.js: website, /app (PWA), /expert, /admin, /org
apps/mobile   Expo React Native (Android first)
apps/api      FastAPI: auth, farm memory, advisory, billing, webhooks (WhatsApp, payments)
packages/     shared: types, API client, i18n strings (ur/en), UI tokens
```
Roles: farmer, expert, admin, org_admin (later). Billing has plans, subscriptions, usage limits, org seats.
## Consequences
One backend serves all surfaces; mobile reuses web logic; plans/limits enforced only in the API.
