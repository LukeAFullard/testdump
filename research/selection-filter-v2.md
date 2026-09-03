# Selection Filter v2 — for the re-run under revised constraints

Written 2026-09-03, before the re-discovery agents reported, so it cannot be retrofitted to justify a candidate I happen to like. This is the test I will apply in Stage 2/3 of the re-run.

## Why the original rubric is no longer sufficient on its own

The brief's definition of acceptable "low competition" includes *"an underserved segment inside a crowded market"* and *"incumbents that are expensive, dated, or badly reviewed, with users publicly saying so."*

**Six independent spot checks today found that pattern to be reliably false as an opportunity signal** (`revised-constraint-spot-checks.md`). In every case the enterprise incumbent was genuinely bad and genuinely expensive, and in every case two to four self-serve entrants were already sitting in the gap at US$29–199/month. The signal is real; it is simply no longer *scarce*, because it is the obvious move and AI tooling made acting on it cheap.

So the rubric still applies, but it needs a gate in front of it.

---

## THE GATE: what kind of defence does this candidate have?

Classify every candidate's moat into one of three tiers. **Tier 3 is an automatic reject regardless of rubric score.**

### Tier 1 — Time-accumulated (STRONGEST)
The defence is something a competitor must *spend time* acquiring, and cannot buy, copy or generate.
- **Un-backfillable history.** Data captured continuously that cannot be reconstructed retroactively. A competitor starting today has zero history and *can never catch up on the past*. This is the purest form: price history, listing changes, register snapshots, availability records. Validated as a real category — Barchart, DXFeed, Kibot, EODHD and Databento all sell exactly this [S] — though financial markets specifically are saturated.
- **Per-jurisdiction or per-source integration work** that accumulates: 60 scrapers built and maintained over two years.
- **Reputation in a domain where being wrong is expensive**, earned case by case.

### Tier 2 — Structurally awkward (ACCEPTABLE)
The defence is that reaching the buyer or passing the gate is genuinely difficult.
- Buyers with **no marketplace, no search intent, and no community** — reachable only via a trade directory and a compliant email. Painful to reach is *good*: it is why the segment stays underserved.
- **Regulatory, certification or approval gates** that take real time to pass (e.g. a marketplace requiring penetration testing and annual re-review).
- **A structural exclusivity rule** — for example, Make.com reportedly blocks apps duplicating an existing integration, so being first for a given service is a durable position [S, to be verified].
- A market **too small to interest a funded competitor** — legitimate, and the same fact that caps the business at roughly US$3–10k/month. Both halves must be stated together.

### Tier 3 — Insight-based (AUTOMATIC REJECT)
The defence is that the operator noticed something.
- "The incumbent is expensive and badly reviewed." ← **six-for-six failure rate today**
- "There's no self-serve tier."
- "We'll execute better" / "first-mover advantage" — already rejected by the brief.
- "A nicer UI on a frontier-model API call."

**If the honest answer to *"what stops a competent person with the same AI tools cloning this in three weeks"* is a fact about the market rather than an accumulation of work, it is Tier 3. Reject it.**

---

## Secondary tests, applied after the gate

1. **Six-customer test.** At US$300/month the twelve-month target is six customers. **Can I name six specific companies that would plausibly pay?** Not a segment — actual names, findable in a public directory. If prospects cannot be enumerated, distribution is a hope, not a plan.
2. **Fulfilment test** (the no-consulting line at 20 hrs/week). **If customer seven arrives, does monthly workload rise by a fixed per-customer amount?** If yes, it is an agency with a login page. Reject.
3. **Absorption test.** If the dominant platform shipped this natively next quarter, does the product still exist? (Unchanged from kill-question 3 — it killed AU Payday Super and the Xero egress monitor.)
4. **Occupancy test — NEW, and mandatory.** Before believing any gap is open, search for self-serve entrants *specifically*, not just the enterprise incumbent. **Assume two competitors exist that I have not found yet, and go look for them.** Six for six says this is the base case.
5. **Un-backfillable test.** Does delay cost the competitor something permanent? If a cloner starting twelve months later is exactly as well positioned, there is no time moat — only a head start, which decays.

---

## What this predicts

Applying this honestly, I expect most of what the three agents return to fail at the gate, because Tier 3 is where most micro-SaaS ideas live and Tier 1 is rare. **A thin final shortlist is the likely and correct outcome**, and per §7 of the brief a clean "nothing here yet" remains a valid result. I am recording that prediction now so that a thin result later reads as the filter working, not as the research failing.
