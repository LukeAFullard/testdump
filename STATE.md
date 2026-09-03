# STATE.md — Project Resume File

> **Purpose.** Any future agent session should be able to read this file alone and continue without the operator re-explaining anything. **Update it at the end of every working session.** If it is stale, it is worse than useless.

---

## Current status

| Field | Value |
|---|---|
| **Project** | **GazetteFeed (placeholder) — Multi-Jurisdiction Corporate Insolvency / Distress-Event API** |
| **Current phase** | **Phase 0 — Verify the licences. NOT STARTED.** |
| **Last updated** | 2026-09-03 (second revision) |
| **Updated by** | Research run (Claude Code session) |
| **Next action** | **Read the actual text of three licences** — Licence Ouverte 2.0 (FR), OGL v3.0 (UK), Law 37/2007 (ES). Every licence claim in this repo is an unverified search snippet, and this single check can end the project. |
| **Overall confidence** | **Moderate-to-good. Scored 75/100 against a 65 bar** — the first candidate in the engagement to clear it, and by ten points. |

## ✅ ROUND 2 COMPLETE — a candidate cleared the bar

**Selected: a normalised, real-time API of corporate insolvency filings from national gazettes.** Launch **France → UK → Spain**; **Germany deliberately excluded** (active dispute between German DPAs and the NRW Ministry of Justice over private republication). Buyers: credit-risk teams, trade-credit insurers, factoring firms. **US$300/month — six customers is the whole twelve-month target.**

**Why it won:** the only candidate with real user-voice evidence (a GitHub request open since June 2024; a documented **€40,000** loss from an API that missed a filing by 11 days), and a **Tier 1 time-accumulated moat demonstrated rather than argued** — three developers built the same German scraper and abandoned it, one listing now marked DEPRECATED. Nothing stops a cloner building it; the evidence says they stop maintaining it.

**Read `04-recommendation.md` bear case first.** Chief risks: three competitors already entered in ~18 months; Germany excluded; **and every licence claim in this repo rests on search snippets because page-fetching was blocked all session.**

## 🔴 ROUND 1 IS SUPERSEDED — historical record only

On 2026-09-03 the operator revised three constraints:
1. **Forget New Zealand.** No NZ-specific product, no NZ market.
2. **Global / online-only business.** Not tied to any local market or physical-world industry.
3. **Steady-state ceiling raised from 3 to 20 hrs/week.**

Round 1's files are preserved as `04-recommendation-ROUND1-SUPERSEDED.md` and `05-build-plan-ROUND1-SUPERSEDED.md`. **Changes 1 and 2 killed that recommendation outright** — the NZ construction retention-money ledger rested on NZ statute and was to be sold through NZ trade associations. Both foundations are gone. `04-recommendation.md` and `05-build-plan.md` are **historical records, not live plans.**

**Change 3 is the most consequential of the whole engagement** and is analysed in `00-brief-review.md` §6. In short: the 3-hour ceiling was systematically selecting *against* the only durable moat available to a solo operator — accumulated maintenance work that a cloner with the same AI tools will not sustain. At 20 hrs/week that class of business is open.

**Also note the target is now tiny.** At NZ$3,000/month: ~18 customers at US$100/mo, or **six at US$300/mo**. The problem is no longer "build a passive funnel" but "find six businesses with an expensive problem" — which favours high prices and enumerable, hard-to-reach buyers.

---

## The one-paragraph brief

A NZ-resident solo operator, building with an AI coding agent, wants a software business reaching **NZ$3,000/month by month 12** on ~US$300 upfront and ~US$100/month, working 8 hrs/week to build and **≤3 hrs/week at steady state**, with **zero audience**, no paid ads, no social media, no personal brand, and no sales calls. **Geography is open and compliant cold email plus trade-forum posting are acceptable.** The chosen candidate is a narrow compliance tool for construction businesses that hold retention money: it maintains the legally-required separate trust ledger and generates the mandatory quarterly subcontractor report. **It never touches the money.** Price NZ$149/month. **21 customers = target.** NZ first, Australia in year two.

---

## Decisions made, and why

