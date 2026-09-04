# Shortlist — the 9 that survived the hard filters

Scored on your rubric. Weights: Problem hardness 15%, Evidence of demand 25%, Wrapper gap
15%, Willingness to pay 15%, Passivity 10%, Buildability by AI agent 10%, Unit economics
5%, Legal/licence 5%.

## Headline: nothing cleared 7.0

| Rank | Candidate | Weighted total | Passes your hard gates? | Verdict |
|---|---|---|---|---|
| 1 | `casact/chainladder-python` — actuarial reserving | **6.90** | **No** — needs sales calls | Below bar |
| 2 | `Arelle/Arelle` — XBRL/iXBRL | **6.80** | Partly — deadline support spikes | Below bar |
| 3 | `IfcOpenShell/IfcOpenShell` — IFC/IDS QA | **6.60** | **Yes** | Below bar |
| 4 | `e2nIEE/pandapower` — grid studies | 6.55 | Partly | Below bar |
| 5 | `Universite-Gustave-Eiffel/NoiseModelling` — noise mapping | 6.35 | Yes | Below bar |
| 6 | `NREL/EnergyPlus` — building energy | 6.20 | Partly | Below bar |
| 7 | `OpenRefine/OpenRefine` — hosted data cleaning | 6.05 | Yes | Below bar |
| 8 | `jhpyle/docassemble` — legal doc automation | 5.85 | Yes | Below bar |
| 9 | `cloud-custodian/cloud-custodian` — cloud governance | 5.85 | No | Below bar |

Per your instruction, I am not inflating anything to manufacture a winner. The three
deep dives cover ranks 1–3.

