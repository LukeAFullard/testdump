# 00 — Brief Review, Operator Profile & Ground Constraints

**Run date:** 2026-09-03
**Status:** Stage 0 complete (pre-fan-out review). Deliverable required by §12 of the brief.

---

## 1. Operator profile as I have read it

| Field | Value used in this run | Source |
|---|---|---|
| Capital up front | **US$300** | Assumed (field left blank) |
| Ongoing budget | **US$100/month** | Assumed (field left blank) |
| Hours during build | **8 hrs/week** | Assumed (field left blank) |
| Hours after launch | **Up to 20 hrs/week** | **REVISED by operator 2026-09-03** (was ≤3) |
| Revenue target | **NZ$3,000/month by month 12** (≈US$1,800) | **CONFIRMED by operator 2026-09-03** |
| Technical level | Can read, review and direct AI-generated code. Not hand-writing a codebase. | Stated |
| Country / tax residency | **New Zealand — for tax only** | Stated |
| Target market | **Global / online-only. Explicitly NOT New Zealand.** | **REVISED by operator 2026-09-03** |
| Existing audience | **None. Zero distribution on day one.** | Stated |
| Off the table | Physical products, inventory, on-camera work, daily social posting | Stated |

### Hard constraints carried into every decision
1. Digital only.
2. No consulting/agency — revenue must not scale with hours.
3. Buildable by an AI coding agent on conventional stacks.
4. ~~Steady-state operator load ≤3 hrs/week.~~ **Up to 20 hrs/week (revised 2026-09-03).**
5. No paid-ads dependency unless CAC payback < 3 months on the stated budget.
6. Avoid regulated data unless the regime and cost are named.

---

## 2. Assumptions I am making where fields were blank

| # | Assumption | Why it matters | If wrong, tell me |
|---|---|---|---|
| A1 | Budget figures are **USD**, not NZD | US$300/NZ$500 vs NZ$300 changes almost nothing at this scale | Low impact |
| ~~A2~~ | ~~Revenue target currency~~ | **RESOLVED 2026-09-03: the target is NZ$3,000/month (≈US$1,800).** This is a 40% lower bar than assumed and materially widens the viable candidate set — see the revised arithmetic in `03-deep-dives.md` | **Resolved** |
| A3 | "Month 12" counts from first build week, not from first revenue | Sets the kill-gate calendar in the build plan | Medium |
| A4 | The ≤3 hrs/week ceiling applies at **steady state**, not during months 1–12 | See critique C1 — as written the ceiling is not achievable during the growth year | Assumed, unchallenged |
| ~~A5~~ | ~~Willingness to do cold outreach~~ | **RESOLVED 2026-09-03: yes — compliant cold email and occasional trade-forum posting are both acceptable.** This keeps ranked channels #2 and #3 live and is the difference between having a distribution plan and not having one | **Resolved** |
| A6 | You will register a NZ company or operate as a sole trader, and will use a Merchant of Record | See §4 — this is close to forced for a solo NZ seller | Medium |
| ~~A7~~ | ~~Geography open~~ | **SUPERSEDED 2026-09-03: geography is not merely open, NZ is excluded.** The business must be global and online-only, not tied to any local market. See §6 | **Resolved** |
| **A8** | **Steady-state ceiling raised from 3 to 20 hrs/week** | **RESOLVED 2026-09-03.** This is the largest single change in the whole engagement and it inverts several earlier conclusions. See §6 | **Resolved** |

---

## 3. What I think is wrong or self-defeating in the brief

I was asked to flag this, so I am being direct. The brief is unusually well-constructed — the §4 tension, the "empty market is a red flag" rule and the "write the bear case first" rule are all correct and most briefs of this kind get them wrong. The problems below are real but mostly fixable.

### C1 — The revenue target and the passivity ceiling are in direct conflict during year 1
US$3,000/month by month 12, from zero audience, with no paid ads, no social media, no personal brand and no sales calls, at ≤3 hrs/week, is not one constraint set — it is two. Every cheap acquisition channel available to a no-audience founder is a **labour** channel in its early months (manual outreach, community participation, marketplace listing optimisation, content). The ≤3 hrs/week ceiling is achievable *at steady state on a product that has already found its channel*. It is not achievable *while finding the channel*.
**Resolution I have adopted:** treat ≤3 hrs/week as a Phase 5 exit criterion, not a Phase 0–4 operating constraint, and be explicit in the build plan about what the real hours are in each phase. If the ≤3 hrs/week ceiling is genuinely binding from day one, then the honest answer is that US$3,000/month in 12 months is not reachable and the target should drop to roughly US$500–1,000/month. I would rather say that now than discover it in month 9.

