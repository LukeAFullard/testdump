# 05 — Phased Build Plan
## NZ Construction Retention-Money Trust Compliance Ledger

**Run date 2026-09-03. Conditional on Phase 0 clearing — see `04-recommendation.md`.**

**Working name:** RetentionLedger (placeholder)
**Buyer:** NZ construction businesses that hold retention money from subcontractors
**Price:** NZ$149/month (US$89) — set by the value-pricing arithmetic in `03-deep-dives.md`, not by competitors
**Target:** US$3,000/month ≈ 34 customers ≈ 3.7 new paying customers per month
**Payments:** Paddle (Merchant of Record). NZ-domestic B2B only at first, so GST is the only tax surface.
**Non-negotiable product boundary:** the software **never touches, moves or custodies money.** Tracking and reporting only. Crossing this line pulls the business into NZ Financial Service Providers Act 2010 and AML/CFT Act 2009 scope.

**Budget envelope:** ~NZ$500 (US$300) upfront, ~US$100/month ongoing.
**Hours:** 8/week during build; ≤3/week at steady state (Phase 5 exit criterion, not a Phase 0–4 operating constraint — see `00-brief-review.md` §C1).

---

## Phase 0 — Validate before building
### *No code. This is the gate on everything.*

**Objective.** Determine whether enough NZ businesses hold retention money, and whether they experience the obligation as painful enough to pay NZ$149/month.

**Deliverables**
1. `research/tam.md` — a sourced count of NZ businesses holding retention money, from MBIE construction statistics, Stats NZ business demography by ANZSIC construction subclass, and Registered Master Builders / Specialist Trade Contractors Federation membership figures. Every figure with a URL and date.
2. `research/interviews.md` — notes from **10 conversations** with NZ head contractors, construction bookkeepers or QSs. Script: *"Walk me through how you handled your last quarterly retention report."* Do not pitch. Listen.
3. `research/competitors.md` — actual prices for Retention Track, Payapps, Gojee, Workbench, obtained by signing up for trials or asking directly.
4. `research/legal.md` — written confirmation of the Act's current commencement and obligations, from MBIE or a NZ construction lawyer.
5. A one-page written go/no-go with the numbers.

**Acceptance criteria**
- [ ] TAM figure sourced from **≥2 independent official sources**
- [ ] **≥10** interviews completed and written up
- [ ] **≥3** competitor prices obtained
- [ ] Legal position confirmed in writing by a named source

**Effort and cost.** Agent: ~4 hrs (desk research, drafting outreach). Operator: **~12 hrs** (the interviews — this part cannot be delegated). Cost: **NZ$0–200** (optional legal question).

**🛑 KILL CRITERIA — stop entirely if any of these is true**
- Pool of businesses holding retentions is **under 800**
- **Fewer than 3 of 10** interviewees describe the quarterly obligation as painful, or say they already handle it adequately
- **≥2 of 5** incumbents already offer a dedicated, well-reviewed compliance product under NZ$149/month
- Xero or a major NZ construction platform has retention-trust compliance on a published roadmap
- Legal advice says the tracking-only product cannot avoid FSP/AML scope

**Resume block.** *A fresh agent needs:* this repo; `04-recommendation.md` for why this was chosen and its named weaknesses; the kill criteria above; the fact that **no claim in this repo was verified by opening a source page** (network was blocked), so everything needs re-checking; and that the single decisive unknown is the TAM denominator.

---

## Phase 1 — Demand smoke test

**Objective.** Prove that NZ contractors will give up an email address for this before a line of product code is written.

**Deliverables**
1. One landing page: the obligation, the penalty, what the tool does, NZ$149/month stated openly, email capture.
2. A 12-question self-assessment ("Are you compliant?") as the lead magnet — genuinely useful standalone.
3. Outreach to **100** NZ head contractors, using deemed consent under the Unsolicited Electronic Messages Act 2007: publicly-published business addresses only, role-relevant message, clear sender identity, working unsubscribe. **Re-read `research/distribution-findings.md` Finding 4 before sending anything.**
4. Posts in 2–3 NZ construction communities where self-promotion is permitted. Check rules first.
5. Approaches to Registered Master Builders and Specialist Trade Contractors Federation about a member newsletter mention.

**Acceptance criteria**
- [ ] Page live on a custom domain, loads under 2s, mobile-legible
- [ ] Analytics recording visits and conversions
- [ ] 100 outreach emails sent, all UEMA-compliant, with unsubscribe honoured automatically
- [ ] **≥25 email signups**
- [ ] **≥5 people reply asking when it ships or what it costs** — the real signal

**Effort and cost.** Agent: ~10 hrs. Operator: ~8 hrs. Cost: **~NZ$60** (domain + email sending).

**🛑 KILL CRITERIA**
- **Under 15 signups** from 100 targeted emails plus community posts (a <15% response to a legally-forced problem means the pain is not felt)
- **Zero** unprompted "when can I buy this" replies
- Association contacts uniformly decline to mention it

