# 03 — Deep Dives on the Surviving Three

**Run date 2026-09-03.** All three survivors are **wounded**; none emerged from Stage 3 undamaged. Scores below are deliberately conservative — see `00-brief-review.md` §C4 on why a self-assigned score is not evidence.

**Rubric note:** the brief says "all nine" criteria but the table lists **eight**, whose weights sum correctly to 100. I score the eight given.

**Currency — REVISED 2026-09-03.** The operator has confirmed the target is **NZ$3,000/month (≈US$1,800)**, not US$3,000. This is a **40% lower bar** than originally assumed and it changes every number below. NZD/USD ≈ 0.60 [ESTIMATE — check spot].

**Geography — REVISED 2026-09-03.** The operator has confirmed the business **need not target NZ customers**, and that **compliant cold email and trade-forum posting are both acceptable**. Both changes are incorporated in the scores.

---

## The churn arithmetic that governs all three

From `research/ground-truth-findings.md`: customers paying **under US$50/month churn at 6–8.6% monthly**. This remains the most important constraint on the target and is almost always ignored in plans like this one.

Model: `N(t) = (G/c) × (1 − (1−c)^t)` where `G` = gross new paying customers per month, `c` = monthly churn.

**Target: NZ$3,000/month.**

| Price | Churn | Customers needed | New customers/month | Gross signups over 12 mo |
|---|---|---|---|---|
| NZ$79 (US$47) | 6% | **38** | **4.4** | ~52 |
| **NZ$149 (US$89)** | **5%** | **21** | **2.3** | **~28** |
| NZ$199 (US$119) | 5% | **16** | **1.7** | ~21 |

*Worked example at NZ$149: `3000 ÷ 149 = 20.1 → 21 customers`. `1 − 0.95^12 = 0.4596`, so `N(12) = G × 9.19`. `21 ÷ 9.19 = 2.3 per month`.* [ESTIMATE]

> ### The two decisions that do the most work
> **1. The currency clarification alone cut the job nearly in half** — from 3.7 new customers a month to 2.3. Roughly **one new customer every 13 days for a year** is now the whole task. That is a materially different proposition from the one I scored at 62.
>
> **2. Price high anyway.** Moving NZ$79 → NZ$149 cuts required monthly acquisition from 4.4 to 2.3 — a 48% reduction in the hardest part of the job — *and* lowers churn by crossing the US$50 threshold. Kill-question 8 says price to value delivered. **A tool that helps avoid a NZ$200,000 fine is not a NZ$79/month product.** NZ$199 is worth testing.

---

# Candidate A — NZ Construction Retention-Money Trust Compliance Ledger
### *Strongest of the three*

**Product.** A narrow compliance tool for NZ head contractors and larger subcontractors who hold retention money from subcontractors. Maintains the legally-required separate trust ledger, auto-generates the mandatory quarterly report to each subcontractor, and warns before a breach. **It never touches the money** — the funds stay in the client's own bank account.

**Buyer.** NZ construction businesses that withhold retentions. **Price: NZ$149/month (US$89)** per the arithmetic above.

### Evidence pack

**Demand signals**
1. **Construction Contracts (Retention Money) Amendment Act 2023** requires retention money held on trust in a separate NZ-registered bank account used solely for that purpose. [S] legislation.govt.nz — accessed 2026-09-03
2. Quarterly reporting to every subcontractor is mandatory: amount, contract, dates, bank details, inspection rights. [S] Anderson Lloyd, Wynn Williams — accessed 2026-09-03
3. Penalties: **up to $200,000 per offence, plus $50,000 per director** for a body corporate. [S] same — accessed 2026-09-03
4. Five apps already serve adjacent needs in the Xero NZ store — Retention Track, Payapps, Gojee, Workbench, RemitClear — proving the segment buys software. [S] — accessed 2026-09-03
5. **Retention Track, the closest-positioned competitor, had zero reviews** at time of search. [S] — accessed 2026-09-03

