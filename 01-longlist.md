# 01 — Longlist

**Run date 2026-09-03.** Stage 1 of the brief: breadth over polish. One-line thesis + at least one demand signal each.

**Evidence tiers:** **[S]** = appeared in a web-search result (real URL, content summarised by the search tool). **[I]** = inference, not evidence. **[SELF-REPORTED]** = founder-claimed, unverifiable. **NO EVIDENCE FOUND** = looked, found nothing.
**Environment caveat:** page fetching was blocked this session (see `00-brief-review.md` §5), so no claim below is verified by my own reading of the source page. Re-check before acting.

---

## A. "Someone is paying a human to do this manually"
*The brief's highest-priority family. Ranked by strength of repetition evidence.*

**1. Templated PDF → spreadsheet extraction, priced below the incumbents**
Thesis: sub-$25/mo document parser for small firms, undercutting Docparser/Nanonets on price and setup time.
Signal: ≥5 distinct dated Upwork/Freelancer postings from different buyers for "PDF to Excel data entry", Apr–Aug 2026 [S]. Competitors Docparser $39/mo (100 docs), Parseur $0.33/page, Nanonets from $499/mo [S].

**2. B2B lead list building**
Thesis: automated prospect list assembly for a narrow vertical.
Signal: 6 postings/gigs across Upwork, PeoplePerHour, OnlineJobs.ph; median lead-gen rate $20/hr, gigs at $40/150 leads [S]. **Red flag: Apollo ($49–149/user/mo), Clay ($185–495/mo), Cognism (~$15k/yr) — crowded and well funded** [S].

**3. Local SEO citation building / NAP consistency monitoring**
Thesis: automated directory submission + drift detection, undercutting Whitespark.
Signal: 5 different Fiverr sellers at $5–$15 per batch plus Upwork job postings [S]. Whitespark charges $79/mo for 30 citations or $549 one-time for 255; BrightLocal $39–449/mo; Yext ~$199/yr/location [S].

**4. E-commerce multichannel product listing sync**
Thesis: Shopify→Amazon/eBay field mapping for small sellers.
Signal: 5 Upwork VA postings for exactly this [S]. **Red flag: core mechanism already commoditised** — Listing Mirror from $69/mo, Sellbrite $29–679/mo [S].

**5. Scanned invoice → bookkeeping ledger entry**
Thesis: AP data entry automation for bookkeepers.
Signal: Upwork showed 145 open invoice-processing jobs at time of search; one explicitly "Ongoing" [S]. **Red flag: Hubdoc $12/mo/client and often bundled free with Xero; Dext ~$25–37.50/mo** [S]. Entrenched and nearly free.

**6. Google Business Profile upkeep + review response for small multi-location operators**
Thesis: cheap GBP posting/review-response tool well under agency pricing.
Signal: recurring monthly-retainer postings on Upwork [S]. Incumbents are agency-priced — Vendasta from ~$79/mo, BirdEye $299–399/mo/location, Podium ~$399/mo [S]. **Genuine price gap below $79.**

**7. Website ADA/WCAG accessibility audit reporting**
Thesis: scan-plus-human-review audit reports, not a remediation widget.
Signal: 4 Upwork postings incl. a dedicated IAAP-certified talent category [S]. accessiBe $59–479/mo and UserWay $49–329/mo are *widgets*, which critics say don't achieve legal compliance — which is why manual auditors still get hired [I]. **Weak: audits skew one-off, not subscription.**

**8. Real-estate skip tracing + CRM data entry** — **REJECT**
Signal: core task already commoditised to **$0.07–0.20 per record** by BatchData, REISkip; REISift $49/mo [S]. Space is full of software, not empty of it.

---

## B. Regulation-driven forced demand

**9. UK Companies House identity-verification portfolio tracker for accountants**
Thesis: dashboard tracking director/PSC verification status and chase emails across an accountancy practice's client book. **Never touches ID documents.**
Signal: **hard deadline — 12-month transition ends 18 Nov 2026**; non-compliance is an ongoing criminal offence [S] changestoukcompanylaw.campaign.gov.uk. Competitors ACSPverify, Verify 365, Inform Direct [S].

