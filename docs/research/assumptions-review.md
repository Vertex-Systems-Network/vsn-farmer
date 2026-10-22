# Assumptions Review (SRS §2.3)
| Assumption | Verdict | Note / fix |
|---|---|---|
| AI ko sirf zaroori authorised data | ✅ Strong | Backend-built context; good privacy design |
| Country/region/language/units configurable | ✅ Strong | Cheap to do from day 1, costly later |
| Diagnosis: pehle existing API, model baad ma | ✅ Correct | Plantix/Kindwise APIs; PK crop coverage (cotton leaf curl, wheat rust) test karna zaroori |
| Satellite/drone MVP ma nahi | ✅ Correct | But keep "field polygon" in schema for later (Farmdar/Sentinel NDVI) |
| Farmer ke paas smartphone + kabhi internet | ⚠️ Partly | Rural PK me smallholder smartphone/data use limited, often son/family operates phone; literacy low → **voice + WhatsApp should move earlier (MVP-lite)**, not Phase 5. PWA offline caching needed |
| Knowledge sources, weather, diagnosis, OTP, payment PK me available | ⚠️ Mostly | Weather/OTP/JazzCash/Easypaisa ok. **Approved Urdu agri knowledge is the biggest gap** — PARC, Punjab Agri Dept, AARI, provincial extension docs need licensing/permission + digitisation |
| Kam az kam 1 qualified expert | ⚠️ Weak | 1 expert = bottleneck + SLA risk. Need on-call rota, SLA (e.g. 24h), and auto "safe generic" reply while waiting |
| Subscription PKR 299–499 farmer se | ❌ Riskiest | Smallholders rarely pay for advice (Plantix, Telenor Khushaal Zamindar free/ad/telco funded). Plan B2B2C: input companies, banks/microfinance (crop loans), insurers, sugar mills/textile contracting, NGOs, govt. Keep farmer free tier strong |
| Web SaaS first | ⚠️ | Fine for Admin/Expert; for farmers WhatsApp bot gives distribution with zero install |
| Missing assumptions | — | Market prices (mandi rates), input authenticity (fake pesticides), dealer network trust, voice accent variety (Punjabi/Saraiki/Sindhi), data-consent law (PECA / PK data protection bill) |

