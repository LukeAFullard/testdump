# Maintenance-as-Moat Data Products (2026-09-03, round 2)

[S] = search-result summary + URL; [I] = inference. Agent ran 38 searches; **WebFetch was blocked network-wide**, so all legal-text claims rest on search snippets, not fetched pages. That is a real precision limit on the licence findings below.

## 1. Multi-jurisdiction corporate insolvency / distress-event API — STRONGEST
**Thesis:** normalise insolvency filings from national gazettes (Spain BORME, UK Gazette, France BODACC; later DE/IT/NL/PT) into one real-time API + webhook feed. Buyers: B2B credit-risk teams, trade-credit insurers, factoring/invoice-finance firms, debt collectors, procurement risk. **US$250–400/mo — six customers hits the whole target.**

**Demand — the best user-voice evidence in the entire project:**
- GitHub feature request **open since 2024-06-05, still unresolved**: "API for Insolvenzbekanntmachungen", stating "as a private company it is very useful to be informed as soon as possible, if one of the business partners is experiencing insolvency proceedings" [S] https://github.com/bundesAPI/sofortmassnahmen/issues/81
- Founder account, **May 2026**, of a concrete loss: a customer "approved a €40,000 line of credit to a Spanish company that had filed for insolvency eleven days earlier... the credit data API they were using hadn't picked it up yet" [S] https://medium.com/@matiasmaquieira96/why-insolvency-data-is-always-late-and-the-api-i-built-to-fix-it-378ab1044fc7
- **Three separate people built the same German insolvency scraper and let it lapse** — Apify's listing is marked **"[DEPRECATED]"** (https://apify.com/studio-amba/insolvenzbekanntmachungen-scraper), plus unmaintained GitHub repos `NDelventhal/InsolvencyAnnouncementsGer`, `agapius/Insolvenzradar`, `leander-ms/insolvenzbekanntmachungen` [S]. **This is the maintenance-moat thesis stated as evidence: the grind is exactly what people quit.**
- Incumbent weakness: large aggregators "license bulk corporate data feeds rather than running their own jurisdiction-specific scrapers", so refresh lags **3 to 21 days, longer in smaller jurisdictions** [S]

**Competitors — nascent, not empty (a stronger signal than emptiness):**
- **Prometiam Risk API** — Spain/UK/France live; founder aims to beat "platforms charging fifty times more"; **pricing not published** [S] prometiam.com
- **Insolvencies.live** — real-time via Pusher Channels; ES/UK/FR live, DE/IT/NL/PT on roadmap; **pricing not published** [S] insolvencies.live/documentation.html
- **getregdata** — pay-per-result **$0.003–$0.01/result**, 29 registry actors incl. an insolvency watchlist [S] getregdata.com

**Legality — the decisive check:**
- **France (BODACC): CLEAR.** Licence Ouverte / Open Licence 2.0 — "free commercial reuse, including redistribution and incorporation into derivative products, with source attribution" [S] data.gouv.fr/datasets/bodacc
- **UK (The Gazette): CLEAR for corporate notices.** OGL v3.0, but **personal data is explicitly excluded from OGL reuse** — caution on individual-insolvency notices [S] thegazette.co.uk/data
- **Spain: legally clear, technically harder.** Law 37/2007 on PSI reuse; **but no official REST API** — data.boe.es is "the closest thing", so scraping is required [S] businessdataguide.com
- **Germany: CAUTION — active regulatory fight, NOT settled law.** German DPAs are in discussion with the NRW Ministry of Justice specifically "to make it more difficult for private providers of portals to extract insolvency data... and permanently publish it searchable on the internet" [S] ldi.nrw.de. **Launch FR/UK/ES; treat Germany as unresolved.**

**Clone resistance (Tier 1, time-accumulated):** each jurisdiction is a separate scraper/parser — different language, format (PDF vs JSON vs HTML), cadence — plus ongoing legal monitoring. **2–4 months to reach the 3-country parity competitors already have; 6–12 months for a 5–7 country footprint**, and staying current is permanent.
**Maintenance:** 8–12 hrs/week [I] — fits the 20-hour ceiling.
**Distribution:** buyers identifiable **by name and title** — credit-risk managers, trade-credit underwriters, factoring ops staff — via LinkedIn title search and trade bodies. Textbook enumerable-prospect motion.