**10. Australia Payday Super reconciliation + 5-year shortfall audit**
Thesis: three-way match (STP vs SuperStream vs bank) and historical unpaid-super exposure audit for bookkeepers.
Signal: **mandatory since 1 July 2026**; 7-business-day deposit rule, penalty 60% of shortfall; **the ATO's own clearing house closed 1 July 2026** forcing employers onto third parties [S]. Existing small vendors: SmallBiz Super Check, FairWork Mate [S].

**11. UK Making Tax Digital ITSA companion tool** — **REJECT**
Signal: real phase-in (>£50k live Apr 2026, >£30k Apr 2027) but **40+ HMRC-recognised products already exist** and the big suites bundle it [S].

**12. Martyn's Law premises assessment & staff-training log** — **WEAK**
Signal: Royal Assent 3 Apr 2025, statutory guidance 15 Apr 2026 [S], but **DEADLINE UNCONFIRMED** — no official commencement order found. Martyn's Law Software already at £19/mo; a free competitor scorecard exists [S].

**13. Canada CBCA beneficial-ownership register builder** — **NARROW**
Signal: mandatory since 22 Jan 2024, penalties to $200k and/or 6 months imprisonment [S]. MinuteKeep already occupies the identical niche; **federal incorporations only**, so market size capped and unverified [S].

**14. EU AI Act Article 50 transparency kit** — **REJECT**
Signal: live 2 Aug 2026 [S], but compliance cost is only **€500–1,500 one-off** and **Legalithm is free through ~April 2028** [S]. Too small, too one-off, free incumbent.

**15–20. Rejected regulation plays** (recorded so the graveyard is visible):
AU Privacy Act Tranche 2 — **no bill introduced, no legislated commencement** [S]. UK Packaging EPR — deadlines passed, consolidated. France/Germany B2B e-invoicing — dominated by registered PDP accounting platforms [S]. **NZ Climate-Related Disclosures — regime shrinking, threshold rising $60M→$1B** [S] Bell Gully. NZ/AU Peppol — mandate only bites suppliers >NZD 33M from 2027 [S]. NZ director address privacy filing — one-off, not SaaS-shaped [S].

---

## C. Data products, APIs and rebuild plays

**21. NZ open-banking cashflow / GST forecast tool for sole traders**
Thesis: small cashflow tool on the new regulated Account Information APIs via Akahu.
Signal: regulated open banking live **1 Dec 2025**; Akahu charges $0.15/payment request and serves 130+ orgs [S]. **Platform risk HIGH: Payments NZ API Centre ceases operating end of Sept 2026** [S].

**22. Self-serve HS-code / import-duty classification API**
Thesis: undercut Avalara's enterprise-only motion for small importers.
Signal: **Avalara publishes no pricing — custom quote only** [S] developer.avalara.com; Tariffs API charges $199/mo for 100k calls [S]. Four players already.

**23. US restaurant health-inspection data, one metro at a time**
Thesis: aggregate fragmented county inspection data for a named vertical buyer.
Signal: "no single API aggregating this data nationally" [S] origami.chat; Rat Radar covers 34 cities [S]. **Why-now WEAK — evergreen, no catalyst.**

**24. NZ building-consent aggregation across ~67 councils** — **RED FLAG**
Signal: no centralised API exists [S] building.govt.nz. **NO COMPETITORS FOUND** — per the brief's rule, a red flag. Likely cause: consent applications carry homeowner personal data and NZ Privacy Act treatment of bulk redistribution is **unresolved and unverified**.

**25. NZ Charities Register value-add layer** — **THIN**
Signal: 27,800+ charities, open API, **CC BY 3.0 NZ, commercial reuse explicitly permitted** [S] — cleanest licence found. But the official data is already free and complete; nothing to accumulate. No moat.

**26. eBay listing tool rebuild post-InkFrog shutdown** — **WINDOW CLOSED**
Signal: InkFrog shutdown announced 29 Apr 2026, effective 1 Jun 2026 [S], but **7+ competitors positioned within weeks** (Frooition, Nembol, CedCommerce, Webinterpret, 3Dsellers, GeekSeller) [S].

**27. NPS/CSAT tool rebuild post-Delighted shutdown** — **WINDOW CLOSED**
Signal: Delighted signups blocked Jul 2025, full shutdown 30 Jun 2026; price anchor $39/100 responses [S]. **6 competitors already positioned** [S].

