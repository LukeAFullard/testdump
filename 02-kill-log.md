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

---
---

# ROUND 2 — Re-run under the revised constraints (2026-09-03)

Constraints changed: **forget NZ, global/online only, ceiling raised 3 → 20 hrs/week.** The round-1 winner is dead (NZ-specific). This is a fresh cull against a **new gate defined *before* the results arrived** (`research/selection-filter-v2.md`), so it cannot have been retrofitted to a favoured answer.

## The gate: what KIND of defence does the candidate have?

Six spot checks established that "a bad, expensive incumbent" is no longer evidence of an opening — in all six cases self-serve entrants already occupied the gap. So each candidate is first classified by moat type:

- **Tier 1 — time-accumulated.** A competitor must *spend time* to match it. Un-backfillable history; per-jurisdiction integration work; reputation where being wrong is expensive.
- **Tier 2 — structurally awkward.** Hard-to-reach buyers; regulatory or approval gates; a platform exclusivity rule; a market too small to interest a funded competitor.
- **Tier 3 — insight-based. AUTOMATIC REJECT.** "The incumbent is expensive and badly reviewed." "There's no self-serve tier." "We'll execute better."

## The round-2 eight

| # | Candidate | Moat tier |
|---|---|---|
| 1 | Multi-jurisdiction corporate insolvency / distress-event API | **Tier 1** |
| 2 | Insurance producer licence & CE compliance (small agencies) | **Tier 1** |
| 3 | Freight carrier-fraud vetting (small brokerages) | Tier 3 → 1? |
| 4 | EPR obligation-mapping API for cross-border e-commerce | **Tier 1** |
| 5 | Make.com first-native-app for an underserved vertical | **Tier 2** |
| 6 | Chemical / cosmetic ingredient regulatory-status API | Tier 1 |
| 7 | Franchisor royalty compliance (<20 units) | Tier 3 |
| 8 | HubSpot silent workflow-failure alerting | Tier 3 |

---

## ☠️ KILL — #8 HubSpot workflow-failure alerting
**Case for failure.** Fails the gate at Tier 3. Polling an API for error states and firing a webhook is a straightforward AI-agent build with no accumulating asset. Worse, this is **an obvious, repeatedly-requested, low-effort HubSpot feature** — the Ideas thread has been open and active since at least Sept 2025, which means HubSpot knows and could ship it any quarter.
**Rebuttal attempt.** Build breadth of failure-type detection and a SOC2-style change-log angle that survives basic native alerting.
**Why it fails.** "They probably won't build it well" is a bet on a competitor's roadmap — the same non-answer the brief rejects. A 12–24 month window is not a business, it is a race with a company that owns the platform. **CUT.**

## ☠️ KILL — #7 Franchisor royalty compliance
**Case for failure.** Tier 3: the entire moat is "enterprise vendors deprioritise franchisors under 20 units". **No "why now"** — the agent searched and found none, and said so. Worse, royalty *auditing* implies per-customer analysis, which risks the fulfilment test: if customer seven arrives, does the operator's monthly work rise by a fixed amount? Probably yes.
**Rebuttal attempt.** Underreporting costs franchisors 5–15% of royalty revenue and some brands have recovered over $1 million — the money is real.
**Why it fails.** The money being real does not make the defence real. Any of the quote-only incumbents can add a small-franchisor tier in a quarter, and the product edges toward being an audit service with a login. **CUT.**

## ☠️ KILL — #6 Chemical / cosmetic ingredient regulatory-status API
**Case for failure.** A licence problem in the two largest jurisdictions. **ECHA's legal notice states that CAS numbers and names sourced via ECHA are "the property of the American Chemical Society and any use or redistribution... is not permitted without... prior written permission."** China's IECSC bulk data is a paid CIRS product. Maintenance was estimated at **10–15 hrs/week — at the ceiling** even under the new allowance.
**Rebuttal attempt.** Key on EC numbers instead of CAS, and source CAS mappings independently.
**Why it fails.** That is a real mitigation but it degrades the product precisely where buyers need it — regulatory staff search by CAS number. Building a compliance data product on a contested identifier is choosing to litigate your core index. **CUT on licence risk.**