**Resume block.** *Needs:* Phase 0 outputs; the landing page repo; the outreach list and send log (for unsubscribe compliance); current signup count against the 25 threshold; and the standing rule that outreach is consent-based under NZ law.

---

## Phase 2 — Thin-slice MVP
### *No accounts. No billing. No settings pages.*

**Objective.** Build the single core loop: enter retentions held → produce a compliant quarterly report.

**Deliverables**
1. Retention record entry: subcontractor, contract, amount, dates, trust account reference.
2. Trust-ledger view with running balances per subcontractor.
3. **Quarterly report generator** producing the statutorily-required PDF: amount, contract, dates, bank details, inspection rights.
4. A breach warning when a ledger position is inconsistent.
5. A seeded demo dataset.
6. **CSV import/export first. No Xero integration yet** — this deliberately avoids the March 2026 Xero egress pricing exposure until the product is proven.

**Acceptance criteria** *(machine-checkable)*
- [ ] Automated test suite passes; **≥80% coverage on ledger arithmetic**
- [ ] Property-based test: for any sequence of retention movements, ledger balance equals the sum of movements — no floating-point drift (use integer cents)
- [ ] Generated PDF contains every field the Act requires, asserted by test
- [ ] End-to-end test: seed data → generate report → assert PDF field values
- [ ] Report generation completes in under 5s for 100 subcontractors
- [ ] **A real contractor from Phase 1 confirms the generated report would satisfy their obligation**

**Effort and cost.** Agent: ~30 hrs. Operator: ~10 hrs (review, and getting that confirmation). Cost: **~US$20/month** (hosting).

**🛑 KILL CRITERIA**
- No Phase 1 contact will look at the output
- The contractor who reviews it says the report would **not** satisfy the obligation and the gap needs domain knowledge you cannot acquire
- Ledger arithmetic cannot be made provably correct — for a compliance product, "mostly right" is worthless

**Resume block.** *Needs:* Phase 1 signup list; the schema; the statutory field list from `research/legal.md`; the integer-cents rule; and the deliberate decision to stay off the Xero API in this phase.

---

## Phase 3 — Monetisation

**Objective.** First real paying customer.

**Deliverables**
1. Accounts and authentication.
2. **Paddle** subscription billing at NZ$149/month, 14-day trial, no card up front.
3. Self-serve onboarding: import subcontractors from CSV, first report inside 15 minutes.
4. Transactional email: welcome, trial ending, payment failed, quarterly reminder.
5. Error alerting to the operator.
6. Terms, privacy policy (NZ Privacy Act 2020), and an explicit disclaimer that the product is **not legal advice**.

**Acceptance criteria**
- [ ] End-to-end test: signup → trial → card → active subscription → invoice issued
- [ ] Dunning tested: failed payment triggers retry and email
- [ ] Cancellation works without contacting the operator
- [ ] A new user reaches their first generated report in **under 15 minutes unaided**, measured
- [ ] **≥1 customer has paid real money**
- [ ] Zero manual steps between signup and value

**Effort and cost.** Agent: ~25 hrs. Operator: ~8 hrs. Cost: **~US$40/month** + Paddle 5% + $0.50/transaction.

**🛑 KILL CRITERIA**
- **Zero paying customers 8 weeks after billing goes live**, having contacted every Phase 1 signup
- Trial-to-paid conversion **under 5%** with ≥20 trials
- Onboarding needs operator intervention for **more than 1 in 5** signups — that is a per-customer manual labour cost, which violates the core constraint

**Resume block.** *Needs:* Paddle account details (MoR chosen because of the UK nil-VAT-threshold and EU first-euro rules in `00-brief-review.md` §4.2); current paying-customer count; trial conversion rate; and the rule that no signup may require a human.

---

## Phase 4 — Distribution engine

**Objective.** Build the one compounding channel, and work it for 90 days before judging it — the pattern the evidence supports.

**Deliverables**
1. **Primary: trade-association channel.** Registered Master Builders and Specialist Trade Contractors Federation — member newsletter mention, directory listing, or member-benefit arrangement.
2. **Secondary: Xero App Store listing.** Requires certification with **≥3 active customers onboarded inside a 30-day review window** — which is why this comes after Phase 3, not before. Model the egress cost against the March 2026 tiers before connecting anything.
3. **Tertiary: a small set of genuinely useful pages** — a retention-obligation explainer, a free trust-ledger template, a penalty calculator. Not a content treadmill; a handful of durable, linkable assets.
4. Continued compliant outreach, batched weekly.
5. A referral ask to every satisfied customer at day 60.

**Acceptance criteria**
- [ ] **≥1 association relationship live** (newsletter mention, listing, or member benefit)
- [ ] Xero listing submitted, or a documented decision not to, with the egress cost modelled
- [ ] **≥3 new paying customers per month for 3 consecutive months** — the arithmetic requires 3.7
- [ ] CAC measured and under NZ$300 (payback inside 2 months at NZ$149)
- [ ] Churn measured; **under 6% monthly**