| Decision | Reasoning | Where |
|---|---|---|
| **Sell B2B, never B2C** | UK has a **nil VAT threshold** for non-established sellers; the EU charges from the **first euro** on B2C digital services. B2B in the EU is reverse-charged — you collect nothing. **Unchanged by the geography revision** — selling globally is exactly what a Merchant of Record makes safe. | `00-brief-review.md` §4.2 |
| **Price high: US$300/mo, not US$29** | At NZ$3,000/month the target is six customers at US$300 versus 62 at US$29, and churn improves above the US$50 line. | `00-brief-review.md` §6.2 |
| **Prefer maintenance-heavy products** | Grind is the one moat an AI coding agent does not erase. Newly available at 20 hrs/week. | `00-brief-review.md` §6.1 |
| **A bad expensive incumbent is no longer evidence of an opening** | Four spot checks today each found 2–4 self-serve entrants already occupying the gap below the enterprise incumbent. | `research/revised-constraint-spot-checks.md` |
| **Use Paddle (Merchant of Record), not raw Stripe** | ~5% + $0.50 is the correct price to make multi-jurisdiction sales tax someone else's problem. A NZ company (Matomo) is a documented Paddle customer. | `00-brief-review.md` §4.1 |
| **Price at NZ$149/mo, not NZ$79** | Cuts customers needed from 38 to 21 *and* lowers churn by crossing the US$50 threshold, cutting required monthly acquisition from 4.4 to 2.3. Test NZ$199 (16 customers). | `03-deep-dives.md` |
| **NZ first, Australia year two** | NZ is cheapest for credibility and shares the timezone; AU is ~5× the market. Conditional on Phase 0 confirming a comparable AU retention regime — currently only a competitor's unverified marketing claim. | `03-deep-dives.md` |
| **No Xero integration until Phase 4** | Xero replaced its 15% revenue share with tenant+egress pricing on **2 Mar 2026**; one developer's bill went from ~$0 to **>$17,000/year**. CSV-first avoids this exposure until the product is proven. | `research/platform-marketplace-findings.md` |
| **Never touch or custody funds** | Crossing that line pulls the business into NZ Financial Service Providers Act 2010 and AML/CFT Act 2009 scope. | `03-deep-dives.md` |
| **First channel = trade associations, not SEO** | Generic SEO is not viable for a zero-authority site in 2026: **68.01% of US Google searches end with no click**; 8% click-through when an AI Overview is present. | `research/distribution-findings.md` Finding 1 |
| **Cold outreach must use deemed consent** | NZ's **Unsolicited Electronic Messages Act 2007** is consent-based, not opt-out like CAN-SPAM. Penalties to **NZ$500,000**. Publicly-published business addresses + role-relevant message only. | `research/distribution-findings.md` Finding 4 |
| **≤3 hrs/week is a Phase 5 exit criterion, not a build constraint** | Phases 0–4 realistically need 6–8 hrs/week. Pretending otherwise makes the plan undeliverable. | `00-brief-review.md` §C1 |
| **Candidates B and C were rejected but documented** | B (AU Payday Super) is being absorbed by Xero/MYOB now. C (Xero egress monitor) has the best pain evidence and the worst structural position. | `04-recommendation.md` |

---

## Open questions — ranked by how much they matter

1. **🔴 DECISIVE: Do the three licences actually permit commercial redistribution of corporate insolvency notices?** France's Licence Ouverte 2.0, the UK's OGL v3.0 (**personal data expressly excluded**) and Spain's Law 37/2007. **Every claim about these in this repo came from a search snippet, not the licence text.** Any prohibition → stop.
2. **🔴 Is the German restriction local or a direction of travel?** German DPAs are working with the NRW Ministry of Justice to make private republication harder. If EU-wide, the category is a melting iceberg.
3. **🟠 What do Prometiam and Insolvencies.live actually charge, cover and how fast are they?** Neither publishes pricing. If they are already fast, cheap and well-covered, you are fourth with no edge.
4. **🟠 Do credit-risk buyers report learning about filings too late?** Need ≥4 of 10 interviewees confirming, or naming a loss.
5. **🟠 Can a solo vendor obtain professional indemnity insurance and enforceable limitation of liability?** Customers extend credit on this data.
6. **🟡 Never reached in any round:** trades certification tracking, self-storage, commercial cleaning, equipment hire.

### ✅ Resolved by the operator on 2026-09-03
- **Revenue target is NZ$3,000/month** (≈US$1,800), not US$3,000. Cut required acquisition from 3.7 to 2.3 customers/month and lowered the TAM threshold from ~1,500 to ~800. Worth +1 on demand evidence.
- **Geography is open** — the business need not target NZ customers. Paddle (MoR) absorbs the multi-jurisdiction tax problem, so this is a genuine loosening; only timezone still constrains.
- **Compliant cold email and occasional trade-forum posting are acceptable.** Keeps ranked channels #2 and #3 live. Worth +1 on distribution.