**Honest weakness in this pack:** signals 1–3 establish a *legal obligation*, not *observed user demand*. **No forum post, review or complaint from an actual NZ contractor was found.** By the brief's own definition, this is **not yet validated**.

**Competitors** — none is a pure compliance product; all are job-management platforms with retention as a feature [I].
| Competitor | Positioning | Pricing |
|---|---|---|
| Retention Track | Retention tracking + Xero sync, AU/NZ/UK legislation-matched | **Not disclosed** — could not verify |
| Payapps | Progress-claim submissions → Xero invoices | **Not disclosed** |
| Gojee | WIP + job costing for accountants | **Not disclosed** |
| Workbench | Project management with retentions module | **Not disclosed** |

**Proof of spend.** Indirect but real: five vendors sustain products for this buyer. **No pricing was verifiable for any of them** — a material gap.

**Bottom-up market math** *(every input marked)*
```
Reachable buyers   = UNVERIFIED — no count of NZ businesses holding retentions was obtainable
Price              = NZ$149/mo                               [ESTIMATE, chosen by value-pricing logic]
Customers needed   = 3000 / 149 = 21                         [ESTIMATE]
Gross signups req. = 2.3/month, ~28 over 12 months           [ESTIMATE, 5% monthly churn]
```
> **Revised 2026-09-03.** At the confirmed NZ$3,000 target, **28 gross signups over a year** is needed rather than 45. Against a pool of even **800** businesses that is **3.5% penetration**; against 1,500 it is 1.9%. **The TAM concern that wounded this candidate is much reduced, though not eliminated** — a pool under ~400 still kills it. Resolving the number remains Phase 0's first job, but the threshold it must clear has dropped substantially.

**Expansion path — newly relevant now that geography is open.** Retention Track markets itself as **"AU/NZ/UK legislation-matched"** [S], which is evidence that analogous retention-trust regimes exist in Australia and the UK. **This is a competitor's own marketing claim and I could not verify the underlying regimes — treat as a hypothesis, not a fact.** If it holds, the sequence is NZ first (cheapest credibility, right timezone), then Australia (~5× the market, 2–4 hour timezone gap), then the UK. **Verifying whether AU and UK retention-trust obligations genuinely exist and resemble NZ's is now a Phase 0 task**, because it converts a small-TAM risk into a staged growth plan.

**Why now.** The Act is in force with severe penalties. Weaker than a fresh deadline — the law has been live since 2023 and full commencement was **not verified**.

**Distribution — first channel: NZ construction trade associations.** Registered Master Builders, Specialist Trade Contractors Federation, and regional builder groups publish member directories and newsletters. Secondary: compliant targeted outreach to NZ head contractors whose business addresses are conspicuously published (deemed consent under the Unsolicited Electronic Messages Act 2007 — see `research/distribution-findings.md` Finding 4). Tertiary: Xero App Store listing, though certification requires **≥3 active customers onboarded within a 30-day review window** — a chicken-and-egg gate that means direct sales must come first.

**What stops a three-week clone?** Honestly, not much in code. The defence is: correctness on trust-ledger math and the exact quarterly report format (a subbie facing a $200k fine will not risk an unproven tool); accumulated reviews and case studies; and NZ-specific regulatory knowledge. **This is a weak moat and should be treated as such.** The realistic protection is that the market is too small to attract a serious competitor — which is the same reason it caps out around US$3–10k/month.

**Steady-state hours/week: ~3.0** — 1.0 support (email only), 0.5 Xero API/webhook monitoring, 0.5 regulatory monitoring (MBIE/building.govt.nz), 1.0 content and listing upkeep. **At the ceiling, not under it.**

**Compliance flags.** Must **never move or custody funds**, or risk NZ Financial Service Providers Act 2010 and AML/CFT Act 2009 scope. NZ Privacy Act 2020 applies to subcontractor personal and banking details.

