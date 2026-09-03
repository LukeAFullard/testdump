# 02 — The Cull and the Kill Log

**Run date 2026-09-03.** Stages 2 and 3. This is the graveyard, as requested.

---

## Stage 2 — Culling 44 candidates to 8

Culled on **demand evidence and distribution feasibility only**, ignoring how interesting the build is. Two gates did nearly all the work:

**Gate A — Distribution.** Research established that generic SEO is not a viable primary channel for a zero-authority site in 2026 (`research/distribution-findings.md`, Finding 1). A candidate survives only if it has a channel that works for an operator with no audience: **platform-marketplace search, compliant targeted B2B outreach, a niche community, or an integration/association directory.**

**Gate B — Shape.** Must be B2B, subscription-shaped (recurring, not one-off), self-serve without sales calls, and plausibly ≤3 hrs/week at steady state.

### The eight that survived to Stage 3
| # | Candidate | Why it survived the cull |
|---|---|---|
| 1 | AU Payday Super reconciliation + shortfall audit | Live legal mandate since 1 Jul 2026, recurring per-pay-cycle, best timezone overlap |
| 2 | NZ construction retention-money trust compliance ledger | Binding law, $200k penalties, quarterly recurring, home market, association channel |
| 3 | Xero API egress-cost monitor (sold to Xero developers) | Acute, dated, *quantified* pain; technical self-serve buyer |
| 4 | UK Companies House ID-verification portfolio tracker | The hardest, nearest verified deadline in the whole run |
| 5 | NZ body-corporate LTMP builder | Binding law with explicitly no opt-out; incumbent serves the wrong buyer |
| 6 | NZ self-managing-landlord compliance dashboard | Two converging 2025/2026 mandates on a segment with no software |
| 7 | Xero FX / difficult-receipt capture | The cleanest high-install/poor-rating signal found (Hubdoc 3.3–3.5★ vs 4.7–4.8★) |
| 8 | QuickBooks↔Shopify reconciliation patch | Unusually strong dated pain: "80% of the features of the old app no longer work" |

