# Open Questions — working defaults (T-001)

Product owner had no fixed answers, so these are **working defaults**. Status: `proposed` — change any of them anytime; the code must keep them configurable (Admin settings), not hard-coded.

| Question (SRS §10) | Default | Why |
|---|---|---|
| Crops first | Wheat, Cotton, Rice | Biggest crops in Punjab; rich public guidance; covers rabi + kharif |
| Region first | Punjab: Faisalabad, Multan, Sheikhupura | Wheat-cotton-rice belts; Urdu/Punjabi users; Punjab Agri Dept content |
| Knowledge sources | Punjab Agriculture Dept / AARI crop guides, PARC publications, Pakistan Meteorological Dept | Official and public; get written permission before launch |
| Diagnosis / weather / SMS / payments | Decide in T-003 via options bank (start: Open-Meteo, local SMS aggregator, JazzCash + Easypaisa) | Cheap, PK-available |
| Free plan AI limit | 20 questions / month | Enough to build habit; caps AI cost |
| Experts & SLA | 2 experts (1 agronomist, 1 plant protection), reply within 24h; urgent within 6h | 1 expert is a single point of failure |
| Field Agent at launch | No; add after first 100 active farmers | Keep MVP small |

## How to validate
Talk to 10–15 farmers + 1–2 agri officers in the chosen districts; update this table and mark `confirmed`.