### Rubric score
| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **12** | Law verified and severe, but demand is *inferred from statute*; zero user-voice evidence found. **+1 on revision:** the same evidence now has to support 21 customers rather than 34 |
| Distribution | 20 | **14** | Associations + home market and timezone; **+1 on revision:** compliant cold email and forum posting are now confirmed available, not assumed |
| Willingness to pay | 15 | **10** | $200k/$50k penalties motivate strongly; five vendors prove spend — but no pricing verifiable |
| Defensibility | 10 | **4** | Low. Compliance logic is copyable; only correctness and reviews defend it |
| Passivity ceiling | 10 | **7** | ~3.0 hrs/wk. Quarterly cadence, no daily ops — but sitting on the ceiling |
| AI-agent buildability | 10 | **9** | CRUD + ledger arithmetic + PDF reports + optional Xero API. Entirely conventional |
| Time to first customer | 8 | **4** | 3–5 months realistically; direct sales must precede the marketplace listing. **Unchanged** — a lower revenue target does not make the *first* customer arrive sooner |
| Platform & regulatory risk (inverted) | 7 | **4** | Xero's Mar 2026 egress pricing is a live risk; mitigated by building standalone/CSV-first. Commencement date unverified |
| **TOTAL** | **100** | **64** | **Was 62. Still one point below the bar** |

> **A note on scoring discipline.** I moved exactly two criteria, by one point each, and I can name the reason for both. I deliberately did **not** bump time-to-first-customer, even though it would have produced a satisfying 65, because a smaller target genuinely does not make the first sale happen faster. Per `00-brief-review.md` §C4, scoring *to* the bar is the failure mode this rubric invites, and 64 is the honest number.

---

# Candidate B — AU Payday Super Reconciliation
### *Largest market, confirmed wound*

**Product.** Three-way match per pay cycle (STP-reported super vs SuperStream confirmation vs bank debit) for AU bookkeepers managing multiple employer clients.

**Buyer.** Australian bookkeepers and BAS agents. **Price: A$99/month per practice** [ESTIMATE].

### Evidence pack
1. **Treasury Laws Amendment (Payday Superannuation) Act 2025**, Royal Assent given; **mandatory from 1 July 2026 — live now**. [S] Grant Thornton, ATO, Fair Work Ombudsman — accessed 2026-09-03
2. SG at 12% must reach the fund within **7 business days**; penalty **60% of the shortfall** plus daily interest. [S] — accessed 2026-09-03
3. **The ATO's own Small Business Superannuation Clearing House closed 1 July 2026**, forcing small employers onto third-party clearing houses — a genuine disruption event. [S] superchoiceservices.com — accessed 2026-09-03
4. Reconciliation is now **per pay cycle**, not quarterly. [S] — accessed 2026-09-03
5. Two small vendors already live: SmallBiz Super Check, FairWork Mate Super Payslip Audit. [S] — accessed 2026-09-03

**Competitors.** Xero, MYOB, e-PayDay bundling payday-super compliance into payroll at **$10–25/employee/month** [S]; plus the two small vendors above (pricing not verifiable).

**Bottom-up market math**
```
Reachable buyers   = UNVERIFIED — no count of AU bookkeeping practices obtained
Price              = A$99/mo ≈ US$65                        [ESTIMATE]
Customers needed   = 3000 / 65 = 46                          [ESTIMATE]
Gross signups req. = ~5/month, ~60 over 12 months            [ESTIMATE, 5% monthly churn]
```

**Why now.** Strong and dated — mandate live two months ago, clearing-house closure forcing migration right now.

