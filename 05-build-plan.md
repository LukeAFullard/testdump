# 05 — Phased Build Plan (Round 2)
## Multi-Jurisdiction Corporate Insolvency / Distress-Event API

*Round 1's plan is preserved as `05-build-plan-ROUND1-SUPERSEDED.md`.*

**Working name:** GazetteFeed (placeholder)
**Buyer:** credit-risk teams, trade-credit insurers, factoring and invoice-finance firms, procurement risk
**Price:** **US$300/month** from the first invoice. Do not launch cheap and hope to raise.
**Target:** NZ$3,000/month ≈ **six customers** ≈ one every seven weeks
**Coverage at launch:** **France (BODACC) → UK (The Gazette) → Spain (BORME).** **Germany excluded** until the NRW dispute resolves.
**Payments:** Paddle (Merchant of Record) — B2B, reverse-charge in the EU, no VAT registration needed by you.
**Hours:** 8/week build; **up to 20/week ongoing** — of which 8–12 is the maintenance that constitutes the moat.

> **The non-negotiable rule of this plan: the product asserts what a public register published and when. It never asserts that a company is solvent.** That distinction is the difference between a data feed and an uninsurable credit opinion.

---

## Phase 0 — Verify the licences. Nothing else matters first.
### No code. No landing page. This gate can end the project in a week.

**Objective.** Establish that commercially redistributing corporate insolvency notices from France, the UK and Spain is lawful, and that buyers feel the pain.

**Deliverables**
1. `research/licences.md` — the **actual text** of Licence Ouverte 2.0 (France), OGL v3.0 (UK) and Spain's Law 37/2007 reuse conditions, read directly rather than via search summary, with the specific clauses permitting commercial redistribution quoted and linked. **Everything in this repo about these licences came from search snippets because page-fetching was blocked; none of it is good enough to build on.**
2. `research/legal-opinion.md` — a paid short-form opinion from an EU data-protection or PSI-reuse lawyer covering: (a) commercial redistribution of corporate insolvency notices in FR/UK/ES; (b) whether the German restriction signals contagion; (c) the UK OGL personal-data exclusion and whether corporate notices sit clearly outside it.
3. `research/competitors.md` — signed-up accounts with **Prometiam** and **Insolvencies.live**: real pricing, coverage, latency, data shape. Plus getregdata's per-result economics.
4. `research/interviews.md` — **10 conversations** with credit-risk or trade-credit underwriting staff. Script: *"Walk me through the last time you found out a European customer had filed. How did you learn, and how late was it?"* Do not pitch.
5. `research/liability.md` — a drafted limitation-of-liability clause and a quote for professional indemnity insurance.

**Acceptance criteria**
- [ ] All three licence texts read in full and the redistribution clause quoted verbatim
- [ ] Written legal opinion obtained covering all three jurisdictions
- [ ] Both competitors' live pricing and latency documented from inside their products
- [ ] **≥10** interviews written up
- [ ] **≥4 of 10** describe learning about a filing too late, or name a loss
- [ ] PI insurance quote obtained and affordable within budget

**Effort and cost.** Agent ~6 hrs. Operator **~15 hrs**. Cost **NZ$500–900** (legal opinion, competitor subscriptions, insurance quote).

**🛑 KILL CRITERIA — stop entirely**
- **Any** of the three licences prohibits commercial redistribution, or the lawyer cannot confirm it
- The German restriction is assessed as an EU-wide direction of travel rather than a local dispute
- **Fewer than 4 of 10** interviewees report late notice or a loss
- Prometiam or Insolvencies.live turn out to be fast, cheap, well-covered and well-supported — you would be fourth with no edge
- PI insurance is unobtainable or unaffordable for a solo vendor

**Resume block.** *A fresh session needs:* this repo; `04-recommendation.md` for the reasoning and the named bear case; the fact that **all licence claims in this repo are unverified search snippets**; and that Germany is deliberately excluded.

---

## Phase 1 — Demand smoke test

**Objective.** Confirm named credit-risk buyers will engage before any scraper is written.

**Deliverables**
1. A one-page technical landing page: coverage, latency promise, webhook shape, sample JSON payload, US$300/mo stated openly. Written for developers and risk analysts, not marketers.
2. A **free live sample feed** — the last 30 days of French BODACC insolvency notices, normalised, publicly queryable. This is the lead magnet and it doubles as proof the pipeline works.
3. **60 compliant outreach emails** to named credit-risk managers, trade-credit underwriters and factoring ops staff, identified via LinkedIn title search and trade-body directories. UEMA 2007 deemed consent: publicly-published business addresses, role-relevant message, clear sender identity, working unsubscribe.
4. Posts in 2–3 credit-risk or fintech communities that permit tool sharing.

**Acceptance criteria**
- [ ] Sample feed live, updating daily, with a public JSON endpoint
- [ ] 60 outreach emails sent, all UEMA-compliant, unsubscribes honoured automatically
- [ ] **≥12 replies**
- [ ] **≥4 people ask about pricing, coverage or an API key** unprompted
- [ ] **≥1 person asks for a jurisdiction you don't yet cover** — the clearest possible demand signal