**28. Paid MCP server / agent-tool monetisation** — **REJECT**
Signal: **"over 20,000 MCP servers in the wild… less than 5% have ever made a single dollar"** [S]. Confirmed real revenues are tiny; the outlier claims are vendor-promoted and unverifiable. The exact trap the brief warned about.

---

## D. Platform-ecosystem micro-SaaS

**29. NZ construction retention-money trust compliance ledger (Xero add-on)**
Thesis: narrow compliance tool keeping the legally-mandated separate trust ledger for retention money and auto-generating the quarterly subcontractor report. Never touches the money.
Signal: **Construction Contracts (Retention Money) Amendment Act 2023** requires retention held on trust in a separate account, with quarterly reporting; **fines to $200,000 per offence plus $50,000 per director** [S] legislation.govt.nz, Anderson Lloyd. Five apps already touch this (Retention Track, Payapps, Gojee, Workbench, RemitClear) — but **Retention Track, the closest positioning, had zero reviews** [S].

**30. Xero API egress-cost monitor, sold to other Xero app developers**
Thesis: forecast a Xero partner's monthly egress bill under the new pricing and alert before a tier threshold.
Signal: **Xero retired its 15% rev-share on 2 March 2026** for tenant+egress tiers ($0/5 connections → $895/mo/10,000; overage $2.40 AUD/GB). **One developer reported their bill going from near-zero to >$17,000/year overnight** [S] Accounting Today. **NO COMPETITOR FOUND — but the competitor search never ran, so this is weak evidence of absence, not proof.**

**31. Foreign-currency / difficult-receipt capture add-on (Xero)**
Thesis: attack the specific documented weak points of Xero's free bundled Hubdoc rather than general receipt OCR.
Signal: **Hubdoc — free and bundled — is rated 3.3–3.5★ against Dext Prepare 4.8★ and AutoEntry 4.7★** [S]; reportedly unreliable on foreign-currency amounts, handwritten, faded thermal and complex layouts [S]. Classic high-install/poor-rating pattern. **Why-now: NO EVIDENCE FOUND.**

**32. QuickBooks↔Shopify reconciliation patch for stranded merchants**
Thesis: patch the functionality Intuit's forced 2026 connector migration removed.
Signal: users report the new app **does not create Sales Receipts**, gives no re-sync ability, cannot map payment types to separate bank accounts, and that **"80% of the features of the old app no longer work"** [S]. Strong dated why-now. **Competitor landscape UNVERIFIED.**

**33. Micro cash-flow forecasting for Xero Starter/Core tiers**
Thesis: flat-fee forecasting for sole traders, against incumbents whose pricing scales with business size.
Signal: Float is the most popular Xero cash-flow app (5★); Fathom serves **99,000 companies** over 13+ years [S] — durable willingness to pay. Users question why they should pay more as the business grows for the same app [S]. **No dated trigger; low clone resistance.**

**34. Fixed-asset register for sole traders (Xero)** — **WEAK**
Signal: Asset.Guru's stated sweet spot is **500–20,000 assets** [S] — a clear micro-end gap. But **Xero's native fixed-asset register is free**, capping willingness to pay. Weakest why-now of any candidate.

**35. Shopify App Store general entry** — **REJECT on saturation**
Signal: **18,062 apps live, +610 in 30 days, +52% YoY new-app growth** as of 29 Apr 2026 [S] appstoreresearch.com. Shopify itself admitted in Feb 2026 that review times had blown out from volume [S]. Fails kill-question 6.

**36. Atlassian Marketplace entry** — **REJECT on economics**
Signal: Connect app revenue share rising **15% → 20% (1 Jan 2026) → 25% (1 Jul 2026)** [S]. A platform raising its take 67% in eighteen months is not a place to build a $3k/mo business.

## E. Unglamorous verticals and market arbitrage

**37. NZ body-corporate Long-Term Maintenance Plan builder for self-managed committees**
Thesis: guided wizard letting a volunteer committee build the mandatory 10/30-year LTMP and reserve-fund schedule.
Signal: **Unit Titles Amendment Act 2022 — "no ability for a body corporate to opt-out"**, final provisions in force 9 May 2024, statutory 3-year review cadence [S] stratatitle.co.nz, hud.govt.nz, legislation.govt.nz. Incumbent MRI Strata Master targets *managing agencies*, not committees [S]. A firm already sells LTMP writing as a manual service [S] thehouseinspector.co.nz.