### C2 — The exclusion list removes almost every fast distribution channel
No paid ads, no social, no personal brand, no on-camera, no daily posting, no consulting. What remains: platform-marketplace search, SEO/LLM-citation, cold outbound email, integration/partner directories, niche communities, and association/trade channels. That is a short list, and at least one of those (SEO) may be structurally impaired in 2026 — I have a dedicated agent testing exactly that. **Distribution, not product, is the binding constraint on this venture**, and I have weighted my thinking accordingly.

### C3 — The rubric says "nine criteria"; the table has eight
The eight listed weights sum correctly to 100 (20+20+15+10+10+10+8+7). I will score on the **eight given**, and note it rather than invent a ninth.

### C4 — A self-assigned score out of 100 is not evidence
I choose the numbers, so I can produce any total I like, and a 65-point bar invites me to score candidates *to* the bar. I will therefore (a) score conservatively, (b) treat the evidence pack as the real deliverable and the score as a summary device, and (c) state plainly if nothing clears 65 rather than nudging a 61 upward. You should read the evidence, not the total.

### C5 — "Clone resistance" is worth less than the brief hopes, and that is survivable
For a business this size the honest moat is usually not defensibility in the strategic sense. It is that **the market is too small to be worth a serious competitor's time**. That is a real and durable protection — and it is also precisely why such a business caps out somewhere between US$3k and US$10k/month. Those two facts are the same fact. Any candidate that claims both a large market *and* clone resistance at solo scale deserves suspicion.

### C6 — "Validated" as defined cannot be fully satisfied by a research run
Your definition requires real humans at real URLs expressing the need. I can find people *describing the pain*. I cannot confirm they will pay you, and no amount of desk research substitutes for that. Everything in these documents is **pre-validation**. Phase 0 exists to do the real thing, and I have made it a hard gate.

### C7 — Minor: "first paying customer" and "no sales calls" sit awkwardly together
Nearly every B2B micro-SaaS acquires its first ~10 customers manually. That is not consulting and does not violate the linear-revenue rule, but it does mean the first customers will cost real hours. I have planned for that rather than pretending otherwise.

---

## 4. Ground constraints for a New Zealand operator (cross-cutting — applies to every candidate)

All figures accessed **2026-09-03**. Evidence tier: **[S]** = seen in a web-search result summary with a real URL; **[I]** = my inference. **I could not open pages directly in this environment (see §5), so nothing below is tier-verified by my own reading of the primary page.** Treat as strong-but-unconfirmed. Confirm with an accountant before relying on it.

### 4.1 Payments — Stripe is available; a Merchant of Record is probably still the right call
- Stripe operates in New Zealand via a NZ-registered entity, supports NZD, and pays out in ~2 business days. [S] — https://support.stripe.com/questions/stripe-service-provider-in-new-zealand , https://stripe.com/nz/global
- Paddle sells into 200+ countries as Merchant of Record and calculates, collects and remits tax, leaving the seller with no sales-tax liability on Paddle transactions. [S] — https://developer.paddle.com/concepts/sell/supported-countries-locales/
- **A New Zealand company (Matomo) is a documented Paddle customer**, which is direct evidence the NZ→Paddle path works in practice. [S] — https://www.paddle.com/customers/matomo-saved-dev-time
- Paddle and Lemon Squeezy both charge around **5% + $0.50 per transaction**. [S] — https://www.lemonsqueezy.com/reporting/merchant-of-record , https://dodopayments.com/blogs/eu-vat-saas-guide-2026

### 4.2 Sales tax — this is the finding that shapes the whole strategy
- **New Zealand:** GST registration required once taxable turnover exceeds **NZD 60,000** in any 12-month period. Services exported to customers outside NZ are **zero-rated**. [S] — https://www.avalara.com/us/en/vatlive/country-guides/oceania/new-zealand/new-zealand-gst-registration.html , https://taxsummaries.pwc.com/new-zealand/corporate/other-taxes
- **United Kingdom:** there is **no registration threshold for non-established sellers** of B2C digital services — VAT is due from the *first* sale. The £90,000 threshold applies only to UK-established businesses. [S] — https://www.anrok.com/vat-software-digital-services/united-kingdom , https://businassist.com/blog/non-established-taxable-person-uk-vat-registration/
- **European Union:** a non-EU seller of B2C digital services has **no threshold** — obligations start at the first euro. Non-Union OSS allows one registration covering all member states. **B2B sales to a VAT-registered EU business use the reverse charge — you collect nothing.** [S] — https://dodopayments.com/blogs/eu-vat-saas-guide-2026 , https://fungies.io/eu-vat-oss-scheme-saas/
- **United States:** economic nexus is typically **US$100,000** per state (41 states), and SaaS taxability varies by state. [S] — https://www.numeral.com/blog/economic-nexus , https://taxcloud.com/blog/sales-tax-nexus-by-state/