**Distribution.** AU bookkeeper communities (Institute of Certified Bookkeepers, Association of Accounting Technicians), compliant targeted outreach, AU timezone overlap (2–4 hours — the operator's best market).

**The wound.** Feature absorption is not hypothetical; it is happening. The buyer already owns payroll software that is building this in.

**Steady-state hours/week: 3–4** — **over the ceiling.** SG rates index annually; clearing-house integrations break.

### Rubric score
| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **12** | Mandate verified, penalties severe, disruption real — but again no user-voice evidence |
| Distribution | 20 | **13** | Real bookkeeper associations; best timezone overlap available to this operator; cold outreach now confirmed |
| Willingness to pay | 15 | **10** | Bookkeepers expense tools; penalties severe |
| Defensibility | 10 | **3** | SG rules are published by the ATO. Essentially none |
| Passivity ceiling | 10 | **5** | 3–4 hrs/wk — **breaches the stated ceiling** |
| AI-agent buildability | 10 | **7** | STP/SuperStream integration is non-trivial and regulated |
| Time to first customer | 8 | **5** | 3–4 months |
| Platform & regulatory risk (inverted) | 7 | **2** | **Active feature absorption by Xero/MYOB — the dominant risk, already underway** |
| **TOTAL** | **100** | **57** | **Well below the bar.** The revision does not touch its wound: absorption by Xero and MYOB is already underway |

---

# Candidate C — Xero API Egress-Cost Monitor
### *Highest variance: best pain evidence, worst structural position*

**Product.** Ingests a Xero app partner's API call patterns, forecasts their monthly bill under the March 2026 tenant+egress pricing, alerts before a tier threshold, and recommends caching/webhook changes.

**Buyer.** Other Xero app developers and agencies. **Price: US$79/month** [ESTIMATE].

### Evidence pack
1. **Xero retired its 15% App Store revenue share on 2 March 2026**, replacing it with tiered developer-platform pricing: Starter $0/5 connections → Advanced $895/mo/10,000 connections; egress overage **$2.40 AUD/GB**. [S] developer.xero.com/pricing, Accounting Today — accessed 2026-09-03
2. **At least one developer reported their bill going from near-zero to over $17,000/year overnight.** [S] Accounting Today, publicaccountant.com.au — accessed 2026-09-03
3. Pricing is explicitly usage-metered, so **every** Xero app developer now has a live, recurring, quantifiable cost to manage. [S] — accessed 2026-09-03
4. Industry coverage frames this as a shock to the whole partner base, not an isolated case. [S] AccountingWEB — accessed 2026-09-03
5. Xero App Store lists **>1,000 apps across 30+ categories** — bounding the buyer universe. [S] — accessed 2026-09-03

**Competitors. NO EVIDENCE FOUND** of an existing third-party Xero-egress monitor. **This is weak evidence of absence, not proof** — the targeted competitor search never ran before the budget was exhausted. Per the brief's own rule, an apparently empty space is a red flag until explained.

**Bottom-up market math**
```
Reachable buyers   = ~1,000-1,500 developer orgs             [ESTIMATE, from >1,000 listed apps]
Price              = US$79/mo                                 [ESTIMATE]
Customers needed   = 3000 / 79 = 38                           [ESTIMATE]
Penetration req.   = 38 / 1,250 = 3.0% of ALL Xero app developers [ESTIMATE]
Gross signups req. = ~4/month, ~50 over 12 months             [ESTIMATE, 5% monthly churn]
```

**Why now.** The best in the run — a dated, quantified, six-month-old pricing shock.

**Distribution.** Xero Developer community and Slack, developer forums, and SEO for narrow terms like "Xero API pricing calculator". Reachable, but **not** marketplace search.

**The wounds, both structural and unrebutted.**
1. **Xero can ship this in its own developer dashboard at any time.** It is a small feature for them and an obvious one. There is no defence.
2. **The buyer is a software developer** — the worst possible customer for a tool this simple, because they can build it in a weekend.
3. The pain may be **transitional**: developers optimise once, then stop caring.
4. You are selling to a base that is simultaneously being squeezed on cost — a shrinking, cost-averse market.

**Steady-state hours/week: ~3.0** — low support (technical buyers), but 1.0 hr/wk tracking Xero's own pricing rules is mandatory, because the product dies silently if they change.

### Rubric score
| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **11** | Dated and quantified pain, but sourced from news coverage, not users asking for a tool |
| Distribution | 20 | **12** | Precise and reachable dev community, but narrow and not marketplace-driven; outreach now confirmed |
| Willingness to pay | 15 | **9** | $17k/yr pain trivially justifies the price — and at the NZ$3,000 target only ~23 of ~1,250 developer orgs (1.8%) are needed. But the buyer can still build it themselves |
| Defensibility | 10 | **2** | Lowest in the set. The customer *is* the potential cloner |
| Passivity ceiling | 10 | **7** | Low support load; mandatory ongoing pricing-rule monitoring |
| AI-agent buildability | 10 | **9** | Straightforward API ingest, modelling and alerting |
| Time to first customer | 8 | **6** | Fastest of the three — no marketplace gate, developers buy quickly |
| Platform & regulatory risk (inverted) | 7 | **1** | **Worst possible: single-platform dependency where the platform is also the obvious competitor** |
| **TOTAL** | **100** | **57** | **Well below the bar.** The revision does not touch its wound: Xero remains both its platform and its most likely competitor |

---

## Scoreboard

*Revised 2026-09-03 for the confirmed NZ$3,000 target, open geography, and confirmed willingness to do cold outreach. Original scores in brackets.*

| Candidate | Demand /20 | Distrib /20 | Pay /15 | Defens /10 | Passive /10 | Build /10 | Speed /8 | Risk /7 | **Total** |
|---|---|---|---|---|---|---|---|---|---|
| **A — NZ retention money** | 12 (11) | 14 (13) | 10 | 4 | 7 | 9 | 4 | 4 | **64** (62) |
| **B — AU payday super** | 12 | 13 (12) | 10 | 3 | 5 | 7 | 5 | 2 | **57** (56) |
| **C — Xero egress monitor** | 11 | 12 (11) | 9 (8) | 2 | 7 | 9 | 6 | 1 | **57** (55) |

> ### **Still nothing clears the 65 bar — but the gap has changed character.**
> The best candidate now falls **one point short instead of three**, and — this is the important part — **the remaining gap is closable by Phase 0 evidence rather than by structure.** Before the revision, clearing the bar required an unknown TAM to turn out large. Now, two of Phase 0's four deliverables (a sourced TAM and ten user interviews) target the single criterion still holding it down: **verified demand evidence at 12/20**. Three of ten interviewees describing real pain would move that to 15+ and put the total at 67.
>
> The structural weakness is unchanged and will not improve: **defensibility stays at 4/10**, and no amount of validation fixes that.

The consistent pattern across all three is instructive rather than accidental: **every candidate scores well on buildability and poorly on defensibility and verified demand.** That is precisely the tension §4 of the brief predicted, showing up in the numbers rather than in argument.

---
---

# ROUND 2 DEEP DIVES (2026-09-03) — under revised constraints

Round 1 above is superseded. Constraints: **global/online only, no NZ, up to 20 hrs/week, NZ$3,000/month.**

## Revised arithmetic — the target is small and that is the point

At **NZ$3,000/month (~US$1,800)**, with 5% monthly churn and `N(12) = G × 9.19`:

| Price | Customers needed | New customers/month | Gross over 12 mo |
|---|---|---|---|
| US$100 | 18 | 2.0 | ~24 |
| **US$300** | **6** | **0.7** | **~8** |
| US$400 | 5 | 0.5 | ~7 |

**At US$300/month the entire twelve-month goal is six paying businesses — roughly one every seven weeks.** With 20 hrs/week available for outreach this is a prospecting problem, not a marketing problem, and it argues for pricing at US$250–400 rather than US$29.

---

# Candidate A — Multi-Jurisdiction Corporate Insolvency / Distress-Event API
### *The strongest candidate produced by either round*

**Product.** Normalised, real-time API + webhook feed of corporate insolvency filings from national gazettes. Launch **France (BODACC), UK (The Gazette), Spain (BORME)**; add Italy, Netherlands, Portugal later. **Germany deliberately excluded at launch** — see risk.
**Buyer.** Credit-risk teams, trade-credit insurers, factoring and invoice-finance firms, debt collectors, procurement risk teams extending credit into Europe.
**Price: US$300/month** (or usage tiers for higher volume). **Six customers = target.**

### Evidence pack
1. **GitHub feature request open since 2024-06-05, still unresolved** — "API for Insolvenzbekanntmachungen", stating a private company finds it "very useful to be informed as soon as possible, if one of the business partners is experiencing insolvency proceedings". [S] github.com/bundesAPI/sofortmassnahmen/issues/81 — accessed 2026-09-03
2. **A documented, quantified failure of the incumbent tools, May 2026:** a customer "approved a €40,000 line of credit to a Spanish company that had filed for insolvency eleven days earlier... the credit data API they were using hadn't picked it up yet". [S] medium.com/@matiasmaquieira96 — accessed 2026-09-03
3. **Three separate developers built the same German insolvency scraper and abandoned it** — Apify's listing is marked **"[DEPRECATED]"**, alongside three unmaintained GitHub repos. [S] — accessed 2026-09-03
4. Incumbent aggregators "license bulk corporate data feeds rather than running their own jurisdiction-specific scrapers", producing refresh lags of **3 to 21 days, longer in smaller jurisdictions**. [S] — accessed 2026-09-03
5. Three recent entrants monetising the same thesis (below) — proof of commercial interest, not an empty room.

> **Why signal 3 is the most important line in this document.** Three capable people built this and quit. That is the maintenance moat stated as evidence rather than as theory — and it is only available to this operator because the ceiling moved from 3 hrs/week to 20.

### Competitors — nascent, not empty
| Competitor | Coverage | Pricing |
|---|---|---|
| Prometiam Risk API | ES/UK/FR live | **Not published** — founder says the aim is beating "platforms charging fifty times more" |
| Insolvencies.live | ES/UK/FR live; DE/IT/NL/PT roadmap | **Not published** |
| getregdata | 29 registry actors incl. insolvency watchlist | **$0.003–$0.01 per result**, pay-per-result |

**Read:** three entrants in ~18 months, none with published pricing, all stuck at the same three countries. Demand has been noticed but not consolidated.

### Legality — checked, and it decides the launch sequence
- **France (BODACC): CLEAR.** Licence Ouverte 2.0 permits "free commercial reuse, including redistribution and incorporation into derivative products, with source attribution". [S] data.gouv.fr
- **UK (The Gazette): CLEAR for corporate notices.** OGL v3.0, but **personal data is expressly excluded** — so corporate insolvency only, not individual bankruptcy.
- **Spain: legally clear, technically harder.** Law 37/2007; **no official REST API**, so scraping is required.
- **Germany: EXCLUDED AT LAUNCH.** German DPAs are in active discussion with the NRW Ministry of Justice to "make it more difficult for private providers of portals to extract insolvency data". Unsettled law, not a green light.

### Bottom-up market math
```
Reachable buyers  = UNVERIFIED count, but enumerable by name and title:
                    credit-risk managers, trade-credit underwriters,
                    factoring/invoice-finance ops staff
Price             = US$300/mo                                  [ESTIMATE]
Customers needed  = 1800 / 300 = 6                             [ESTIMATE]
Gross signups     = ~8 over 12 months, ~0.7/month              [ESTIMATE, 5% churn]
```
> **Six customers.** Against a European credit-risk buyer pool that certainly numbers in the thousands, this is the lowest-penetration requirement of any candidate in either round.

**Why now.** Three entrants in 18 months; a dated €40,000 loss (May 2026); incumbents structurally lagging 3–21 days because they license bulk feeds rather than scraping.

**Clone resistance — Tier 1.** Each jurisdiction is a separate parser in a different language and format with a different cadence, plus ongoing legal monitoring. **2–4 months to reach the three-country parity the competitors already have; 6–12 months for five to seven.** Staying current is permanent. A cloner must redo it *and sustain it* — and the evidence says people quit.

**Steady-state hours/week: 8–12.** Well inside the 20-hour ceiling.

**Fulfilment test: PASSES.** Customer seven costs nothing extra — the same feed serves all customers. This is the cleanest pass of any candidate in either round.

### Rubric
| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **15** | An open GitHub request, a documented €40k loss, three abandoned scrapers, and three funded-enough entrants. **The only candidate in either round with real user-voice evidence.** |
| Distribution | 20 | **15** | Buyers enumerable by name and title via LinkedIn and trade bodies; only six needed; compliant cold email is the whole plan |
| Willingness to pay | 15 | **12** | A €40k loss trivially justifies US$300/mo; three competitors monetising |
| Defensibility | 10 | **7** | Tier 1, time-accumulated; 2–4 months to parity, 6–12 to lead; evidenced by abandonment |
| Passivity ceiling | 10 | **8** | 8–12 hrs/wk against a 20-hr allowance |
| AI-agent buildability | 10 | **8** | Scrapers, normalisation, API, webhooks — conventional. Spain's lack of an API adds work |
| Time to first customer | 8 | **6** | Fast: technical B2B buyer, no marketplace gate, direct outreach |
| Platform & regulatory risk (inverted) | 7 | **4** | Germany contested; UK excludes personal data; sources can change terms unilaterally |
| **TOTAL** | **100** | **75** | ✅ **Clears the 65 bar** |

---

# Candidate B — Insurance Producer Licence & CE Compliance

**Product.** Multi-state producer licence, appointment and CE renewal tracking for independent agencies with 5–30 licensed producers. **Price US$400/month per agency** (flat, versus incumbents' per-producer pricing).

### Evidence pack
1. **AgentSync average annual contracts >$100k, up to ~$370k**, *before* the required Salesforce licensing; a reviewer notes "for the cost, we expected a more comprehensive and adaptable solution". [S] g2.com — accessed 2026-09-03
2. Sircon users cite a **$22.50/mo base plus per-agent cost**, "steep to small setups", one saying "the prices are insane on top of that". [S] sourceforge.net — accessed 2026-09-03
3. **Two live job ads** — "Insurance License and Compliance Coordinator" (Chicago) and "Insurance Licensing Coordinator" (Brownsville) — the manual version being hired for right now. [S] indeed.com — accessed 2026-09-03
4. Trade press, Aug 2026: "Producer compliance platforms face a new test on cost". [S] fintech.global — accessed 2026-09-03
5. Nebraska adds retaliatory non-resident fees effective **July 2026**; complexity is rising. [S] agenzee.com — accessed 2026-09-03

**Competitors.** AgentSync (quote-only, requires Salesforce, $100k+/yr); Sircon/Vertafore (base + per-producer); Advantage/XLSoft (~$40–80/producer/mo, annual contracts); State Based Systems (no public pricing).

**Bottom-up math.** `1800 / 400 = 5 customers` [ESTIMATE]. Enumerable via the **NAIC public License Manager**, state DOI licensee lookups, and Big I chapter directories.

**Clone resistance — Tier 1.** 50-state renewal calendars, CE rules and NIPR/NAIC feed handling is exactly the accumulating grind, plus a buyer segment beneath AgentSync's enterprise sales motion (Tier 2 as well).

**Steady-state: 8–10 hrs/week. Fulfilment test: PASSES.**

**The wound.** The product depends on **NIPR/NAIC data access, whose authorisation requirements and terms are unverified.** If bulk or programmatic access requires an industry authorisation a solo foreign vendor cannot obtain, the idea is dead on day one. This is a single point of failure and it is unresolved.

| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **13** | Two job ads and two pricing complaints — good, but less acute than A's documented loss |
| Distribution | 20 | **14** | NAIC License Manager and DOI lookups make prospects highly enumerable; only five needed |
| Willingness to pay | 15 | **12** | $100k+/yr contracts upmarket prove enormous spend |
| Defensibility | 10 | **7** | Tier 1: 50-state calendars and feed handling |
| Passivity ceiling | 10 | **8** | 8–10 hrs/wk |
| AI-agent buildability | 10 | **6** | **Gated on NIPR/NAIC access terms — unverified and potentially blocking** |
| Time to first customer | 8 | **5** | 3–4 months |
| Platform & regulatory risk (inverted) | 7 | **3** | Single point of failure on a data-access relationship not yet confirmed |
| **TOTAL** | **100** | **68** | ✅ Clears, but on a gated premise |

---

# Candidate C — EPR Obligation-Mapping API

**Product.** Data-only API answering "which packaging/WEEE/battery EPR registrations does product category X require in country Y, at what fee, threshold and deadline". **Explicitly not the registration service.** **Price US$300/month.**

### Evidence pack
1. "Amazon does not handle your EPR compliance"; consequences include **"listing suspension... withheld payouts... full market exclusion"**. [S] avask.com — accessed 2026-09-03
2. eBay publishes its own EPR regulation page for sellers. [S] export.ebay.com — accessed 2026-09-03
3. Fragmentation documented: a Spanish seller shipping to DE/FR/IT/NL "may need four separate EPR registrations"; France's system "takes no account of small businesses"; fees range **$10 in Germany to over $165 in France**. [S] minefieldnavigator.com — accessed 2026-09-03
4. **PPWR adds fresh obligations from 12 August 2026.** [S] tracextech.com — accessed 2026-09-03

**Competitors — and why the space is empty.** AVASK, Minefield Navigator and EPR-Register® all monetise the **manual registration service**. **NO EVIDENCE FOUND** of a self-serve data API. Per the brief's rule I must explain the emptiness rather than celebrate it: **the incumbents' business model is the explanation — selling the data would disintermediate the service they actually sell.** That is a satisfying explanation, and it is also a warning, because any of them could add a data tier defensively.

**Bottom-up math.** `1800 / 300 = 6 customers` [ESTIMATE]. Buyers: compliance managers at named 3PLs and seller aggregators — **one 3PL account represents many downstream sellers**, which is real leverage.

**Clone resistance — Tier 1 but thinner.** 10+ EU countries plus US states (California, Colorado, Oregon, Maine, Minnesota, Washington), each periodically revised. Initial build 3–4 months.

**Steady-state: 6–10 hrs/week. Fulfilment test: PASSES.**

**The wound. Licence terms are NOT confirmed for any national PRO fee schedule.** No prohibition was found, but neither was permission. For a product whose entire substance is redistributed regulatory data, that is the decisive unknown.

| Criterion | Wt | Score | Justification |
|---|---|---|---|
| Verified demand evidence | 20 | **12** | Strong consequence evidence, but **no direct "I would pay for this"** found |
| Distribution | 20 | **13** | 3PLs and aggregators enumerable; leverage via one account serving many sellers |
| Willingness to pay | 15 | **10** | Listing suspension and withheld payouts are severe; but incumbents sell service, not data |
| Defensibility | 10 | **6** | Tier 1 but thinner — regulatory facts, widely published |
| Passivity ceiling | 10 | **8** | 6–10 hrs/wk, the lowest of the three |
| AI-agent buildability | 10 | **8** | Mostly structured research and data modelling; low technical risk |
| Time to first customer | 8 | **5** | Moderate |
| Platform & regulatory risk (inverted) | 7 | **3** | **Redistribution licence unconfirmed** — the decisive unknown |
| **TOTAL** | **100** | **65** | ✅ Exactly at the bar |

---

## Round-2 scoreboard

| Candidate | Demand /20 | Distrib /20 | Pay /15 | Defens /10 | Passive /10 | Build /10 | Speed /8 | Risk /7 | **Total** |
|---|---|---|---|---|---|---|---|---|---|
| **A — Insolvency API** | 15 | 15 | 12 | 7 | 8 | 8 | 6 | 4 | **75** |
| **B — Producer licensing** | 13 | 14 | 12 | 7 | 8 | 6 | 5 | 3 | **68** |
| **C — EPR mapping API** | 12 | 13 | 10 | 6 | 8 | 8 | 5 | 3 | **65** |
| *(R1 best — NZ retention)* | *12* | *14* | *10* | *4* | *7* | *9* | *4* | *4* | *64* |

> ### **All three clear the 65 bar. Candidate A clears it by ten points.**
> Round 1 produced nothing above 64. The difference is **not** better searching — it is the constraint change. Raising the ceiling from 3 to 20 hrs/week made the maintenance-moat class available, and that is where the Tier 1 defences live. **Defensibility rose from 4/10 to 7/10**, which is the single largest movement in the whole engagement.