**38. NZ self-managing-landlord compliance dashboard**
Thesis: per-property tracker for Healthy Homes statement renewal and cert expiry, alongside the new mandatory Bond Hub.
Signal: Healthy Homes compliance statement mandatory for all private rentals **from 1 July 2025**; **as of 29 June 2026 all bond transactions moved online via Bond Hub** [S] tenancy.govt.nz. Two converging regulatory deadlines hitting landlords who previously ran no software.

**39. Tattoo-studio flat-fee booking + deposit tool** — **REJECT**
Signal: real complaints against Booksy for "fee stacking and unexpected Boost charges" and double-bookings [S] ddiy.co. But 6+ direct competitors, some funded; payment and calendar sync are exactly where incumbents fail, so a solo builder inherits the highest-support-burden part.

**40. Independent funeral-home flat-fee tribute/payments site** — **REJECT**
Signal: Tukios claims "trusted by 10,000+ funeral homes since 2010" [S], and a $49/mo flat-fee alternative already exists [S] partingpro.com. **NO EVIDENCE FOUND** of any specific complaint against a named product. Emotionally sensitive, time-critical support demands a human on the phone — breaks the 3 hr ceiling.

**41. Skip/waste-bin hire operator software** — **DISQUALIFIED on saturation**
Signal: 6 named AU/NZ vendors already, several with Xero/MYOB integration built — iHub Logistics ("Built for Australian & New Zealand Operators"), HirePOS, CloudBin, Binwatch, AR Digital, Infinity2X One [S].

**42. Driving-instructor scheduling** — **DISQUALIFIED on saturation**
Signal: 6 named products incl. bookitLive (explicitly AU+NZ) and Bookeo at $39.95/mo [S].

**43. Marina berth booking** — **DISQUALIFIED on mechanism**
Signal: Dockwa "trusted by 1000+ marinas"; **Marinapy already explicitly courts "small to mid-sized operations where lean teams matter most"** [S]. Migrating a marina's berth map is inherently per-customer manual work — breaches the no-manual-work constraint regardless of competition.

**44. Veterinary recall/reminder add-on** — **DISQUALIFIED**
Signal: real complaints that reminder cards "are not getting to the clients" and that platforms "don't talk to each other" [S] capterra.com. But **"iRecall alternatives" is itself an indexed category** [S] saashub.com — an established point-solution already owns this exact niche. Evidence the model works, not evidence of a gap.

---

## The most important negative finding in the longlist

**No clean "proven overseas, absent locally" arbitrage gap was found.** Every AU/NZ vertical actually searched already had vendors serving *both* markets from one product — iHub Logistics "Built for Australian & New Zealand Operators", bookitLive "across Australia and New Zealand", MRI Strata Master sold in both [S]. The naive localisation thesis does not survive contact with evidence. The only localisation-shaped opening found is narrower: an enterprise vendor that has not come *down-market*, which is a much thinner wedge.

**Verified population figures:** NZ **5,361,300** (Stats NZ provisional, 31 March 2026) [S] stats.govt.nz; Australia ~27.8M at 31 Dec 2025, reaching 28M during 2026 [S] abc.net.au. **Combined AU+NZ ≈ 33.3M, about 5.2× NZ alone.**
**Verdict:** NZ alone is very likely insufficient for a narrow vertical at US$3,000/month. **AU+NZ combined is the minimum viable geography for almost any narrow B2B vertical here** — though no verified buyer-count denominator was obtained for any single category, so this remains order-of-magnitude reasoning.

---

## Coverage gaps in this longlist (stated, not hidden)
The session's web-search budget (200/200) was exhausted before these were reached: idea-level signals for **Notion, Figma, Monday.com, Airtable and Webflow**; trades certification/licence-expiry trackers; self-storage lead follow-up; commercial-cleaning quoting; equipment/plant-hire booking; sports-club vetting trackers. **No primary Reddit thread content was retrievable for any subreddit** — every attempt returned aggregator or Capterra pages instead. The brief asked for forum-level user voice and I largely could not obtain it; that is a genuine shortfall against §6 of the brief, not a completed search.

---
---

# ROUND 2 ADDITIONS (2026-09-03) — global/online only, 20 hrs/week