### Cut before Stage 3, with reasons
- **Saturation (kill-question 6):** Shopify App Store entry (18,062 apps, **+52% YoY new-app growth**), PDF→spreadsheet parsing, B2B lead lists (Apollo/Clay/Cognism), local SEO citations (BrightLocal/Whitespark), multichannel listing sync (already commoditised), skip-bin hire (6 AU/NZ vendors), driving-instructor scheduling (6 vendors), tattoo booking (6+ vendors), vet recall (iRecall already owns it).
- **Already cheap or free:** invoice→bookkeeping (Hubdoc $12/mo, often free with Xero; Dext ~$25–37.50), skip tracing (**$0.07–0.20 per record**), fixed-asset registers (Xero's is free), EU AI Act kit (Legalithm free to 2028).
- **Economics of the platform:** Atlassian Marketplace (revenue share **15% → 20% → 25% within 18 months**).
- **Not subscription-shaped:** ADA/WCAG audits (one-off), NZ director address filing (one-off), most compliance checklists.
- **Window closed:** InkFrog and Delighted rebuilds — both shut down 2–3 months ago with 6–7 competitors already positioned within weeks.
- **Legal/licence unresolved:** NZ building consents (**no competitors found — treated as a red flag**, likely a Privacy Act reason), NZ Companies Office register copying (guidance discourages it).
- **Hype without a market:** MCP monetisation — **"over 20,000 MCP servers… less than 5% have ever made a single dollar."**
- **Deadline not real:** AU Privacy Act Tranche 2 (no bill introduced), Martyn's Law (no official commencement order found).
- **Market shrinking:** NZ Climate-Related Disclosures (threshold rising $60M → $1B, cutting scope by more than half).

---

## Stage 3 — Kill attempts

For each of the eight: the strongest case that it fails, then an attempt to rebut. **Anything I could not rebut is cut.**

---

### ☠️ KILL 1 — AU Payday Super reconciliation
**The case for failure.** The buyer already owns payroll software, and payday-super compliance is being absorbed into it right now: Xero, MYOB and e-PayDay are building it in at $10–25/employee/month. This is kill-question 3 (feature absorption) in its purest form, and the absorption is already underway rather than hypothetical. Two small vendors (SmallBiz Super Check, FairWork Mate) already occupy the niche. Steady-state was estimated at **3–4 hrs/week** — at or over the ceiling — because SG rates index annually and clearing-house integrations break.

**Rebuttal attempt.** The *historical audit* angle (5-year unpaid-super exposure before it becomes statute-barred) is genuinely distinct from ongoing compliance, and payroll vendors have a structural disincentive to build it because it surfaces their own customers' past failures using their own software.

**Why the rebuttal fails.** The audit is a **one-off per client**. A bookkeeper runs it once across the book and is done. That is a service or a one-time product, not a subscription — and the recurring half of the idea is precisely the half being absorbed for free. The durable part isn't recurring; the recurring part isn't durable.
**VERDICT: CUT.**

---

### ☠️ KILL 2 — UK Companies House ID-verification tracker
**The case for failure.** Pure timing. The transition ends **18 November 2026 — eleven weeks from today**. Phases 0 through 3 at 8 hrs/week realistically take 10–14 weeks. The product would launch exactly as the buying urgency evaporates. Add a trust gap: UK accountancy practices are relationship-driven buyers, and this is a no-name solo vendor in New Zealand with a 12-hour timezone gap.

**Rebuttal attempt.** Demand does not go to zero — new incorporations and annual confirmation statements create an ongoing drip, so the tool has a life after the deadline.

**Why the rebuttal fails.** The post-deadline market is smaller, unurgent, and by then owned by ACSPverify, Verify 365 and Inform Direct, who will have spent the entire acute window acquiring exactly those accounts. Arriving after the forcing function has passed, into a market where incumbents have just harvested it, is the worst possible entry timing. The deadline that makes this idea attractive is the same deadline that makes it unreachable.
**VERDICT: CUT. The clearest kill in the set.**

---

### ☠️ KILL 3 — NZ body-corporate LTMP builder
**The case for failure.** The revenue model contradicts the product. The statutory review cadence is **every three years**. Nobody pays a monthly subscription for a document they touch once every three years — churn would be catastrophic or the price would have to be one-off. The buyer is a volunteer committee with no software budget habit and no purchasing authority reflex. Clone resistance is low, and the total number of NZ body corporates is **unverified**.

**Rebuttal attempt.** Price it annually or triennially, and add ongoing maintenance-schedule tracking to create a reason to log in between reviews.

**Why the rebuttal fails.** Inventing engagement that the statute does not require is wishful. The law creates a three-yearly obligation; a product that needs users to care monthly is fighting its own demand curve. And an annual/triennial price against an unverified, NZ-only denominator cannot plausibly reach US$3,000/month recurring.
**VERDICT: CUT on revenue shape.**

---

### ☠️ KILL 4 — NZ self-managing-landlord compliance dashboard
**The case for failure.** The buyer is effectively a consumer — an individual with one or two rental properties — not a business that expenses software. The brief and my own NZ tax analysis both push toward B2B, and this is the wrong side of that line. Healthy Homes compliance is largely a one-off statement per tenancy; Bond Hub is a free government system. At the NZ$8–15/month price implied, churn would be brutal (kill-question 4: **6–8.6% monthly** at sub-$50 price points), and NZ-only TAM is small.

**Rebuttal attempt.** Landlords with 3–10 properties behave like small businesses and would pay for consolidated compliance.

**Why the rebuttal fails.** That sub-segment is a fraction of an already-small NZ-only pool, and it is exactly the segment most likely to have already engaged a property manager — who brings their own software. The rebuttal shrinks the market to rescue the buyer quality, and the shrunken market cannot support the target.
**VERDICT: CUT on buyer quality and price point.**

---

### ☠️ KILL 5 — Xero FX / difficult-receipt capture
**The case for failure.** **No "why now" exists** — the agent searched and found none; this is an evergreen product gap, not a dated opportunity. The product must beat a free bundled incumbent (Hubdoc) while also competing with two paid incumbents rated **4.7★ and 4.8★**. And the specific weakness being arbitraged — OCR quality on messy and foreign-currency receipts — is the single fastest-improving capability in the industry. Kill-question 3: Xero improves Hubdoc's OCR and the entire rationale disappears.

**Rebuttal attempt.** Xero may never prioritise foreign-currency receipts because it is a minority use case, leaving a durable niche.

**Why the rebuttal fails.** "The incumbent probably won't bother" is a bet on a competitor's roadmap, which is not a moat — it is the "we'll execute better" answer the brief explicitly rejects, wearing a different hat. With no why-now and no defence, this is a feature waiting to be absorbed.
**VERDICT: CUT.**

---

### ☠️ KILL 6 — QuickBooks↔Shopify reconciliation patch
**The case for failure.** Three compounding problems. (1) **Intuit can fix its own connector at any time**, which deletes the entire wedge — and it is under active user pressure to do exactly that. (2) The competitor landscape is **unverified**; the search never ran, and established players (Webgility, Synder, A2X) plausibly already serve this. (3) Maintenance sits on *two* third-party APIs simultaneously, which the agent judged likely to **exceed 3 hrs/week**.

**Rebuttal attempt.** "80% of the features of the old app no longer work" is the strongest dated pain signal in the entire run, and stranded merchants bleeding money are highly motivated buyers.

**Why the rebuttal fails.** The strength of the pain is precisely what guarantees Intuit will fix it — a vendor does not leave 80% of a flagship integration broken indefinitely. The business is a bet that a large company stays incompetent, on a timeline you do not control, in a market whose competition you have not verified. That is kill-question 2 with no answer to "the business survives that."
**VERDICT: CUT.**

---

### 🩸 WOUNDED, NOT KILLED 1 — Xero API egress-cost monitor
**The case for failure.** Platform risk is the worst in the set: Xero has an obvious incentive and a trivial path to putting egress forecasting into its own developer dashboard, which would kill the product overnight with no defence. The buyer universe is tiny (>1,000 apps listed, so perhaps a low four-figure number of developer organisations) — and it is a buyer universe of **software developers, who can build this themselves**, the worst possible customer for a simple tool. The pain may also be **transitional**: developers optimise once, then stop worrying. And "no competitor found" is weak evidence, because the competitor search never ran.

**Rebuttal attempt.** The pain is quantified at up to **$17,000/year**, so a $50–100/month price is trivially justified by value. Developers are self-serve, technically literate, and generate almost no support load — an excellent fit for a 3 hrs/week ceiling. The Xero Developer community is a real, reachable, non-social channel.

**Assessment.** The rebuttal survives partially. The value-anchored pricing and the low support load are real. But nothing rebuts the platform risk or the self-build problem, and both are structural. **Carried to deep dive as the highest-variance option, not as a healthy candidate.**

---

### 🩸 WOUNDED, NOT KILLED 2 — NZ construction retention-money compliance ledger
**The case for failure.** The demand is **inferred from legislation, not observed from users**. No forum post, review or complaint from an actual NZ contractor was found — which is exactly what the brief's definition of "validated" warns against ("your own reasoning about why something should be needed is not validation"). The addressable denominator is **completely unverified**: nobody knows how many NZ businesses actually hold retention money. Five vendors already touch the space. Clone resistance is low. The Act's full commencement date was not verified.

**Rebuttal attempt.** The forcing function is unusually strong and verifiable: retention money must sit in a separate trust account with quarterly reporting, and penalties run to **$200,000 per offence plus $50,000 per director**. The closest-positioned competitor, Retention Track, **had zero reviews** — weak incumbency, not a saturated market. None of the five existing tools is a pure compliance product; they are job-management platforms with retention as a feature. And this is the operator's **home market**: right timezone, credible local vendor, reachable trade associations, and no cross-border tax complexity.

**Assessment.** The rebuttal holds on everything except the denominator. Home-market advantage plus a severe legal forcing function plus visibly weak incumbents is the best combination in the run. But an unverified TAM is a genuine, potentially fatal unknown. **Carried to deep dive as the strongest candidate, conditional on resolving TAM first.**

---

### 🩸 WOUNDED, NOT KILLED 3 — AU Payday Super (audit-only variant)
Cut as a subscription above, but the *reconciliation* half is carried forward to the deep dive purely as the best available comparator: it is the one candidate with a live mandate, severe penalties and a market ~5× larger than NZ. It enters the deep dive already carrying a confirmed feature-absorption wound.

---

## Summary of Stage 3

**Six killed outright. Three carried forward, all wounded.** No candidate emerged from the kill stage undamaged — which is itself the honest headline of this run and is dealt with directly in `04-recommendation.md`.