### 4.3 Two conclusions I will carry into every candidate

> **CONCLUSION 1 — Sell B2B, not B2C.**
> The UK nil threshold and the EU first-euro rule mean a NZ solo operator selling B2C digitally is in immediate multi-jurisdiction tax scope. Selling **B2B** puts EU sales under reverse charge and keeps the compliance surface far smaller. This reinforces the brief's own B2B preference for an independent, structural reason.

> **CONCLUSION 2 — Use a Merchant of Record (Paddle or Lemon Squeezy), not raw Stripe.**
> ~5% + $0.50 is the correct price to pay to make the §4.2 problem someone else's. At US$3,000/month that is roughly **US$150/month plus per-transaction fees** [ESTIMATE: 5% × $3,000 = $150; plus $0.50 × ~60 transactions ≈ $30; total ≈ **$180/month**]. Budget it from day one. Raw Stripe is only sensible if sales are overwhelmingly NZ/AU B2B.

### 4.4 Company setup
- NZ company incorporation is approximately **NZD 118.74 + GST (≈NZD 136.55)**, plus ~NZD 10 + GST to reserve a name. No minimum share capital. [S] — https://companies-register.companiesoffice.govt.nz/help-centre/starting-a-company/incorporating-a-company/ , https://www.mbie.govt.nz/business-and-employment/business/regulating-entities/review-of-new-zealand-companies-office-fees-and-levies-2025/discussion-document-review-of-new-zealand-companies-office-fees-and-levies-2025/section-5-proposed-fees-and-total-charges-for-all-registers
- **[I]** Comfortably inside the US$300 budget. A sole trader is cheaper still; a company is the safer default once customers exist.

### 4.6 Geography is open — and a Merchant of Record is what makes that true

**Confirmed 2026-09-03: the business does not have to target New Zealand customers.**

This is less of a loosening than it first appears, and more of one in a different direction:
- **Tax does not constrain geography, because Paddle absorbs it.** The UK nil-threshold and EU first-euro problems in §4.2 are exactly what a Merchant of Record exists to solve. Selling B2B through Paddle, the operator can sell into the UK, EU, US or Australia without registering anywhere. My earlier lean toward NZ-domestic selling was partly belt-and-braces and should be relaxed.
- **Timezone still constrains geography**, and this is the binding one. See §4.5 — async-only support is fine anywhere, but anything needing responsiveness is limited to AU/NZ.
- **Credibility still favours the home market for a first product.** Being a local vendor is worth something when selling compliance software to a trust-sensitive buyer, and it costs nothing to start there and expand.

**Net effect on strategy:** start where credibility is cheapest, then expand to the largest market that shares the timezone. Do not treat NZ as a ceiling.

### 4.5 Timezone — a real constraint, and a partial advantage
**[I]** NZ is UTC+12/+13. Auckland business hours have **near-zero overlap with US business hours and almost none with EU**. Australia (2–4 hrs behind) is the only major market with genuine working overlap.
**Implication:** any candidate requiring same-day interactive support, live onboarding, or sales calls into the US or EU is **disqualified for this operator**. Candidates whose support is genuinely async (docs, email, 24h SLA) are unaffected — and a 24h async SLA is entirely normal for low-priced B2B tools. AU/NZ-focused candidates gain a real advantage here.

---

## 5. Research-environment limitation — disclosed because it affects evidence quality

This session's egress policy **blocks all direct page fetching**. Verified 2026-09-03: `WebFetch` returns `EGRESS_BLOCKED`, and `curl` receives `HTTP 403` on CONNECT for every external host tested (`ird.govt.nz`, `gov.uk`, `reddit.com`). Only `WebSearch` functions.

**Consequence for §6 (Evidence Standard) and §10 (Anti-Slop Rules) of the brief:**
- I can supply **real URLs and search-summarised page content**.
- I **cannot** open a page to quote a review verbatim, confirm a live pricing tier, count reviews, or read a licence in full.
- Therefore I will **not** present verbatim quotes from reviews or forum posts, because I cannot confirm the wording. Paraphrase marked **[S]** is the honest maximum.