---

## Metrics to date

*Nothing built, nothing sold. All zero. Populate as the project runs.*

| Metric | Current | Target | Phase gate |
|---|---|---|---|
| Licence texts read in full | 0 | 3 | Phase 0 |
| Legal opinion obtained | No | Yes | Phase 0 |
| Interviews completed | 0 | 10 | Phase 0 |
| Interviewees reporting late notice | 0 | ≥4 | Phase 0 |
| Outreach replies | 0 | 12 | Phase 1 |
| Unprompted pricing/access enquiries | 0 | 4 | Phase 1 |
| Jurisdictions live | 0 | 3 (FR/UK/ES) | Phase 4 |
| Median notice-to-API latency | — | <24 hrs | Phase 4 |
| Paying customers | 0 | **6** | Phase 4 |
| Monthly churn | — | <5% | Phase 4 |
| Operator hrs/week (measured) | — | ≤15 | Phase 5 |
| MRR | NZ$0 | NZ$3,000 (6 customers) | Phase 6 |

---

## ⚠️ Health warnings for any future session

1. **No claim in this repository was verified by opening a source page.** The research session's egress proxy blocked all page fetching (403 CONNECT on every host) and the web-search budget was exhausted at 200/200. Every citation came from a search-result summary. **Re-verify anything before acting on it.** Evidence tiers: **[S]** search summary, **[I]** inference, **[ESTIMATE]** derived arithmetic, **NO EVIDENCE FOUND**.
2. **The search was never finished.** Notion, Figma, Monday.com, Airtable, Webflow, trades certification trackers, self-storage, commercial cleaning and equipment hire were never examined. **No primary Reddit or forum thread content was retrievable at all** — a real shortfall against the brief's evidence standard. Re-running discovery with fetching enabled is arguably higher-value than building.
3. **This candidate scored 64 against a 65 bar.** It is the best of a weak field, not a strong find, and **defensibility (4/10) will never improve** — no amount of validation fixes that. `04-recommendation.md` leads with the bear case; read that before the bull case.
4. **The base rates are hostile.** 54% of tracked indie products earn $0; 70% of micro-SaaS earn under US$1,000/month; median ~US$500/month. NZ$3,000 ≈ US$1,800/month — still an above-median, roughly top-quartile outcome. Budget **12–18 months**, not 12.
5. **Churn is the silent killer.** Sub-US$50/month customers churn at **6–8.6% monthly**. This is why the price is NZ$149 and not NZ$79.
6. **Every phase has a kill criterion. Honour them.** The most common failure mode in the post-mortem literature is not a bad idea — it is continuing past the point where the numbers said stop.

---

## File map

| File | Contents |
|---|---|
| `00-brief-review.md` | Operator profile, assumptions, critique of the brief, **NZ payment/tax/timezone constraints** |
| `01-longlist.md` | 44 candidates with theses and signals |
| `02-kill-log.md` | The cull to 8, and six kill attempts with reasoning |
| `03-deep-dives.md` | Evidence packs, churn arithmetic and rubric scores for the final 3 |
| `04-recommendation.md` | **Bear case first**, then the case for, runner-up conditions, and what research would change the answer |
| `05-build-plan.md` | Six phases with acceptance and kill criteria |
| `STATE.md` | This file |
| `research/distribution-findings.md` | **Read first.** SEO viability, ranked channels, NZ cold-email law |
| `research/ground-truth-findings.md` | Base rates, churn, platform rug-pulls, **the 8 kill questions** |
| `research/regulation-findings.md` | Regulatory candidates and rejections |
| `research/platform-marketplace-findings.md` | Xero/Intuit/Shopify/Atlassian marketplace economics |
| `research/data-and-rebuild-findings.md` | Data products, licences, MCP assessment |

---

## Session log

| Date | What happened | Next |
|---|---|---|
| 2026-09-03 | Full discovery run. 44 candidates longlisted, culled to 8, 6 killed, 3 deep-dived. **Nothing cleared the 65 bar; best was 62.** Conditional recommendation made with a hard Phase 0 gate. Research degraded by blocked page-fetching and an exhausted search budget. | Operator to confirm target currency, geography and outreach willingness. |
| 2026-09-03 (rev) | Operator confirmed **NZ$3,000 target, open geography, outreach acceptable**. All arithmetic and scores revised: winner **62 → 64**, required acquisition **3.7 → 2.3/month**, TAM threshold **1,500 → 800**. Australia added as year-two market pending Phase 0 verification. | **Run Phase 0, interviews first.** |