**Correction made during research.** I initially scored NoiseModelling at 6.80 on the
strength of an 8/10 wrapper gap, then read its README properly. It already ships a
"user-friendly web-based GUI", Docker images, an OGC WPS API, and a documented
*"Deployment on a public server"* section
([README lines 43–92, verified 2026-09-04](https://raw.githubusercontent.com/Universite-Gustave-Eiffel/NoiseModelling/main/README.md)).
The premise of your thesis — "no usable product wrapped around it" — does not hold.
The remaining gap is "someone else runs the container and bills you", which is close to
hard filter #5 (the hard part isn't the repo). Wrapper gap 8 → 5, total 6.80 → 6.35,
dropping it from 2nd to 5th.

**Why every score is capped:** the demand axis carries 25% weight and I could not gather
dated, attributable, "this person would pay" evidence for any candidate. GitHub's search
API rate-limited me and the web-search tool hit a session quota. Every candidate scores
5–6 on demand as a result. If you resolve demand for one of these and it turns out to be
a genuine 8, that candidate lands at 7.3–7.6 and clears your bar. **This is the single
highest-value thing to resolve, and it is what Phase 0 of the build plan is for.**

---

## 1. `casact/chainladder-python` — 6.90

Actuarial loss reserving (triangles, link ratios, IBNR, Mack/bootstrap) in Python.
Verified 2026-09-04: [275 stars, 115 forks, 113 open issues, 3,026
commits](https://github.com/casact/chainladder-python); MPL-2.0 read from
[LICENSE](https://raw.githubusercontent.com/casact/chainladder-python/main/LICENSE);
PyPI release 0.10.0 on 2026-07-29.

| Axis | W | Score | Justification |
|---|---|---|---|
| Problem hardness | 15% | 8 | Stochastic reserving (Mack, bootstrap ODP, Clark) is genuinely hard statistics with a published [CAS practitioners' guide](https://eforum.casact.org/article/123379-practitioners-guide-to-building-actuarial-reserving-workflows-using-chain-ladder-python) — **verified**. |
| Evidence of demand | 25% | 5 | The CAS runs a Contributors Working Group around it, so institutional interest is real; but **no** dated evidence of anyone wanting to *buy* a hosted version — **inferred**. |
| Wrapper gap | 15% | 8 | No hosted product built on it that I could find; incumbents are all desktop/enterprise — **inferred from absence**. |
| Willingness to pay | 15% | 9 | [ResQ (WTW) claims 500+ companies](https://www.wtwco.com/en-us/solutions/products/resq); [Arius was acquired by Akur8](https://www.akur8.com/reserving/arius), which raised a [$120M Series C](https://www.cbinsights.com/company/arius) — **verified as enterprise-priced; list prices not published**. |
| Passivity | 10% | 4 | **The killer.** Insurers do not buy reserving software self-serve; they run model validation and expect a human. Fails your "no sales calls" gate — **assumed, confidently**. |
| Buildability | 10% | 7 | Clean pandas/scikit-learn-style API; an agent can drive it. Triangle-grid UI is fiddly. |
| Unit economics | 5% | 8 | Triangles are tiny; compute is seconds of CPU. |
| Legal/licence | 5% | 8 | MPL-2.0, file-level copyleft only, no maintainer cloud. Flag: used in regulated filings. |

## 2. `Arelle/Arelle` — 6.80

XBRL/iXBRL processor, certified by XBRL International. Verified 2026-09-04: [232 stars,
359 forks, 92 open issues, 10,253 commits](https://github.com/Arelle/Arelle); Apache-2.0
read from [LICENSE.md](https://raw.githubusercontent.com/Arelle/Arelle/master/LICENSE.md);
PyPI `arelle-release` 2.44.7 uploaded **2026-09-03** — the day before I checked.

| Axis | W | Score | Justification |
|---|---|---|---|
| Problem hardness | 15% | 9 | XBRL taxonomies, dimensions, calculation linkbases and filer-specific rule sets (SEC EFM, ESEF) are brutal; Arelle is the certified reference implementation — **verified**. |
| Evidence of demand | 25% | 6 | Highest of the shortlist: filing mandates (ESEF, SEC, Companies House) create non-optional demand, and a release dated 2026-09-03 proves live institutional use — **verified**. |
| Wrapper gap | 15% | 5 | **The problem.** [Workiva states it invests in Arelle](https://www.workiva.com/solutions/xbrl-and-ixbrl) and files more iXBRL facts than anyone; ParsePort and a long list of [XBRL-certified vendors](https://software.xbrl.org/) exist — **verified**. |
| Willingness to pay | 15% | 8 | Filing is mandatory; late or invalid filings carry penalties. |
| Passivity | 10% | 5 | Filing deadlines create clustered support spikes — a solo operator gets buried in the ESEF window. |
| Buildability | 10% | 7 | Python, with CLI and web-service API already built in. |
| Unit economics | 5% | 8 | Validation is cheap CPU. |
| Legal/licence | 5% | 8 | Apache-2.0, no maintainer cloud. Flag: adjacent to financial regulation, which you asked to avoid. |

## 3. `IfcOpenShell/IfcOpenShell` — 6.60

IFC parsing, geometry kernel and IDS (Information Delivery Specification) validation.
Verified 2026-09-04: [2.8k stars, 959 forks, 1.1k open
issues](https://github.com/IfcOpenShell/IfcOpenShell). Licence **LGPL-3.0-or-later** —
verified from the presence of
[COPYING.LESSER](https://raw.githubusercontent.com/IfcOpenShell/IfcOpenShell/master/COPYING.LESSER)
plus the README's own per-module table (the Bonsai/BlenderBIM add-on is GPL-3.0 and must
be avoided; the libraries are LGPL). PyPI `ifcopenshell` 0.8.5 uploaded 2026-04-13.

| Axis | W | Score | Justification |
|---|---|---|---|
| Problem hardness | 15% | 9 | An IFC parser plus an OpenCASCADE-based geometry kernel plus an IDS rule engine is years of work — **verified** by the module table in the README. |
| Evidence of demand | 25% | 5 | IDS is a real, recently-adopted buildingSMART standard and clients now write it into BIM Execution Plans; but no dated "I'd pay" evidence found — **inferred**. |
| Wrapper gap | 15% | 4 | **Weakest axis.** [buildingSMART runs a free validation service](https://validate.buildingsmart.org/), [ifc-ids.com](https://ifc-ids.com/) is free and in-browser, and [Data Octopus](https://dataoctopus.net/) already sells pay-as-you-go IFC↔IDS checks — **verified**. |
| Willingness to pay | 15% | 7 | [Solibri from ~$185/user/month](https://www.solibri.com/our-offerings) and BIMcollab Zoom at ~€720/year prove the budget exists — **verified from vendor/comparison pages**. |
| Passivity | 10% | 8 | Upload IFC → run rules → download report. No per-customer setup, no human in the loop. Best passivity on the shortlist. |
| Buildability | 10% | 8 | `ifcopenshell` is Python, documented, with IDS support already implemented. An agent can build against it immediately. |
| Unit economics | 5% | 7 | Bounded CPU per model; large IFCs need memory headroom but runs are minutes, not hours. |
| Legal/licence | 5% | 8 | LGPL-3.0 (no network copyleft), maintainer funded by donations via Open Collective, no commercial cloud tier. |

## 4–9: scored, deep-dive not written

| Candidate | Total | The one thing that sinks it |
|---|---|---|
| `NoiseModelling` — hosted noise mapping | 6.35 | Downgraded mid-research: the project already ships a web GUI, Docker images, a WPS API and public-server deployment docs. What's left to sell is hosting and billing, which is thin. High WTP (CadnaA/SoundPLAN are multi-thousand-euro desktop licences) and a genuinely hard CNOSSOS-EU engine, but Java/Groovy/H2GIS makes it the least agent-friendly codebase here. |
| `pandapower` — grid connection studies | 6.55 | Real gap and high WTP (PowerFactory/ETAP are quote-based, thousands per seat), but funded entrants (Pearl Street, GridUnity) are moving in, and a wrong answer in a grid study is a liability problem. |
| `EnergyPlus` — building energy compliance | 6.20 | Wrapper gap 4/10 — [cove.tool](https://cove.tool/) is funded and cloud-native on this exact stack; Pollination serves the Ladybug side. |
| `OpenRefine` — hosted data cleaning | 6.05 | **Verified: no hosted version exists** (12k stars, BSD-3-Clause). But unit economics score 3/10 — a JVM heap per user for multi-hour interactive sessions — and the buyers (librarians, journalists, GLAM, nonprofits) have the lowest budgets of anyone on this list. The gap exists because the economics are bad, which is exactly the "structural gap" test failing. |
| `docassemble` — legal doc automation | 5.85 | [Gavel starts at $83/mo](https://lawyerist.com/reviews/document-management-automation/gavel/) and owns this niche. Also a health flag: last PyPI release 2025-03-04, ~18 months stale — **verified**. |
| `cloud-custodian` — cloud governance | 5.85 | FinOps is crowded, and holding customers' AWS credentials is the opposite of a low-support, low-risk passive business. |

---

## What I could not verify, and what would resolve it

| Open question | Why it matters | How to resolve |
|---|---|---|
| Does anyone actually want to *buy* hosted noise mapping? | Demand is 25% of the score and is the sole reason NoiseModelling sits at 6.8 not 7.6 | 10 interviews with acoustic consultants; see Phase 0 |
| Real list prices for CadnaA / SoundPLAN / ResQ / Arius | WTP scores rest on "enterprise-priced", which is inference | Request a quote as a prospective buyer |
| Star counts / commit recency for ~45 longlist repos | Health filter #4 is unverified for most of the longlist | Re-run once GitHub search rate limits reset |
| Whether Data Octopus has traction | Decides whether IfcOpenShell is a 4 or a 7 on wrapper gap | Check their pricing page and any public customer count |
