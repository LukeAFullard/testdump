# Deep dive #1 — `casact/chainladder-python` → hosted actuarial reserving

**Weighted score: 6.90 / 10. Below your 7.0 bar. Fails your "no sales calls" gate.**

Highest raw score in the search, and the one I'd hand you if willingness-to-pay were the
only axis. It is not, and the gate it fails is one you wrote down as a requirement.

---

## The repo

| Fact | Value | Source & date |
|---|---|---|
| Repo | `casact/chainladder-python` | [github.com/casact/chainladder-python](https://github.com/casact/chainladder-python), checked 2026-09-04 |
| Stars / forks | 275 / 115 | same page, 2026-09-04 |
| Open issues | 113 | same page, 2026-09-04 |
| Commits | 3,026 on `main` | same page, 2026-09-04 |
| Licence | **MPL-2.0** | Read from [LICENSE](https://raw.githubusercontent.com/casact/chainladder-python/main/LICENSE) via raw.githubusercontent.com, 2026-09-04. Grepped for Commons Clause / "may not sell" — **zero hits**. |
| PyPI | `chainladder` 0.10.0, uploaded **2026-07-29** | [pypi.org/pypi/chainladder/json](https://pypi.org/pypi/chainladder/json), 2026-09-04; `license` field reads `MPL-2.0` |
| Governance | Casualty Actuarial Society runs a Contributors Working Group meeting biweekly | Repo README, 2026-09-04 |

**What it does and why it's hard.** Loss reserving is the process of estimating how much
an insurer owes on claims that have happened but aren't fully paid or even reported yet
(IBNR — incurred but not reported). The library implements triangle data structures,
link-ratio development, and both deterministic and stochastic methods (Mack, bootstrap
ODP, Clark, Benktander, Cape Cod). This is not CRUD — it's a body of statistical
methodology with a peer-reviewed literature, and the CAS published a
[practitioners' guide to building reserving workflows on it](https://eforum.casact.org/article/123379-practitioners-guide-to-building-actuarial-reserving-workflows-using-chain-ladder-python).
Rebuilding it correctly would take a competent team many months, and getting it *wrong*
is invisible until an audit. **Verified.**

**Health:** healthy. 3,026 commits, a release six weeks before I checked, and an
institutional backer (CAS). Passes hard filter #4.

**Licence risk:** MPL-2.0 is file-level copyleft. You can build a proprietary SaaS on it;
you only have to publish modifications to *its* files. Cleanest possible outcome. No
Commons Clause, no commercial-use carve-out. **Verified by reading the file.**

## The gap

`chainladder-python` is a Python library. To use it you write code, manage a Python
environment, hand-build triangles from claims extracts, and produce your own exhibits.

A hosted product would be: upload a claims listing (CSV/Excel) → it builds the triangle →
you pick methods and select development factors in a UI → it produces the reserve
estimate, the diagnostics, and a formatted actuarial exhibit pack you can drop into a
board report or hand to an auditor.

The distance between library and product is real: triangle construction from messy claims
data, the judgment-heavy step of *selecting* link ratios, and the exhibit formatting that
actuaries actually deliver. That's a genuine product, not a thin wrapper.

## The buyer

**Not "small businesses".** Specifically:

- **Role:** Chief Actuary, Reserving Actuary, or Actuarial Manager.
- **Organisation:** P&C insurer writing US$50M–500M gross written premium; or a captive
  insurer; or an MGA that must report to its capacity providers; or a 2–20 person
  actuarial consultancy doing outsourced reserving for several such clients.
- **Why they're the buyer:** they must produce a reserve estimate every quarter, signed,
  with documented methodology. It is non-optional and recurring.
- **What they do today:** Excel, almost always. A reserving workbook with triangles built
  by hand, passed down through staff turnover, with formula errors nobody can find. The
  step up is ResQ or Arius, which is a large jump in cost and procurement effort.
- **The consultancy is the better wedge** — they feel the pain N times per quarter across
  N clients, they're small enough to buy without a committee, and they have no incumbent
  licence to write off.

## Evidence of demand

**This is where the candidate is weak, and I won't dress it up.**

| Claim | Status | Evidence |
|---|---|---|
| Commercial reserving software is enterprise-priced and widely used | **Verified** | [ResQ (WTW) states 500+ companies use it](https://www.wtwco.com/en-us/solutions/products/resq); [Arius (Milliman) was acquired by Akur8](https://www.akur8.com/reserving/arius) in Sept 2024; Akur8 raised a [$120M Series C](https://www.cbinsights.com/company/arius) |
| Actuaries are actively adopting the open-source library | **Verified** | The CAS published a practitioners' guide (linked above) and hosts a Contributors Working Group |
| Small actuarial teams currently use Excel-based tooling | **Inferred** | Industry commentary that "Excel-based or cloud light solutions are suitable for smaller actuarial teams" — [The Actuarial Club](https://theactuarialclub.com/2023/08/01/non-life-reserving-software-for-actuaries/). I could not verify a market-share figure. |
| Anyone wants to buy a *hosted* version of this specific library | **NOT VERIFIED** | I found no issue, forum post, or job listing asking for it. This is the gap in the case. |
| Actual list prices for ResQ / Arius | **NOT VERIFIED** | Both are quote-based; no public pricing page exists. My WTP score of 9 rests on inference from enterprise positioning, not a price I read. |

## Competitive landscape

| Product | Positioning | Pricing | Source |
|---|---|---|---|
| ResQ (WTW) | Market leader, large insurers/reinsurers | Quote-only | [wtwco.com](https://www.wtwco.com/en-us/solutions/products/resq) |
| Arius / Arius Enterprise (Akur8, ex-Milliman) | Deterministic + stochastic, mid-to-large P&C | Quote-only | [arius.milliman.com](https://arius.milliman.com/en/arius-enterprise) |
| Addactis | European non-life reserving | Quote-only | [addactis.com](https://www.addactis.com/solutions/reserving/) |
| R `ChainLadder` package | Free, the R-side equivalent | Free | [mages.github.io/ChainLadder](https://mages.github.io/ChainLadder/) |
| Excel | The real incumbent | Already paid for | — |

**The wedge:** nobody serves the bottom of this market self-serve. Every commercial
option requires a procurement conversation. A US$300/month self-serve product for a
5-person consultancy or a captive has no direct competitor. **That gap is real.**

**The reason the gap exists:** see "Why this will fail".

## The product

**Core loop:** upload claims extract → confirm triangle mapping → select methods and
development factors → export exhibit pack.

**v1 screens:** (1) upload + column mapping; (2) triangle view with editable link-ratio
selections; (3) method comparison (Mack vs. bootstrap vs. Cape Cod) side by side;
(4) diagnostics (residual plots, Mack's assumption tests); (5) export to Excel + PDF.

**Explicitly NOT in v1:** capital modelling, pricing, IFRS 17 measurement, reinsurance
structures, multi-user review workflow, data warehouse connectors.

## Business model

| Tier | Price | For |
|---|---|---|
| Solo | US$290/user/month | Independent consulting actuary |
| Team | US$990/month, 5 seats | Small consultancy or captive |
| Firm | US$2,500/month, 15 seats + API | Mid-size insurer |

No free tier — a free tier attracts students and costs support time; offer a 14-day trial
instead. Merchant of record: **Paddle or Lemon Squeezy**, not raw Stripe, so US sales tax
and EU VAT are handled from New Zealand.

**Cost to serve:** trivially low. Triangles are kilobytes; a reserve run is seconds of
CPU. Realistically **US$3–8 per customer per month** on a small managed container plus
Postgres. Unit economics are excellent — which is why the axis scores 8.

## Distribution plan

1. **The CAS community itself.** The Contributors Working Group and CAS E-Forum are
   where this library's users already are. Publish a genuinely useful free tool (e.g. a
   triangle-from-claims-extract converter) and let it carry the product. Concrete first
   action: present at a CAS webinar or write for the E-Forum.
2. **Long-tail SEO against queries that currently return only GitHub and PDFs:**
   "chainladder python triangle from claims data", "bootstrap ODP reserving example",
   "Mack method Excel alternative", "IBNR calculation software small insurer",
   "reserve development triangle template". These currently return READMEs and academic
   PDFs — **inferred from the search results I saw, not systematically volume-checked**.
3. **Actuarial consultancies directly on LinkedIn.** ~2–20 person firms, findable by
   title. This is outbound, and it is the tell that this business isn't passive.

## Realistic financial model

Assumptions, stated: launch at month 6; ARPU US$400 (blend of Solo and Team); monthly
churn 2% (professional tools with quarterly workflows churn low); no paid acquisition;
infra US$150–400/month total; ignores your time.

| Month | Pessimistic customers / MRR | Base customers / MRR |
|---|---|---|
| 6 | 0 / $0 | 1 / $290 |
| 9 | 1 / $290 | 4 / $1,400 |
| 12 | 2 / $600 | 9 / $3,300 |
| 18 | 4 / $1,300 | 18 / $6,900 |
| 24 | 6 / $2,000 | 28 / $11,200 |

**Base case at month 24: ~US$134k ARR.** **Pessimistic: ~US$24k ARR.** Neither is a
hockey stick, and the base case still assumes you personally close roughly one customer a
month — which is sales work.

## Why this will fail

**Why hasn't anyone built it already?** Because the buyer will not self-serve. Reserving
output goes into audited financial statements and regulatory filings. Before an actuary
runs your numbers in anger, they will want: documented methodology, version control of
the calculation engine, evidence the results tie to a known benchmark, and often a
conversation with a human who will answer for it. That is a sales-and-assurance motion,
not a signup flow. The gap in the market is not an oversight — it is the market pricing
in trust.

**What happens when the maintainer adds a hosted tier?** Low risk. The CAS is a
professional body, not a vendor. But the more realistic version of this risk is
different: **Akur8, having bought Arius and raised $120M, moves down-market.** They have
the brand, the actuarial credibility, and the capital to serve small insurers at a price
you cannot undercut on trust.

**Realistic revenue ceiling.** Count the buyers: small-to-mid P&C insurers plus captives
plus small actuarial consultancies, worldwide, that would buy self-serve software in
English. Low thousands, of which you might reach a few hundred. At US$400 ARPU that is a
**ceiling around US$1–2M ARR**, and realistically a few hundred thousand. It is a good
solo income; it is not a large business.

**How do the first 50 paying customers find out?** Honest answer: you present at CAS
events and message actuaries on LinkedIn for a year. SEO will not deliver 50 customers in
a market this small — the search volume isn't there. **This is the distribution answer
that should worry you most**, and it directly contradicts your "no sales calls" requirement.

**What breaks if the repo changes?** MPL-2.0 cannot be revoked for existing code, and you
could fork. API churn is the live risk: the library is pre-1.0 (0.10.0), and pre-1.0
projects break interfaces. Mitigate by pinning the version and treating upgrades as
deliberate projects.

## Risks and mitigations

| Risk | Severity | Mitigation |
|---|---|---|
| Buyer requires sales calls — fails your gate | **High** | None that preserves the constraint. This is why it isn't my recommendation. |
| Professional liability if a reserve estimate is wrong | High | Terms of service disclaiming actuarial opinion; position as a calculation tool, not an opinion. Take advice — I am not a lawyer. |
| Regulatory adjacency (results feed statutory filings) | Medium | You are not a regulated entity, but your customers are. Flagged per your brief. |
| Akur8 moves down-market | Medium | Nothing structural. Speed and price only. |
| Pre-1.0 API churn | Low | Pin versions; wrap the library behind your own interface. |
| Market too small to support SEO-led growth | **High** | Accept a community-led, slow-growth path. |
