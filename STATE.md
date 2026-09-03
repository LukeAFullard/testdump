# STATE.md — Project Resume File

> **Purpose.** Any future agent session should be able to read this file alone and continue without the operator re-explaining anything. **Update it at the end of every working session.** If it is stale, it is worse than useless.

---

## Current status

| Field | Value |
|---|---|
| **Project** | RetentionLedger (placeholder) — NZ construction retention-money trust compliance ledger |
| **Current phase** | **Phase 0 — Validate before building. NOT STARTED.** |
| **Last updated** | 2026-09-03 |
| **Updated by** | Research run (Claude Code session) |
| **Next action** | **Resolve the TAM denominator: how many NZ businesses hold retention money?** Nothing else matters until this is answered. |
| **Overall confidence** | **Low-to-moderate.** Scored 62/100 against a 65 bar. Proceeding is conditional on Phase 0. |

---

## The one-paragraph brief

A NZ-based solo operator, building with an AI coding agent, wants a software business reaching **US$3,000/month by month 12** on ~US$300 upfront and ~US$100/month, working 8 hrs/week to build and **≤3 hrs/week at steady state**, with **zero audience**, no paid ads, no social media, no personal brand, and no sales calls. The chosen candidate is a narrow compliance tool for NZ construction businesses that hold retention money: it maintains the legally-required separate trust ledger and generates the mandatory quarterly subcontractor report. **It never touches the money.** Price NZ$149/month.

---

## Decisions made, and why

| Decision | Reasoning | Where |
|---|---|---|
| **Sell B2B, never B2C** | UK has a **nil VAT threshold** for non-established sellers; the EU charges from the **first euro** on B2C digital services. B2B in the EU is reverse-charged — you collect nothing. | `00-brief-review.md` §4.2 |
| **Use Paddle (Merchant of Record), not raw Stripe** | ~5% + $0.50 is the correct price to make multi-jurisdiction sales tax someone else's problem. A NZ company (Matomo) is a documented Paddle customer. | `00-brief-review.md` §4.1 |
| **Price at NZ$149/mo, not NZ$79** | Halves the customers needed (34 vs 64) *and* lowers churn, cutting required monthly acquisition from 7.3 to 3.7 — a 49% reduction in the hardest part of the job. | `03-deep-dives.md` |
| **No Xero integration until Phase 4** | Xero replaced its 15% revenue share with tenant+egress pricing on **2 Mar 2026**; one developer's bill went from ~$0 to **>$17,000/year**. CSV-first avoids this exposure until the product is proven. | `research/platform-marketplace-findings.md` |
| **Never touch or custody funds** | Crossing that line pulls the business into NZ Financial Service Providers Act 2010 and AML/CFT Act 2009 scope. | `03-deep-dives.md` |
| **First channel = trade associations, not SEO** | Generic SEO is not viable for a zero-authority site in 2026: **68.01% of US Google searches end with no click**; 8% click-through when an AI Overview is present. | `research/distribution-findings.md` Finding 1 |
| **Cold outreach must use deemed consent** | NZ's **Unsolicited Electronic Messages Act 2007** is consent-based, not opt-out like CAN-SPAM. Penalties to **NZ$500,000**. Publicly-published business addresses + role-relevant message only. | `research/distribution-findings.md` Finding 4 |
| **≤3 hrs/week is a Phase 5 exit criterion, not a build constraint** | Phases 0–4 realistically need 6–8 hrs/week. Pretending otherwise makes the plan undeliverable. | `00-brief-review.md` §C1 |
| **Candidates B and C were rejected but documented** | B (AU Payday Super) is being absorbed by Xero/MYOB now. C (Xero egress monitor) has the best pain evidence and the worst structural position. | `04-recommendation.md` |

---

## Open questions — ranked by how much they matter

1. **🔴 DECISIVE: How many NZ businesses hold retention money?** Unknown. Under 800 → **stop**. Above ~1,500 → the score likely clears the 65 bar. *This is Phase 0's first job.*
2. **🔴 Is the revenue target US$3,000 or NZ$3,000/month?** NZ$3,000 ≈ US$1,800 — roughly 20 customers instead of 34, which would likely push the candidate above the bar on its own. **Ask the operator.**
3. **🟠 Do real NZ contractors find the quarterly obligation painful?** Demand is currently inferred from statute, with **zero user-voice evidence**. Fewer than 3 of 10 interviewees describing pain → stop.
4. **🟠 What do Retention Track, Payapps, Gojee and Workbench charge?** No pricing was obtainable for any of them.
5. **🟠 Is the operator willing to send compliant cold email and post in forums?** Assumption A5. If not, the viable channel set collapses to marketplace search alone.
6. **🟡 Exact commencement and current obligations under the Construction Contracts (Retention Money) Amendment Act 2023.** Not verified.
7. **🟡 Does Xero or a major NZ construction platform have retention-trust compliance on a roadmap?** Would fire kill-question 3.

---

## Metrics to date

*Nothing built, nothing sold. All zero. Populate as the project runs.*

| Metric | Current | Target | Phase gate |
|---|---|---|---|
| Interviews completed | 0 | 10 | Phase 0 |
| TAM sources found | 0 | 2 | Phase 0 |
| Email signups | 0 | 25 | Phase 1 |
| Unprompted "when can I buy" replies | 0 | 5 | Phase 1 |
| Paying customers | 0 | 1 | Phase 3 |
| New paying customers/month | 0 | 3.7 | Phase 4 |
| Monthly churn | — | <6% | Phase 4 |
| Operator hrs/week (measured) | — | ≤3 | Phase 5 |
| MRR | US$0 | US$3,000 | Phase 6 |

---

## ⚠️ Health warnings for any future session

1. **No claim in this repository was verified by opening a source page.** The research session's egress proxy blocked all page fetching (403 CONNECT on every host) and the web-search budget was exhausted at 200/200. Every citation came from a search-result summary. **Re-verify anything before acting on it.** Evidence tiers: **[S]** search summary, **[I]** inference, **[ESTIMATE]** derived arithmetic, **NO EVIDENCE FOUND**.
2. **The search was never finished.** Notion, Figma, Monday.com, Airtable, Webflow, trades certification trackers, self-storage, commercial cleaning and equipment hire were never examined. **No primary Reddit or forum thread content was retrievable at all** — a real shortfall against the brief's evidence standard. Re-running discovery with fetching enabled is arguably higher-value than building.
3. **This candidate scored 62 against a 65 bar.** It is the best of a weak field, not a strong find. `04-recommendation.md` leads with the bear case; read that before the bull case.
4. **The base rates are hostile.** 54% of tracked indie products earn $0; 70% of micro-SaaS earn under US$1,000/month; median ~US$500/month. US$3,000/month is a top-10–20% outcome. Budget **12–18 months**, not 12.
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
| 2026-09-03 | Full discovery run. 44 candidates longlisted, culled to 8, 6 killed, 3 deep-dived. **Nothing cleared the 65 bar; best was 62.** Conditional recommendation made with a hard Phase 0 gate. Research degraded by blocked page-fetching and an exhausted search budget. | **Operator to confirm the currency of the revenue target, then run Phase 0.** |
