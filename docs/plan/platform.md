# Platform overview — sirf app nahi, poora platform

**Simple matlab:** VSN Farmer ek platform hai jis ke kai hisse hain, sab ek hi backend aur ek hi database se chalte hain.

| Hissa | Kis ke liye | Kahan | Code (planned) |
|---|---|---|---|
| Public website | Visitors | yoursite.com: features, pricing, sign up | `apps/web` |
| Farmer web app (PWA) | Farmers | yoursite.com/app | `apps/web` |
| Mobile app (Android, phir iOS) | Farmers | Play Store / App Store | `apps/mobile` |
| WhatsApp + voice channel | Farmers (kam parhe likhe) | WhatsApp number | `apps/api` (webhook) |
| Expert dashboard | Experts | /expert | `apps/web` |
| Admin dashboard | Aap ki team | /admin | `apps/web` |
| Partner/Organization dashboard (B2B) | Companies, banks, NGOs | /org | `apps/web` (later) |
| Plans & payments | Sab | Free / Premium / Organization plans; JazzCash, Easypaisa, card | `apps/api` billing |
| Backend API | Sab ke peeche | api.yoursite.com | `apps/api` |

## Plans (draft — FR-13)
| Plan | Kis ke liye | Kya milta hai |
|---|---|---|
| Free | Farmer | 20 AI sawal/mahina, 1 farm, basic calendar |
| Premium (PKR 299–499, test hoga) | Farmer | Zyada sawal, kai farms, poori history, expense reports, expert priority |
| Organization (B2B) | Companies, banks, NGOs | Apne farmers ke liye seats, dashboard, reports (consent ke saath) |

## Build order
Website + farmer web app pehle (sab se tez), phir Expert/Admin dashboards, phir mobile app (zyada code web ke saath share), phir B2B dashboard. Details: `roadmap.md`.