**45. Multi-jurisdiction corporate insolvency / distress-event API** ⭐ **SELECTED**
Normalised real-time feed of insolvency filings from national gazettes (FR/UK/ES). Signal: GitHub request open since **2024-06-05**; documented **€40,000 credit line extended to a company that had filed 11 days earlier** because the incumbent API missed it (May 2026); **three separate abandoned German scrapers** incl. a **DEPRECATED** Apify actor [S].

**46. Insurance producer licence & CE compliance (5–30 producer agencies)**
Signal: **AgentSync contracts average >$100k/yr, up to ~$370k**, before required Salesforce licensing [S] g2.com; Sircon pricing called "insane"; **two live job ads** for the manual role [S].

**47. EPR obligation-mapping API for cross-border e-commerce**
Signal: "Amazon does not handle your EPR compliance" — consequences include **listing suspension, withheld payouts, full market exclusion** [S]; fees **$10 (DE) to $165+ (FR)**; **PPWR obligations from 12 Aug 2026** [S].

**48. Freight carrier-fraud vetting for small brokerages** — **CUT ON LIABILITY, best raw demand in the project**
Signal: cargo theft **~$725M in 2025, up 60% from $455M**; FMCSA double-brokering complaints **8,000+ in 2025 vs ~2,000 in 2021**; **15,419 broker authorities revoked** [S]. But Truckstop RMIS Lite already at **$340/mo**, and a solo vendor cannot price the liability.

**49. Make.com first-native-app for an underserved vertical** — **CUT, but the only structural exclusivity found**
Make "will only accept an app if [the incumbent] is not actively developing it" [S] developers.make.com. **Buildium is not on Zapier at all**; property managers reportedly spend **$8,400–$14,200/yr** on middleware workarounds [S]. Cut because **Make has no payments rail** — the defensible asset doesn't monetise.

**50. Chemical / cosmetic ingredient regulatory-status API** — **CUT ON LICENCE**
**ECHA legal notice: CAS numbers/names are "the property of the American Chemical Society and any use or redistribution... is not permitted without... prior written permission"** [S] echa.europa.eu/legal-notice.

**51. Notion compliance-grade backup** — weak moat
A solo founder runs "Notion Backups" at ~**US$2,300 MRR** [SELF-REPORTED]. But SimpleBackups ($49–299/mo), ProBackup and BackupLABS compete, and clone resistance is LOW.

**52. HubSpot silent workflow-failure alerting** — **CUT**
Ideas thread active **19 Sept 2025**; native tooling is passive log review [S]. But it is an obvious low-effort HubSpot feature — highest absorption risk found.

**53. Webflow post-sunset subscription reconciliation**
**Webflow sunset native User Accounts 29 Jan 2026**, forcing customers onto Memberstack/Outseta [S]. Vendor-neutral reconciliation across Stripe + membership platform + CMS.

**54–59. Round-2 rejects:** EU procurement debarment aggregator (**Germany's Wettbewerbsregister has no public API**, bulk redistribution not intended); e-invoicing mandate tracker (**free trackers already exist** covering 126–130 countries); product recall aggregation (**SuperRecall.ai $449/mo, 60+ countries**); sanctions/PEP screening (**free OpenSanctions** + ComplyAdvantage $99.99/1000); VAT rate APIs (**TaxRates.io $9/mo**); company registry aggregation (Sayari, Orbis, Creditsafe, from €0.05/request); ISO 17025 / LIMS (**$50k+/yr but no complaints or job ads found**); clinical-trial eISF (**Veeva SiteVault has a free tier**); US professional licence lookup (Apify actors, all 50 states); DOT driver-qualification files ($30–150/mo, served); medical credentialing ($50–200/mo, served); UK right-to-work (£149/mo unlimited); government tender monitoring (HigherGov $500–2,500/yr, GovTribe $1,350–4,000/yr already serve small tier); IOLTA for solo attorneys (Clio, CosmoLex, LeanLaw, PCLaw, Soluno).

## Round-2 marketplace mechanics — the finding that saves months
**Most platform marketplaces have no payments rail at all.** Only **monday.com** (built-in Stripe, mandatory since July 2024) offers one to a new solo developer. **Figma is CLOSED to new paid sellers.** **Discord's rail excludes NZ developers** (US/UK/EU only). Notion, Airtable, Webflow, Slack, Zapier, Make and HubSpot are **discovery-only**. **ClickUp has no third-party marketplace at all.** Full table in `research/marketplace-payments-rails.md`.