**Effort and cost.** Agent: ~20 hrs. Operator: ~6 hrs/week for 90 days. Cost: **~US$60/month**, plus optional NZ$200–400 for an association listing.

**🛑 KILL CRITERIA**
- After 90 days of one focused channel, **fewer than 2 new paying customers per month**
- Churn **above 8% monthly** — at that rate the target is arithmetically unreachable
- CAC exceeds 3 months of revenue with no path down
- Xero egress cost at projected scale exceeds 20% of revenue

**Resume block.** *Needs:* which channel was chosen and the 90-day start date (do not switch channels early); association contacts and status; the Xero egress model; and the current monthly new-customer rate against the 3.7 target.

---

## Phase 5 — Passivity hardening

**Objective.** Drive operator time to ≤3 hrs/week and prove it with a measurement, not an assertion.

**Deliverables**
1. Self-serve documentation covering the top 20 support questions actually received.
2. In-app contextual help at the three points where users get stuck.
3. Automated dunning, trial reminders, quarterly deadline reminders.
4. Uptime and error monitoring with alerts.
5. Canned support responses for the top 10 questions.
6. A regulatory-watch routine: a monthly calendar reminder to check MBIE and building.govt.nz for changes.
7. **A time log — four weeks of actual recorded minutes, itemised.**

**Acceptance criteria**
- [ ] Measured operator time **≤3 hrs/week averaged over 4 consecutive weeks**, itemised as: support ___ min, ops ___ min, updates ___ min, content ___ min, admin ___ min
- [ ] **≥70% of support questions answerable by linking to a doc**
- [ ] Zero manual steps in onboarding, billing or cancellation
- [ ] Alerting verified by a deliberately induced failure
- [ ] The product survives a **two-week untouched period** with no customer-visible degradation — run this test for real

**Effort and cost.** Agent: ~15 hrs. Operator: ~6 hrs. Cost: **~US$70/month**.

**🛑 KILL CRITERIA**
- Measured time **exceeds 5 hrs/week** after hardening, with no further automation available
- Support load grows **faster than linearly** with customers
- The two-week untouched test produces customer-visible failures

**Resume block.** *Needs:* the four-week time log; the support-question inventory; which questions still lack docs; and the standing rule that the ceiling is measured, never assumed.

---

## Phase 6 — Compound or kill

**Objective.** Decide with numbers, on a date set in advance, rather than by drift.

**Review date: 12 months after Phase 3 billing went live.**

**Deliverables.** A one-page review against the numbers below, and a decision recorded in `STATE.md`.

### DOUBLE DOWN if all of these hold
- MRR **≥ US$2,000** and growing month on month
- Churn **< 6% monthly**
- Operator time **≤ 3 hrs/week** sustained
- CAC payback **< 3 months**
- **≥1 channel** producing customers predictably

*Then:* raise the price for new customers, add the adjacent obligation (progress claims, or the AU equivalent), and consider Australia — noting AU is ~5× the market and shares the timezone.

### SHUT DOWN if any of these hold
- MRR **< US$750** after 12 months of selling
- Churn **> 10% monthly** sustained
- Operator time **> 5 hrs/week** with no automation left
- Zero customers acquired in the last 8 weeks
- An incumbent has shipped this natively and is winning

*Then:* consider selling. At 2–3× annual SDE for this tier, a business at US$1,500/month might fetch roughly **US$36,000–54,000** [ESTIMATE, from the multiples in `research/ground-truth-findings.md`] — a real outcome, not a failure.

### KEEP GOING, DON'T EXPAND if in between
Revenue US$750–2,000, acceptable churn, hours within ceiling. Hold it as a small profitable asset. Do not add features. Do not hire. **Re-review in 6 months.**

**Effort and cost.** Agent: ~2 hrs. Operator: ~3 hrs.

**Resume block.** *Needs:* the metric history since Phase 3; this decision table; and the instruction that the decision is made against these numbers on the date set, not deferred because it feels bad.

---

## Cumulative budget check

| Phase | Agent hrs | Operator hrs | Cost |
|---|---|---|---|
| 0 | 4 | 12 | NZ$0–200 |
| 1 | 10 | 8 | ~NZ$60 |
| 2 | 30 | 10 | ~US$20/mo |
| 3 | 25 | 8 | ~US$40/mo + Paddle fees |
| 4 | 20 | ~6/wk × 90 days | ~US$60/mo + NZ$200–400 |
| 5 | 15 | 6 | ~US$70/mo |
| 6 | 2 | 3 | — |
| **Total** | **~106** | **~125** | **Within US$300 upfront and US$100/month** |

**Honest note on hours.** Operator time across Phases 0–4 averages **well above 3 hrs/week** — closer to 6–8. The ≤3 hrs/week ceiling is a Phase 5 *exit criterion*, and treating it as a build-phase constraint would make the plan undeliverable. This is flagged in `00-brief-review.md` §C1 and is the single most important expectation to set correctly before starting.
