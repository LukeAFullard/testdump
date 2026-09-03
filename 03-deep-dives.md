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