**Effort and cost.** Agent ~12 hrs. Operator ~10 hrs. Cost ~NZ$80 (domain, email).

**🛑 KILL CRITERIA**
- Under 6 replies from 60 targeted, role-relevant emails
- Zero unprompted pricing or access enquiries
- Consistent feedback that existing tools are already fast enough

**Resume block.** *Needs:* Phase 0 outputs; the outreach list and send log (for unsubscribe compliance); reply counts against thresholds; the sample-feed repo.

---

## Phase 2 — Thin-slice MVP
### One jurisdiction. No accounts, no billing, no settings.

**Objective.** France end to end: BODACC → normalised records → queryable API → webhook.

**Deliverables**
1. BODACC ingestion on a schedule, with change detection.
2. A normalised schema — company identifier, legal name, procedure type, court, filing date, source URL, ingestion timestamp. **Every record carries a link to the source notice**; the product never asserts anything the register did not publish.
3. REST endpoint: query by company identifier and by date range.
4. Webhook delivery with retry and dead-letter handling.
5. Ingestion-failure alerting to the operator.
6. A public status page showing last-successful-ingestion per jurisdiction. **With this buyer, visible freshness is the product.**

**Acceptance criteria** *(machine-checkable)*
- [ ] Test suite passes; **≥80% coverage on parsing and normalisation**
- [ ] Golden-file tests: a fixed set of real BODACC notices parses to expected records; **any parser regression fails CI**
- [ ] Idempotency test: re-ingesting the same notice creates no duplicate
- [ ] **Freshness test: a notice published today appears in the API within 24 hours**, asserted by an automated daily check
- [ ] Webhook delivery retries on failure and dead-letters after N attempts, proven by test
- [ ] Status page reflects a deliberately induced ingestion failure within 15 minutes

**Effort and cost.** Agent ~35 hrs. Operator ~10 hrs. Cost ~US$25/month.

**🛑 KILL CRITERIA**
- BODACC data proves too unstructured to parse to a reliable schema
- Freshness cannot beat the incumbents' 3–21 day lag — **latency is the entire value proposition**
- No Phase 1 contact will test the endpoint

**Resume block.** *Needs:* the schema; golden-file fixtures; the freshness SLA; the rule that every record links to its source; and that Spain requires scraping while France and the UK have structured feeds.

---

## Phase 3 — Monetisation

**Objective.** First paying customer, and the UK added.

**Deliverables**
1. API-key issuance, accounts, usage metering.
2. **Paddle** subscription at US$300/month, 14-day trial with a key issued immediately.
3. UK (The Gazette) ingestion — **corporate notices only**, with an explicit filter excluding individual-insolvency notices per the OGL personal-data exclusion.
4. Developer docs: authentication, endpoints, webhook payloads, a runnable curl example, and a stated freshness SLA.
5. Terms of service carrying the Phase 0 limitation-of-liability wording and an explicit statement that the feed reports published notices and is not a credit opinion.
6. Dunning and failed-payment handling.

**Acceptance criteria**
- [ ] End-to-end test: signup → key issued → API call succeeds → trial converts → invoice raised
- [ ] A developer reaches a successful authenticated API call **in under 10 minutes from the docs alone**, measured on a real person
- [ ] UK personal-data exclusion enforced **in code**, with a test asserting individual-insolvency notices are never emitted
- [ ] **≥1 customer has paid real money**
- [ ] Cancellation is self-serve

**Effort and cost.** Agent ~28 hrs. Operator ~10 hrs. Cost ~US$50/month + Paddle 5% + $0.50/txn.

**🛑 KILL CRITERIA**
- **Zero paying customers 10 weeks after billing goes live**, having contacted every Phase 1 respondent
- Buyers consistently demand Germany as a precondition — the one market you cannot lawfully serve
- Trial-to-paid under 15% with ≥10 trials

**Resume block.** *Needs:* Paddle details; the UK personal-data filter and its test; current customer count; trial conversion; and the standing rule that the ToS never implies a solvency opinion.

---

## Phase 4 — Distribution and coverage engine

**Objective.** Reach six paying customers, and make coverage the reason they stay.

**Deliverables**
1. **Spain (BORME) ingestion** — the scraping-based jurisdiction. Completing FR+UK+ES reaches parity with both named competitors.
2. Sustained compliant outreach: 40 named prospects per month, batched weekly.
3. A **public coverage and latency page** — jurisdictions, freshness, historical uptime. Publish latency honestly; with this buyer it is the strongest possible marketing.
4. Listings in fintech and risk-tooling directories, plus RapidAPI as a secondary discovery channel.
5. One genuinely useful public artefact — for example an open dataset of French insolvency filing volumes by month and sector — as a linkable asset that earns attention without a content treadmill.
6. Referral ask to every satisfied customer at day 60.

