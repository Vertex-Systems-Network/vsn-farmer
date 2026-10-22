# AI Farmer Advisory SaaS — SRS (text copy)

> Source: original SRS PDF. Converted to text so every AI tool can read it. FR IDs are the canonical requirement references.

```text
AI Farmer Advisory SaaS
Software Requirements Specification (SRS)

1. Introduction
1.1 Maqsad
Yeh document AI Farmer Advisory ki requirements batata hai. Yeh ek web-based SaaS platform hai jo
farmers ko unki crop, location, weather, farm history aur crop stage ke mutabiq amli (practical)
farming guidance deta hai. Platform mobile browser par asani se chalega aur Urdu aur English dono
ma hoga.

1.2 Scope
    • Public website (landing page)
    • Farmer app (dashboard)
    • Expert panel: risky ya uncertain cases check karne ke liye
    • Admin dashboard: users, plans, knowledge aur settings sambhalne ke liye
Pehle release ma Pakistan ke chuninda farmers aur crops hon ge. Baad ma dusri crops, regional
languages aur dusre mulk shamil honge.

1.3 Chand Alfaz
 Lafz                  Matlab
 SaaS                  Website ke zariye subscription par istemal hone wala software
 PWA                   Aisi website jo phone ki home screen par app ki tarah install ho sakti hai
 RAG                   AI pehle approved sources se information nikalta hai, phir jawab likhta hai
 Farm Memory           Farmer ka saved farm, crop aur activity data jo advice ko personal banata hai
 Crop Timeline         Ek crop ki poori history: kaam, masail, photos, advice aur result
 Escalation            Risky ya uncertain case Expert ko bhejna
 MVP                   Pehla release (minimum viable product)



2. Overall Description
2.1 System ka Structure
 Hissa                 Tafseel
 Frontend              Next.js + TypeScript. Public website, Farmer, Expert aur Admin screens. Mobile-
                       first, PWA.
 Backend               Python + FastAPI. Login, permissions, farm data, AI, safety check, alerts, billing.
 Database              PostgreSQL
 Bahar ki services     OTP/login, AI model (LLM) aur RAG, photo diagnosis API, weather API, photo
                       storage, SMS/WhatsApp, payment gateway


Website ke hisse: yoursite.com (public), /app (Farmer), /expert (Expert), /admin (Admin).
2.2 Users (Roles)
 Role                 Kaun hai                      Kaam
 Farmer               Asli user                     App use karta hai, sawal poochta hai, farm ka record
                                                    rakhta hai
 Expert               Agriculture expert            Mushkil ya risky sawalon ke jawab check karta hai
 Admin                Aap aur aap ki team           Poora system chalata hai, knowledge bhi sambhalta hai


Baad ke roles (MVP ma nahi): Support Agent, Field Agent, Organization account.

2.3 Pabandiyan aur Assumptions
     •    AI ko farmer ke private records ka unrestricted access nahi hoga. Backend sirf zaroori
          authorised data AI ko dega.
     •    Country, region, language, crop variety aur units configurable honge.
     •    Photo diagnosis ke liye pehle maujooda API test hogi, apna model baad ma.
     •    Satellite aur drone features pehle release ma nahi.
     •    Farmers ke paas smartphone aur kabhi kabhi internet hai.
     •    Approved knowledge sources, weather aur diagnosis API, OTP aur payment providers
          Pakistan ma dastiyab hain.
     •    Kam az kam ek qualified expert cases review ke liye maujood hai.

3. User Journey aur Workflow
 Step       Stage                    Kya hota hai
 1          Landing page             Visitor features aur pricing dekhta hai, Sign Up karta hai
 2          Sign up                  Mobile number, OTP, naam, language
 3          Onboarding               Language, farm add, crop add. Calendar khud ban jata hai.
 4          Farmer Dashboard         Roz ka istemal: Ask AI, calendar, alerts, records
 5          Admin Dashboard          Users, plans, experts, knowledge, rules, reports
 6          Expert Panel             Flagged cases check karke jawab bhejna


Advisory ka Flow
     • Farmer sawal bhejta hai (text, voice ya photo).
     • Backend login aur permission check karta hai.
     • Farm Memory se crop, stage, location aur history nikalta hai. Info kam ho to AI sawal
       poochta hai.
   • Approved knowledge, weather aur (photo ho to) diagnosis API se info li jati hai.
   • AI sources ke saath jawab ka draft banata hai.
   • Safety check: safe jawab farmer ko jata hai, risky ya uncertain jawab Expert ke paas jata hai.
   • Jawab Crop Timeline aur Advisory History ma save hota hai.
   • Kuch din baad follow-up: farmer batata hai ke fark pada ya nahi.
Poora diagram aakhir ma Appendix A ma hai.
4. Functional Requirements
4.1 Landing Page
 ID        Requirement                                                                           Priority
 FR-1.1    Navbar: Logo, Features, How It Works, Pricing, Login, Sign Up.                        MVP
 FR-1.2    Hero section: heading, chhoti line aur "Free shuru karen" button.                     MVP
 FR-1.3    Farmer ke masail, How It Works (3 steps), Features, Supported Crops, Pricing aur      MVP
           FAQ.
 FR-1.4    Contact aur WhatsApp button. Footer ma About, Privacy Policy, Terms.                  MVP
 FR-1.5    Urdu/English aur mobile screen par theek chalna.                                      MVP


4.2 Sign up aur Login
 ID        Requirement                                                                           Priority
 FR-2.1    Mobile number se registration aur OTP verification.                                   MVP
 FR-2.2    Naam aur language (Urdu/English) chunna.                                              MVP
 FR-2.3    Dobara login mobile number aur OTP se.                                                MVP
 FR-2.4    OTP attempts aur resend par limit.                                                    MVP
 FR-2.5    Login ke baad user ko uske role ka sahi hissa dikhna (Farmer, Expert ya Admin).       MVP


4.3 Onboarding
 ID        Requirement                                                                           Priority
 FR-3.1    Chaar se kam screens: language, farm (naam, location, land area), crop (crop,         MVP
           variety, sowing date).
 FR-3.2    Setup ke baad system crop calendar khud banaye aur Farmer Dashboard khole.            MVP


4.4 Farmer Dashboard
 ID        Requirement                                                                           Priority
 FR-4.1    Dashboard par: farm/crop selector, current crop aur stage, weather alerts, aane       MVP
           wale kaam, recent advisory, "AI se poochen" button.
 FR-4.2    Quick actions: irrigation, fertilizer ya symptoms record karna.                       MVP
 FR-4.3    Menu: Dashboard, My Farms, My Crops, Ask AI, Crop Diagnosis, Crop Calendar,           MVP
           Weather & Alerts, Farm Expenses, Crop Timeline, Advisory History, Subscription,
           Profile & Settings, Help.


4.5 Farm, Crop aur Farm Memory
 ID        Requirement                                                                           Priority
 FR-5.1    Farmer kai farms add, edit aur archive kar sake (naam, location, land area, plots).   MVP
 FR-5.2    Crop record: crop, variety, sowing date, growth stage, expected harvest.              MVP
 FR-5.3    Activities record: irrigation, fertilizer, spray, notes.                              MVP
 FR-5.4    Crop Timeline sab kuch date ke hisab se dikhaye: activities, masail, photos, AI       MVP
           advice, harvest aur yield.
 ID        Requirement                                                                           Priority
 FR-5.5    AI saved details khud use kare, farmer ko dobara na likhni paren.                     MVP
 FR-5.6    Crops aur varieties ki list Admin configure kar sake.                                 MVP


4.6 AI Advisory (Ask AI)
 ID        Requirement                                                                           Priority
 FR-6.1    Farmer farm aur crop chun kar text, voice ya photo se sawal bheje.                    MVP
 FR-6.2    Info kam ho to AI follow-up sawal poochay.                                            MVP
 FR-6.3    Jawab approved sources (RAG) par mabni ho.                                            MVP
 FR-6.4    Jawab ka format: masle ki asaan wazahat, mumkin wajohat, agle qadam,                  MVP
           source/reference aur zaroorat par expert ki salah.
 FR-6.5    Source ki last-updated date aur uncertainty saaf dikhayi jaye.                        MVP
 FR-6.6    Jawab farmer ki language ma aur asaan alfaz ma ho.                                    MVP
 FR-6.7    Safety check: dawai ki dose jaise high-risk mashwaron ma approved local               MVP
           guidance aur product label ka khayal.
 FR-6.8    Risky ya uncertain case Expert queue ma jaye.                                         MVP
 FR-6.9    Har jawab Advisory History aur Crop Timeline ma save ho.                              MVP
 FR-6.10   Plan ke mutabiq sawalon ki limit. Jawab ko rate karna aur galat jawab report          Phase 2
           karna.


4.7 Photo Diagnosis
 ID        Requirement                                                                           Priority
 FR-7.1    Farmer pattay, tane ya phal ki photo upload kare. System photo ki quality check       MVP
           kare.
 FR-7.2    Mumkin bimari, keera ya kami batai jaye ("probable result" ke taur par) aur           MVP
           zaroorat par aur sawal poochay jayen.
 FR-7.3    Uncertain diagnosis par expert review suggest ho.                                     MVP
 FR-7.4    Diagnosis photo ke saath Crop Timeline ma save ho taa-ke tabdeeli track ho.           MVP


4.8 Weather, Alerts aur Calendar
 ID        Requirement                                                                           Priority
 FR-8.1    Farm ki location ka current weather aur forecast.                                     MVP
 FR-8.2    Alerts weather, crop stage aur location par mabni, jaise barish se pehle irrigation   MVP
           review, stage par inspection, weather risk ka ehtiyati alert.
 FR-8.3    Har weather event par khud ba khud treatment recommend nahi hogi.                     MVP
 FR-8.4    Alerts app ma. SMS/WhatsApp ka option baad ma. Farmer notification                    MVP /
           preferences set kare.                                                                 Phase 2
 FR-8.5    Crop Calendar: sowing, inspection, irrigation, fertilizer, pest/disease monitoring,   MVP
           harvest preparation. Crop, location aur sowing date ke mutabiq. Farmer kaam
           "complete" mark kare.
4.9 Follow-up aur Result Tracking
 ID        Requirement                                                                             Priority
 FR-9.1    Advice ke kuch din baad follow-up request.                                              Phase 2
 FR-9.2    Farmer record kare: steps follow kiye? Symptoms ma farq? Nayi problem? Expert           Phase 2
           se baat hui? Final crop result?
 FR-9.3    Jawab Timeline ma save ho aur Admin reports ma use ho.                                  Phase 2


4.10 Farm Expenses
 ID        Requirement                                                                             Priority
 FR-10.1   Kharcha record karna: seeds, fertilizer, crop-protection, irrigation, labour,           Phase 2
           machinery, harvesting. Saath crop ki sale aur income.
 FR-10.2   System total kharcha, andaza income aur profit/loss nikale.                             Phase 2


4.11 Expert Panel
 ID        Requirement                                                                             Priority
 FR-11.1   Review Queue: flagged cases, urgent upar.                                               MVP
 FR-11.2   Case Detail: sawal, photos, farm history, AI draft aur sources.                         MVP
 FR-11.3   Actions: Approve, Edit & Send, Reject, Farmer se sawal.                                 MVP
 FR-11.4   Jawab tayyar hone par farmer ko notification. Expert sirf apne assigned cases           MVP
           dekhe.
 FR-11.5   Completed Cases, AI ko feedback, profile aur availability.                              Phase 2


4.12 Admin Dashboard
 ID        Requirement                                                                             Priority
 FR-12.1   Overview: total aur active farmers, naye signups, AI sawal, AI cost per advisory.       MVP
 FR-12.2   Users: list, search, account band/chalu, roles.                                         MVP
 FR-12.3   Experts: add/remove, crop aur region dena, workload.                                    MVP
 FR-12.4   Knowledge Sources: guides aur documents upload, approve aur archive (naam,              MVP
           date, crop, region). AI sirf approved sources use kare.
 FR-12.5   Crop Calendar aur Alert Rules: kaun sa alert kab jaye.                                  MVP
 FR-12.6   Crops aur Regions: crops, varieties, provinces, districts, languages, units.            MVP
 FR-12.7   AI Settings: model, daily limits, safety rules, API keys, features on/off. AI ko test   MVP
           karna aur dekhna ke konse sources use hue.
 FR-12.8   Audit Log: kis ne kya change kiya.                                                      MVP
 FR-12.9   Plans & Payments, Advisory Monitoring, Announcements aur Reports.                       Phase 2


4.13 Plans aur Payment
 ID        Requirement                                                                             Priority
 FR-13.1   Free plan: basic profile, limited AI sawal, basic calendar, limited history.            MVP
 ID             Requirement                                                                          Priority
 FR-13.2        Premium: zyada sawal, kai farms/crops, advanced timeline, personal reminders,        Phase 2
                poori history, expense reports.
 FR-13.3        Limit khatam hone par Premium ka option. Payment (JazzCash, Easypaisa ya             Phase 2
                card) ke baad plan foran active ho aur Admin ko nazar aaye.
 FR-13.4        Premium ki tajwez shuda qeemat taqreeban PKR 299 se 499 mahina hai. Yeh              Phase 2
                verified market rate nahi hai. Farmer interviews aur paid-user testing ke baad tay
                hogi.


4.14 Urdu Voice
 ID             Requirement                                                                          Priority
 FR-14.1        Urdu ma voice sawal (jahan supported ho) aur asaan Urdu jawab ke saath               Phase 2
                important baton ka khulasa.
 FR-14.2        Regional languages ki support.                                                       Baad ma


4.15 Profile aur Settings
 ID             Requirement                                                                          Priority
 FR-15.1        Profile, language, farm locations aur notification preferences badalna.              MVP
 FR-15.2        Account security, data export aur account delete. Help aur support contact.          MVP /
                                                                                                     Phase 2



5. Interfaces
      •    Mobile-first, responsive. Bara text, bare buttons aur asaan alfaz.
      •    Urdu (right-to-left) aur English (left-to-right) layout.
      •    Expert aur Admin screens zyada tar computer ke liye.
      •    Sab traffic HTTPS par. Frontend aur backend REST API se baat karen.
      •    Bahar ki services: OTP, AI model, weather, diagnosis, photo storage, SMS/WhatsApp,
           payment.

6. Non-Functional Requirements
Numbers tajwez shuda hain, testing ke baad confirm honge.
 Pehlu                         Zaroorat
 Speed                         Page taqreeban 3 second ma load ho (3G/4G par). AI jawab taqreeban 10 second
                               ma shuru ho.
 Availability                  Launch ke baad kam az kam 99%.
 Kam internet                  App halki ho, photos upload se pehle compress hon, kharab connection par saaf
                               message aur retry.
 Security                      Safe login, HTTPS, hassas data encrypted, aam attacks se hifazat.
 Access control                Farmer sirf apna data dekhe. Expert sirf assigned cases. Admin ke kaam log hon.
 Privacy                       Private photos aur farm data mehfooz. Farmer data export aur delete kar sake.
 AI safety                     Approved sources, references, uncertainty ka izhar aur risky cases ka escalation.
 Usability                     Naya farmer bina training ke chand minute ma onboarding mukammal kar sake.
 Pehlu                      Zaroorat
 Localization               Poori Urdu/English support. Country, language aur units configurable.
 Compatibility              Chrome, Edge, Safari, Firefox aur kam qeemat Android phones.
 Cost                       AI cost per advisory napi jaye. Limits aur sahi model se cost control ma rahe.
 Backup                     Database ka regular backup aur restore test.



7. Database Tables
 Table                              Maqsad
 users                              Farmer, Expert, Admin accounts aur profiles
 farms / fields                     Farm ki location, area aur plots
 crop_cycles                        Crop, sowing date, growth stage
 farm_events                        Irrigation, fertilizer aur dusre kaam
 advisory_cases /                   Masail, status aur AI baat-cheet
 advisory_messages
 crop_images                        Photos aur diagnosis
 knowledge_sources                  Approved guidance aur citations
 alerts                             Weather aur crop-stage notifications
 expenses / harvest_records         Kharcha, yield aur sales
 follow_up_records                  Advice ke natayej


Is ke ilawa chahiye: subscriptions aur payments, expert assignments, notifications aur audit logs.

8. Roles aur Permissions
 Kaam                                                 Farmer                Expert           Admin
 Apni farms, crops aur records manage karna           Han                   Nahi             Nahi
 Ask AI aur apni advisory history                     Han                   Nahi             Nahi
 Assigned flagged cases review karna aur jawab        Nahi                  Han              Nahi
 bhejna
 Users, plans aur payments manage karna               Nahi                  Nahi             Han
 Knowledge sources, alert rules aur AI settings       Nahi                  Nahi             Han
 Reports aur audit log dekhna                         Nahi                  Nahi             Han



9. MVP aur Banane ki Tarteeb
MVP ma kya hoga
    •     Landing page, sign up, onboarding
    •     Farm aur crop management, Farm Memory aur Crop Timeline
    •     Source-supported AI advisory aur advisory history
    •     Basic weather, reminders aur crop calendar
    •     Basic photo diagnosis (agar API tested ho)
    •     Expert panel aur Admin core
    •      Urdu/English mobile-friendly interface

Tarteeb
 Phase             Kaam
 Phase 1           Landing page, sign up, onboarding, farm aur crop add
 Phase 2           Farmer Dashboard, AI advisory, Crop Timeline, history
 Phase 3           Expert panel, Admin dashboard, knowledge upload
 Phase 4           Weather alerts, photo diagnosis, plans aur payments
 Phase 5           Expenses, follow-up analytics, voice, WhatsApp, Android app


Farmer Dashboard pehle banta hai kyun ke Admin aur Expert ka kaam usi ke data par chalta hai.

10. Success Metrics aur Risks
Metrics
    •      Weekly active farmers aur repeat usage
    •      Farm profile mukammal karne wale users
    •      Follow-up completion aur farmer retention
    •      Expert review ma jawab ki quality aur high-risk cases ka sahi escalation
    •      AI cost per advisory aur free se paid conversion

Risks
 Risk                              Hal
 Galat crop advice                 Approved sources, expert review, safety checks
 Farmers ka kam istemal            Asaan Urdu, mobile-friendly design, local feedback, WhatsApp aur Field
                                   Agent ka sochna
 AI ka zyada kharcha               Usage limits aur monitoring, munasib model
 Galat photo diagnosis             Probable result dikhana, aur sawal, uncertain cases escalate
 Privacy                           Safe login, restricted access, photos ki hifazat
 Provider par inhisar              AI, weather aur diagnosis providers backend ke peeche badle ja saken



Open Questions
    •      Pehle kaun si crops aur kaun se provinces/districts?
    •      Kaun se knowledge sources approved aur istemal ke liye jaiz hain?
    •      Kaun se diagnosis, weather, SMS/WhatsApp aur payment providers?
    •      Free plan ma mahine ke kitne AI sawal?
    •      Kitne experts hon ge aur escalated case ka jawab kitne waqt ma?
    •      Kya launch par Field Agent role chahiye?
Appendix A. Working Flow Diagram




Gray: farmer ke steps. Purple: system ke andar ke steps. Coral: Expert.
```