## ☠️ KILL — #5 Make.com first-native-app *(the most interesting kill in the project)*
**Case for failure.** The moat is real and rare: Make "will only accept an app if [the incumbent developer is] not actively developing it", so the first native app for a service can lock out later native competitors. But three things break it. (1) **Make has no payments rail** — revenue must come from an adjacent "automation pack plus support" subscription, which is support-linear and edges into the fulfilment trap. (2) **Enforcement of the anti-duplicate policy is unverified** — it is documentation, not a contract, and I could not confirm how consistently it is applied. (3) The target vendor can ship its own integration, which **Tenant Turner just did in July 2025**.
**Rebuttal attempt.** Get the native app live early, accumulate reviews and install base, and make switching costly through template breadth.
**Why it fails.** The moat protects the *integration*, but the *revenue* lives in the automation pack, and nothing protects that. You would own a defensible asset that does not monetise, attached to a monetising asset that is not defensible. **CUT — but recorded as the only genuine structural exclusivity found in the whole project, and worth revisiting if Make ever ships a payments rail.**

## ☠️ KILL — #3 Freight carrier-fraud vetting
**Case for failure.** The demand evidence is the strongest dated set in the project — **US/Canada cargo theft ~$725M in 2025, up 60%; FMCSA double-brokering complaints 8,000+ in 2025 vs ~2,000 in 2021; 15,419 broker authorities revoked**. But: **Truckstop RMIS already publishes a Lite tier at $340/month**, sitting squarely in the proposed price band, and Highway is well funded. And the decisive problem is **liability**: fraud screening is a product where being wrong costs the customer a stolen load. A solo operator with no professional indemnity cover, telling a brokerage a carrier is safe, is accepting a risk they cannot price.
**Rebuttal attempt.** Accumulate proprietary fraud-signal history over time, which would convert the moat from Tier 3 to Tier 1 and also justify the price.
**Why it fails.** The accumulation argument is genuinely good and nearly saves it. But it does not arrive until year two, while the liability exists from customer one. **CUT on liability, not on demand.** If the operator can obtain suitable insurance and a robust limitation of liability, this deserves reconsideration — it has the best raw demand evidence found.

---

## 🩸 SURVIVORS — carried to deep dive

### #1 Multi-jurisdiction insolvency API — survives strongly
**Kill attempt.** Three competitors entered in the last ~18 months (Prometiam, Insolvencies.live, getregdata) so this is nascent, not empty. Germany is legally contested. Spain has no official API and requires scraping.
**Rebuttal.** Nascent-with-three-recent-entrants is a *better* signal than emptiness — it is demand that has been noticed but not yet consolidated, and none of the three has published pricing or achieved coverage beyond the same three countries. The German fight is avoidable by launching FR/UK/ES, where **France's Licence Ouverte 2.0 explicitly permits commercial redistribution**. Spain's scraping requirement is a *cost*, which under a 20-hour ceiling is a moat rather than a blocker. **Survives.**

### #2 Insurance producer licensing — survives
**Kill attempt.** The whole product depends on NIPR/NAIC data access, whose terms and authorisation requirements are **unverified and could be fatal**. "Why now" is only moderate.
**Rebuttal.** The Tier 1 moat is genuine — 50-state renewal calendars are exactly the accumulating grind — and **AgentSync's $100k+/yr average contracts requiring a Salesforce licence** prove enormous willingness to pay upmarket, with two live job ads showing the work being done by hand today. **Survives, with the data-access question as its gate.**

### #4 EPR obligation-mapping API — survives, wounded
**Kill attempt.** **Licence terms are not confirmed for any national PRO fee schedule.** No direct "someone will pay for this" quote was found.
**Rebuttal.** The emptiness has a business-model explanation that passes the brief's own test: every incumbent monetises the *manual registration service*, so none of them wants to sell the data that would disintermediate them. **PPWR obligations from 12 August 2026** give a dated why-now. **Survives on the weakest evidence of the three.**

---

## Round-2 summary
**Five killed, three survive — and unlike round 1, the survivors are not all wounded in the same place.** The difference is entirely attributable to the constraint change: raising the ceiling to 20 hrs/week made the maintenance-moat class available, and that class is where the Tier 1 defences live.