## 2. SMB-tier chemical/cosmetic ingredient regulatory-status API — CUT ON LICENCE
CAS/EC lookup across TSCA, REACH/SVHC, China IECSC, Japan ENCS, Korea KECI. Enterprise incumbents all quote-only: 3E Regulatory Intelligence (350,000+ substances), SGS Digicomply (160+ jurisdictions), CIRS ChemCheck [S].
**Killer:** **ECHA's legal notice states CAS numbers/names sourced via ECHA are "the property of the American Chemical Society and any use or redistribution... is not permitted without... prior written permission"** [S] echa.europa.eu/legal-notice. China IECSC bulk access is a paid CIRS product (confidential-part enquiry 3,000 RMB) [S]. Two of the largest jurisdictions are legally encumbered. Maintenance 10–15 hrs/wk, at the ceiling.

## 3. EPR obligation-mapping API for cross-border e-commerce — MEDIUM, genuinely underserved
**Thesis:** data-only API answering "which packaging/WEEE/battery EPR registrations does category X need in country Y, what fee, what threshold, what deadline" — explicitly **not** the registration service.
- eBay publishes an EPR regulation page; "Amazon does not handle your EPR compliance", with consequences including "listing suspension... withheld payouts... full market exclusion" [S] avask.com
- Fragmentation documented: a Spanish seller shipping to DE/FR/IT/NL "may need four separate EPR registrations"; France's system "takes no account of small businesses"; fees range **$10 in Germany to over $165 for France** [S] minefieldnavigator.com
- **PPWR adds fresh obligations from 12 August 2026** [S] tracextech.com — a live moving target
**Why the space is empty — and it passes the brief's test:** every player found (AVASK, Minefield Navigator, EPR-Register®) monetises the **manual registration service**, which is exactly the non-scalable fulfilment model the operator must avoid. **NO EVIDENCE FOUND** of a pure self-serve "which registrations do I need" data API. The emptiness has a business-model explanation, not a no-demand explanation.
**Legality: NOT CONFIRMED.** No explicit redistribution prohibition found, but no explicit permissive licence for any national PRO's fee table either. Needs a per-country check before launch.
**Maintenance:** 6–10 hrs/wk. **Distribution:** compliance managers at named 3PLs and seller aggregators — one 3PL account represents many downstream sellers.

## 4. EU procurement debarment/exclusion aggregator — CUT
Fragmentation is real ("Most EU jurisdictions do not have a single national debarment registry... no uniform name... no uniform model" [S] hsfkramer.com), but **NO EVIDENCE FOUND of expressed willingness to pay**, and Germany's Wettbewerbsregister **has no public API** — access needs an authenticated MeinUK/Elster/BundID account, per-request [S] bundeskartellamt.de. Bulk commercial redistribution is plainly not the intended use. **DISQUALIFIED pending explicit confirmation.**

## 5. E-invoicing mandate status API — CUT
**Free** trackers already exist and are maintained: eInvoice.Global (126 countries), e-invoice.app (130+) [S]. One says a developer API "is being built". Free underlying content makes charging hard. Only viable as a bundled feature, not standalone.

## Rejected as SATURATED (occupancy test applied)
| Space | Evidence |
|---|---|
| Product recall aggregation | SuperRecall.ai **$449/mo, 60+ countries**, plus RecallStream and Apify actors [S] |
| Sanctions/PEP screening | **Free** OpenSanctions + ComplyAdvantage **$99.99/1000 entities, 4.3/5 on G2** praised for SMB affordability [S] |
| VAT/GST rate API | **TaxRates.io at $9/month**, strong reviews [S] |
| Company registry aggregation | Sayari, Moody's Orbis, Creditsafe, InfobelPRO, Coresignal, from €0.05/request [S] |
| Medical device registration | Emergo by UL, RegDesk, Rimsys, MakroCare own the workflow [S] |
| US professional licence lookup | Multiple Apify actors across all 50 states [S] |

## Could not verify
Pricing for Prometiam, Insolvencies.live, getregdata (all off-site or behind signup). Revenue/customers for any solo-built competitor. Full terms of insolvenzbekanntmachungen.de, bundeskartellamt.de, thegazette.co.uk — **WebFetch blocked, snippets only**. Redistribution terms for NL/IT procurement registers. Whether any national PRO permits redistribution of its fee schedule.