Evidence tiers used throughout these documents:
- **[S]** — appeared in a web-search result: real URL, content summarised by the search tool.
- **[I]** — my own inference or arithmetic. **Not evidence.**
- **[ESTIMATE]** — a derived number, with the arithmetic shown.
- **[UNVERIFIED]** — asserted somewhere but I could not corroborate it.
- **NO EVIDENCE FOUND** — I looked and found nothing. A legitimate result.

Anything marked **[S]** should be re-checked by opening the page before you act on it. This is a genuine downgrade against the brief's stated standard and I would rather name it than paper over it.

---

## 6. The 2026-09-03 constraint revision — and why it changes the answer, not just the numbers

Three changes arrived together: **forget NZ; online-only; up to 20 hrs/week.** The third is not a loosening of a parameter. It reverses the selection logic that produced the earlier recommendation.

### 6.1 The 3-hour ceiling was systematically selecting against the only available moats

Look at what the old ceiling actually killed, from `02-kill-log.md` and `01-longlist.md`:
- US restaurant health-inspection data — killed on **scraper maintenance**
- QuickBooks↔Shopify reconciliation patch — killed partly on **two-API maintenance load**
- AU Payday Super — killed partly on **3–4 hrs/week**, over the ceiling
- Funeral homes, marinas, driving schools — killed on **support load**
- Any per-jurisdiction data aggregation — killed on **ongoing upkeep**

Now notice what those all have in common: **the maintenance burden that disqualified them is the same property that would have defended them.** A competitor with identical AI coding tools can clone a feature in three weeks. What they will not do is maintain 60 jurisdiction-specific scrapers, or keep a duty-rate table current every week, for two years. **Grind is the one moat an AI coding agent does not erase**, and the old ceiling forbade exactly that.

> **This is the central resolution of the brief's §4 tension.** The answer to "what stops someone cloning this in three weeks" is not cleverness or first-mover advantage. It is accumulated, boring, ongoing work that a cloner would have to redo and then sustain. At 3 hrs/week that answer was unavailable. At 20 hrs/week it is the strategy.

### 6.2 The target is now genuinely small, which changes what to look for

At NZ$3,000/month (~US$1,800):

| Price point | Customers needed | New customers/month to get there in 12 mo |
|---|---|---|
| US$29/mo | 62 | ~7 |
| US$100/mo | 18 | ~2 |
| **US$300/mo** | **6** | **~0.7** |
| US$500/mo | 4 | ~0.5 |

[ESTIMATE, 5% monthly churn, model in `03-deep-dives.md`]

> **Six customers.** At US$300/month the entire twelve-month goal is six paying businesses. That is not a marketing problem; it is a "find six companies with an expensive problem" problem — and with 20 hrs/week available for manual outreach, it is very tractable.
>
> **Strategic consequence: hunt for expensive problems affecting enumerable buyers, not large addressable markets.** Vendors whose pricing is sales-quote-only are the signal, because opaque enterprise pricing means they ignore anyone small — while the small firms still have the problem.

### 6.3 Where the "no consulting" line now sits

Raising the ceiling to 20 hrs/week creates real tension with hard constraint 2 (*revenue must not scale linearly with hours*). The line I am applying:

- **Allowed:** manual prospecting and sales, hands-on onboarding of early customers, data and scraper maintenance, support. These do not scale with customer count in a fixed ratio and are normal for early B2B.
- **Not allowed:** per-customer fulfilment — the operator personally producing each customer's output every month. That is an agency with a login page, and it fails the brief regardless of hours available.

**Test to apply to every candidate: if customer number seven arrives, does the operator's monthly workload rise by a fixed, unavoidable per-customer amount?** If yes, reject.

### 6.4 What this invalidates from the earlier work
- **The recommendation is dead.** The NZ construction retention-money ledger was built on NZ statute and sold through NZ trade associations. "Forget NZ" removes both. `04-recommendation.md` is superseded.
- **The Australia expansion path dies with it** — same reason.
- **The passivity criterion (10 points) is now near-uniformly satisfied**, so it stops discriminating between candidates and the effective rubric narrows to seven meaningful criteria.
- **Several Stage 3 kills should be reconsidered**, specifically those killed on maintenance or support load rather than on demand or competition.

### 6.5 What it does NOT change
- Generic SEO is still not a viable channel (`research/distribution-findings.md`).
- Churn at low price points is still 6–8.6% monthly — another argument for pricing high.
- Base rates are still hostile: 54% of indie products earn $0; median micro-SaaS ~US$500/month.
- NZ tax residency still applies: **sell B2B, use a Merchant of Record.** §4.2 and §4.3 stand unchanged. Selling globally is precisely what Paddle exists to make safe.
- Timezone still rules out anything needing same-day interactive support or live sales calls into the US or EU.

---