**Acceptance criteria**
- [ ] Three jurisdictions live with published per-jurisdiction freshness
- [ ] **≥6 paying customers**
- [ ] Median notice-to-API latency **under 24 hours**, published
- [ ] Churn **under 5% monthly**
- [ ] CAC under US$400 (payback inside 1.5 months at US$300/mo)
- [ ] **≥1 customer citing coverage or latency as the reason they chose you over a named competitor**

**Effort and cost.** Agent ~25 hrs. Operator ~12 hrs/week sustained. Cost ~US$80/month.

**🛑 KILL CRITERIA**
- Fewer than 3 paying customers 6 months after billing began
- Churn above 8% monthly
- A competitor reaches 6+ jurisdictions with better latency while you are at three
- A source jurisdiction restricts redistribution — treat as an existential review, not a setback

**Resume block.** *Needs:* per-jurisdiction ingestion status; the coverage page; customer count and churn; competitor coverage as last checked; and the standing rule to publish latency honestly.

---

## Phase 5 — Hardening

**Objective.** Make the maintenance sustainable and prove the hours, because the maintenance *is* the moat and burnout is the way it fails.

**Deliverables**
1. Per-source health monitoring with alerting on schema drift, not just on hard failure — **the dangerous failure mode is a parser that silently stops matching, not one that crashes.**
2. Automated golden-file regression on every source, daily.
3. Runbooks for each jurisdiction: where the data comes from, known quirks, what breakage looks like, how to fix it.
4. Self-serve docs covering the top 20 support questions.
5. A monthly regulatory-watch routine covering all source jurisdictions plus the German dispute.
6. **A four-week itemised time log.**

**Acceptance criteria**
- [ ] Measured operator time **≤15 hrs/week averaged over 4 weeks**, itemised: parser maintenance ___, support ___, outreach ___, admin ___
- [ ] Schema-drift alerting proven by deliberately feeding a malformed source document
- [ ] Every jurisdiction has a written runbook a stranger could follow
- [ ] **The product survives a two-week untouched period with no silent data gaps** — run this for real and verify afterwards that no notices were missed
- [ ] ≥70% of support questions answerable by linking to docs

**Effort and cost.** Agent ~18 hrs. Operator ~10 hrs. Cost ~US$90/month.

**🛑 KILL CRITERIA**
- Measured time exceeds 20 hrs/week with no automation left
- The two-week untouched test reveals **silent** data gaps that alerting missed
- Parser breakage exceeds roughly one incident per source per month

**Resume block.** *Needs:* the time log; per-source runbooks; drift-alerting config; and the rule that silent gaps are the real risk.

---

## Phase 6 — Compound or kill

**Review date: 12 months after Phase 3 billing went live.**

### DOUBLE DOWN if all hold
- MRR **≥ NZ$2,500** and growing
- Churn **< 5% monthly**
- Operator time **≤ 15 hrs/week**
- **≥4 jurisdictions** live with sub-24-hour median latency
- CAC payback **< 2 months**

*Then:* add Italy, Netherlands and Portugal; revisit Germany only if the NRW dispute resolves favourably; raise price for new customers; consider adjacent distress events (court judgments, striking-off notices).

### SHUT DOWN if any hold
- MRR **< NZ$800** after 12 months of selling
- Churn **> 10% monthly**
- A source jurisdiction prohibits redistribution and cannot be replaced
- A competitor reaches 8+ jurisdictions with better latency and lower price
- Operator time **> 20 hrs/week** sustained

*Then:* consider selling. At 2–3× annual SDE, a business at NZ$2,000/month might fetch roughly **NZ$48,000–72,000** [ESTIMATE, multiples from `research/ground-truth-findings.md`]. A data business with accumulated coverage may fetch better than a generic SaaS at the same revenue, because the coverage is the asset — but I have **no category-specific multiple** to support that.

### KEEP GOING, DON'T EXPAND if in between
Hold as a small profitable asset. Add no features. Maintain coverage. Re-review in 6 months.

---

## Budget check

| Phase | Agent hrs | Operator hrs | Cost |
|---|---|---|---|
| 0 | 6 | 15 | NZ$500–900 |
| 1 | 12 | 10 | ~NZ$80 |
| 2 | 35 | 10 | ~US$25/mo |
| 3 | 28 | 10 | ~US$50/mo + Paddle |
| 4 | 25 | ~12/wk | ~US$80/mo |
| 5 | 18 | 10 | ~US$90/mo |
| 6 | 2 | 3 | — |
| **Total** | **~126** | **~140 + sustained** | **Upfront exceeds US$300 in Phase 0 only** |

**One budget honesty note.** Phase 0's legal opinion (NZ$500–900) **exceeds the US$300 upfront allowance.** I am recommending you spend it anyway: it is the cheapest possible way to discover the project is illegal, and every other cost in the plan is contingent on it. If that is genuinely unavailable, the fallback is to read the three licence texts yourself and launch **France only** — its Licence Ouverte is the most explicit about commercial redistribution — accepting materially more risk.
