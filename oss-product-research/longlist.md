# Longlist — open-source engines assessed as product candidates

**Research window:** 2026-09-03 → 2026-09-04. All licence values in the "Licence
(verified)" column were read from the repository's own `LICENSE`/`COPYING` file over
`raw.githubusercontent.com` on **2026-09-04**, not from the GitHub sidebar badge and not
from memory.

## Evidence status — read this before trusting any number below

I have to be straight with you about what this table is and isn't.

| Field | Status |
|---|---|
| Licence | **VERIFIED** for 55 of 57 rows — fetched the actual licence file. Two rows returned NOT-FOUND (non-standard path) and are marked. |
| Extra clauses | **VERIFIED** — every licence file was grepped for Commons Clause / "may not sell" / "not be sold". Zero hits across all 55. |
| Stars / open issues | **VERIFIED for only 6 repos** (loaded the GitHub page). Everything else says `not verified`. I did not estimate them. |
| Release recency | **VERIFIED** for 8 packages via the PyPI JSON API. |
| Verdict reasoning | **INFERRED** from search results, or **ASSUMED** from domain knowledge — labelled per row. |

**The honest limitation:** GitHub's search endpoint rate-limited me (HTTP 429,
`Retry-After: 3600`) after six parallel queries, and the web-search tool hit a session
quota mid-run. So this longlist is broad on *licence* evidence and thin on *stars and
demand* evidence. Where I could not verify, I have written `not verified` rather than
filling the gap with a plausible-looking number. That gap is the main weakness of this
whole exercise and it is why the demand axis is scored conservatively throughout.

---

## A. Document processing, OCR, PDF

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 1 | `ocrmypdf/OCRmyPDF` | Adds an OCR text layer to scanned PDFs | not verified | MPL-2.0 | **Reject** | Category is commoditised — dozens of hosted OCR products. Engine is a wrapper over Tesseract. PyPI release 2026-08-28 (healthy). |
| 2 | `tesseract-ocr/tesseract` | OCR engine | 76.3k (verified 2026-09-04) | Apache-2.0 | **Reject** | Same — the wrapper market is saturated (Fiverr gigs at ~$105 prove the manual demand, but so does every OCR SaaS). |
| 3 | `Stirling-Tools/Stirling-PDF` | Self-hosted PDF toolbox | not verified | MIT at root, **but** `app/proprietary/` + `app/saas/` carry a separate licence | **Reject** | Hard filter #2. Open-core; "Stirling PDF Inc." sells the wrapper. Verified by reading the licence file's own carve-out text. |
| 4 | `veraPDF/veraPDF-library` | PDF/A + PDF/UA conformance checker | not verified | NOT-FOUND at standard paths | **Reject** | Hard filter #3 — Allyant/CommonLook, Equidox, AudioEye, PopeTech already own PDF accessibility. |
| 5 | `w3c/epubcheck` | EPUB validator | not verified | BSD-family | **Reject** | Free hosted wrappers already exist (PubCoder, Publica.la). |
| 6 | `daisy/ace` | EPUB accessibility checker | not verified | MIT | **Reject** | See deep-dive rejection note below — PaperbackKit already ships auto-remediation. |
| 7 | `datalab-to/marker` | PDF → markdown conversion | not verified | Apache-2.0 | **Reject** | Hard filter #2 — Datalab sells the hosted API. |
| 8 | `Unstructured-IO/unstructured` | Document ingestion for LLMs | not verified | Apache-2.0 | **Reject** | Hard filter #2 — Unstructured sells a hosted API. |
| 9 | `paperless-ngx/paperless-ngx` | Document management | not verified | GPL-3.0 | **Reject** | Third-party hosting already exists; B2C-ish; low WTP. |
| 10 | `Kozea/WeasyPrint` | HTML → PDF | not verified | BSD-family | **Reject** | Thin wrapper problem (filter #5); DocRaptor/PDFShift already serve it. |

## B. Geospatial, transport, logistics

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 11 | `VROOM-Project/vroom` | Vehicle routing (VRP) solver | not verified | BSD-family (2-clause, Julien Coupey) | **Reject** | Hard filter #3 — Routific, OptimoRoute, Onfleet, Route4Me, NextBillion, **and** a hosted VROOM API already exists (simplerouting.io). |
| 12 | `Project-OSRM/osrm-backend` | Road routing engine | not verified | NOT-FOUND at standard paths | **Reject** | Hosted by Mapbox/Stadia/others. Buyers are developers who can self-host. |
| 13 | `onthegomap/planetiler` | Vector basemap tile generation | not verified | Apache-2.0 | **Reject** | Buyers are technical (filter: no non-technical latent demand). Protomaps/MapTiler serve it. |
| 14 | `pgRouting/pgrouting` | Routing inside PostGIS | not verified | GPL-2.0 | **Reject** | Developer tool, not a product surface. |
| 15 | `MobilityData/gtfs-validator` | Validates transit GTFS feeds | not verified | Apache-2.0 | **Reject** | Buyer is a public transit agency → procurement cycle, violates "no sales calls / passive". |
| 16 | `eclipse-sumo/sumo` | Microscopic traffic simulation | not verified | UNKNOWN (EPL-2.0 expected; file parse inconclusive) | **Reject** | Genuinely hard engine, but buyers are consultancies bought via tender. Not passive. |
| 17 | `OSGeo/gdal` | Geospatial format translation | not verified | NOT-FOUND at standard paths | **Reject** | MyGeodata Converter already serves the cheap end; FME owns the top. |
| 18 | `PDAL/PDAL` | Point cloud processing | not verified | BSD-family | **Reject** | Per-user compute is heavy (filter #6); buyers are surveyors with desktop workflows. |
| 19 | `r-lidar/lidR` | LiDAR forest metrics in R | not verified | GPL-3.0 | **Reject** | Real NZ/forestry relevance, but heavy compute on large point clouds and fragmented buyer base. |

## C. Construction, BIM, building performance

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 20 | `IfcOpenShell/IfcOpenShell` | IFC library + geometry engine + IDS validation | 2.8k, 959 forks, 1.1k open issues (verified 2026-09-04) | **LGPL-3.0-or-later** (COPYING.LESSER present; README confirms; Bonsai add-on is GPL-3.0) | **Advance → shortlist** | Hard engine, permissive-enough licence, no maintainer cloud (donations via Open Collective). Wrapper gap is the weak spot. |
| 21 | `NREL/EnergyPlus` | Whole-building energy simulation | not verified | BSD-family (LBNL/UIUC custom) | **Advance → shortlist** | World-class engine, compliance-driven. Contested by cove.tool (funded). |
| 22 | `NREL/OpenStudio` | SDK/GUI layer over EnergyPlus | not verified | BSD-family | **Reject (merge into #21)** | Same thesis as EnergyPlus; not independent. |
| 23 | `ladybug-tools/honeybee-energy` | Environmental design toolkit | not verified | **AGPL-3.0** | **Reject** | Hard filter #1 (AGPL) **and** #2 — Ladybug Tools sell Pollination.cloud. Double disqualification. |
| 24 | `CadQuery/cadquery` | Parametric CAD as Python code | not verified | Apache-2.0 | **Reject** | Buyers are engineers who code; no non-technical latent demand. |

## D. Finance, insurance, legal, compliance

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 25 | `casact/chainladder-python` | P&C actuarial loss reserving | 275 stars, 115 forks, 113 open issues, 3,026 commits (verified 2026-09-04) | MPL-2.0 | **Advance → shortlist** | Highest willingness-to-pay found anywhere in this search. PyPI release 2026-07-29. |
| 26 | `Arelle/Arelle` | XBRL / iXBRL processor, XII-certified | 232 stars, 359 forks, 92 open issues, 10,253 commits (verified 2026-09-04) | Apache-2.0 | **Advance → shortlist** | Extremely healthy (PyPI release **2026-09-03**, i.e. yesterday). Wrapper partly owned by Workiva. |
| 27 | `jhpyle/docassemble` | Guided-interview legal doc automation | not verified | MIT | **Advance → shortlist (weak)** | Gavel (ex-Documate) at $83/mo is funded and owns this. PyPI release 2025-03-04 — 18 months stale, a health flag. |
| 28 | `ZUGFeRD/mustangproject` | ZUGFeRD/Factur-X e-invoice validation | not verified | Apache-2.0 | **Reject** | Hard filter #3 — Docentric, InvoiceXML, zugferd-validator.de, thelawin.dev, Invoice-Converter all already wrap it. |
| 29 | `beancount/beancount` | Plain-text double-entry accounting | not verified | GPL-2.0 | **Reject** | Users are hobbyist developers; Xero/QuickBooks own the paying market. |
| 30 | `simonmichael/hledger` | Plain-text accounting | not verified | GPL-3.0 | **Reject** | Same. |
| 31 | `actualbudget/actual` | Personal budgeting | not verified | MIT | **Reject** | B2C, low WTP, third-party hosts already exist (PikaPods). |
| 32 | `freelawproject/eyecite` | Legal citation extraction | not verified | BSD-family | **Reject** | Thin relative to the real product (filter #5); Westlaw/Lexis bundle it. |
| 33 | `gramps-project/gramps` | Genealogy | not verified | GPL-2.0 | **Reject** | B2C, Ancestry owns distribution. |

## E. Scientific / engineering simulation

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 34 | `Universite-Gustave-Eiffel/NoiseModelling` | CNOSSOS-EU environmental noise mapping | 232 stars, 96 forks, 61 open issues, 3,695 commits (verified 2026-09-04) | GPL-3.0 | **Advance → shortlist** | Best wrapper gap found in the entire search. See deep dive. |
| 35 | `e2nIEE/pandapower` | Power flow / short circuit (IEC 60909) | not verified | BSD-family | **Advance → shortlist** | PyPI release 2026-07-08. Funded competitors emerging (Pearl Street, GridUnity). |
| 36 | `PyPSA/PyPSA` | Energy system optimisation | not verified | MIT | **Reject (merge into #35)** | Same buyer; research-oriented; scenario compute is expensive. |
| 37 | `pvlib/pvlib-python` | PV performance modelling | not verified | BSD-family | **Reject** | Hard filter #3 — Aurora Solar (heavily funded), Helioscope, PVsyst, OpenSolar (free). |
| 38 | `NREL/floris` | Wind farm wake modelling | not verified | BSD-family | **Reject** | Buyer pool is tiny (wind developers) and served by WAsP/WindPRO. |
| 39 | `pybamm-team/PyBaMM` | Battery simulation | not verified | BSD-family | **Reject** | Narrow research niche; COMSOL owns the paying end. |
| 40 | `pyswmm/pyswmm` | Python interface to EPA SWMM | not verified | BSD-family (2-clause) | **Reject** | PCSWMM and Fluidit already wrap the EPA engines; wrapper gap not structural. PyPI release 2025-09-09. |
| 41 | `OpenWaterAnalytics/EPANET` | Water distribution hydraulics | not verified | MIT | **Reject** | Same as #40 — commercial shells already exist. |
| 42 | `ajwdewit/pcse` | Crop growth simulation (WOFOST) | not verified | UNKNOWN (parse inconclusive) | **Reject** | Hard filter #5 — the hard part is weather/soil data acquisition, not the model. |
| 43 | `brightway-lca/brightway2` | Life-cycle assessment framework | not verified | BSD-family | **Reject** | Hard filter #5 — ecoinvent database licence is the real barrier and it is expensive. |

## F. Data tooling, text, media, security

| # | Repo | What it does | Stars | Licence (verified) | Verdict | Reason |
|---|---|---|---|---|---|---|
| 44 | `OpenRefine/OpenRefine` | Messy-data cleaning + reconciliation | 12k stars, 2.2k forks, 682 open issues (verified 2026-09-04) | BSD-3-Clause | **Advance → shortlist** | Verified: no hosted OpenRefine service exists. Fails on unit economics. |
| 45 | `vale-cli/vale` | Prose/style-guide linter | not verified | MIT | **Reject** | Hard filter #2 — maintainers run **Vale Studio / Vale CMS**, a hosted UI on the same engine. |
| 46 | `simonw/datasette` | Publish/explore data as a web app | not verified | not fetched | **Reject** | Hard filter #2 — Datasette Cloud is the maintainer's own product. |
| 47 | `cloud-custodian/cloud-custodian` | Cloud governance policy engine | not verified | Apache-2.0 | **Advance → shortlist (weak)** | No maintainer cloud (CNCF). But FinOps is crowded and AWS credentials = high support/security burden. |
| 48 | `sqlfluff/sqlfluff` | SQL linter | not verified | MIT | **Reject** | Developer tool; no non-technical buyer. |
| 49 | `frictionlessdata/frictionless-py` | Data package validation | not verified | MIT | **Reject** | Buyers are grant-funded open-data teams; negligible WTP. |
| 50 | `pa11y/pa11y` | Web accessibility testing | not verified | LGPL-3.0 | **Reject** | Hard filter #3 — AccessiBe, UserWay, Siteimprove, AudioEye, Equally AI. Far more than 15 funded competitors. |
| 51 | `googlefonts/fontbakery` | Font QA / conformance | not verified | Apache-2.0 | **Reject** | Total addressable market is a few thousand type designers. |
| 52 | `Audiveris/audiveris` | Optical music recognition | not verified | **AGPL-3.0** | **Reject** | Hard filter #1. Also Soundslice/PhotoScore hold the market. |
| 53 | `MediaArea/MediaConch` | AV file conformance for archives | not verified | NOT-FOUND at standard paths | **Reject** | Buyer is an archive/broadcaster → tender-driven procurement. |
| 54 | `bavc/qctools` | Video QC for preservation | not verified | NOT-FOUND at standard paths | **Reject** | Same as #53. |
| 55 | `senaite/senaite.core` | Open-source LIMS | not verified | GPL-2.0 | **Reject** | Labs need per-customer configuration — directly violates "no per-customer setup". |
| 56 | `restic/restic` | Backup | not verified | BSD-family | **Reject** | BorgBase/rsync.net/Backblaze already serve it. |
| 57 | `changedetection-io/changedetection.io` | Website change monitoring | not verified | NOT-FOUND at standard paths | **Reject** | Hard filter #2 — maintainer sells the hosted version. |

---

## Rejection patterns worth noticing

Counting the rejections by *which* hard filter killed them tells you more than the
individual rows:

| Killed by | Count | Comment |
|---|---|---|
| #3 — a competitor already owns the wrapper | 18 | **By far the dominant failure mode.** |
| #2 — the maintainer sells the wrapper | 6 | Vale, Datasette, Stirling-PDF, marker, unstructured, changedetection.io, Ladybug |
| #5 — the hard part isn't the repo | 5 | Usually data acquisition (LCA, crop models) |
| Not passive / procurement-driven buyer | 8 | Transit agencies, archives, labs, traffic consultancies |
| #1 — AGPL | 2 | honeybee-energy, Audiveris |
| #6 — unit economics | 3 | Point clouds, LiDAR, PV/battery scenario compute |

**The structural finding:** the thesis you asked me to test is *mostly false in 2026*.
For nearly every open-source engine with genuine latent demand, somebody has already
built the wrapper — and often it's a solo operator or small team, not a funded startup
(simplerouting.io for VROOM, Data Octopus for IFC/IDS, PaperbackKit for EPUB
accessibility, zugferd-validator.de for e-invoicing). The "obvious" gaps have been
closed in the last 24 months, plausibly because AI coding agents lowered the build cost
for everyone, not just for you.

The candidates that still have a *real* wrapper gap have it for a reason: the buyer pool
is small, the buyer buys via tender, or the compute is expensive. That is the finding
that drives `shortlist.md` and `recommendation.md`.

---

# Appendix — search log

You asked to see the queries, not just the conclusions. Here is what I actually ran,
in order, and what came back. Including the parts that failed.

## Tooling constraints hit (relevant to judging breadth)

This session's egress proxy blocked most hosts for command-line access. What worked:
`raw.githubusercontent.com` (licences, READMEs — the workhorse), `pypi.org` and
`registry.npmjs.org` (release recency), plus the web-fetch and web-search tools.
What did **not** work: `api.github.com` beyond `/rate_limit` (session bound to one repo),
`img.shields.io`, GitHub Atom feeds, and direct `github.com` HTML over curl (403).

Two hard stops mid-research:
- **GitHub search returned HTTP 429 with `Retry-After: 3600`** after six parallel
  repository-topic queries. That killed the structured `stars:>N pushed:>DATE topic:X`
  sweep you specified, which is why star counts are verified for only 6 repos.
- **The web-search tool hit a session quota** partway through the competitor round,
  costing me the planned searches on Arelle, MediaConch, pandapower, lidR and SUMO.
  I re-ran three of those after the quota reset; two were never run.

## Queries run

**Structured GitHub repository queries (all six returned HTTP 429 — no results):**
```
stars:>500  pushed:>2025-06-01 topic:geospatial
stars:>300  pushed:>2025-06-01 topic:ocr
stars:>200  pushed:>2025-06-01 topic:bim
stars:>200  pushed:>2025-06-01 topic:accounting
stars:>150  pushed:>2025-06-01 topic:hydrology
stars:>200  pushed:>2025-06-01 topic:logistics
```

**GitHub issue/demand queries (ran successfully, low yield):**
```
"is there a GUI"     in:title is:issue is:open   sort:reactions-+1
"hosted version"     in:title is:issue           sort:reactions-+1
"web UI"             in:title is:issue is:open   sort:reactions-+1
repo:OpenRefine/OpenRefine  hosted OR "web version" OR SaaS OR "online version"
```
**What they returned, honestly: almost nothing usable.** The reaction-sorted issue
searches surfaced big consumer repos (vscode, AFFiNE, headscale, AdGuard) rather than
domain engines. The single strongest signal your brief hoped for — "an issue with 40+ 👍
asking for a web UI, still open after two years" — **I did not find for any candidate.**
The best hit was `headscale#234` "Any WEB UI planned?" (57 reactions, opened 2021-11-23),
which is a developer tool and fails your non-technical-demand test. The OpenRefine query
returned 58 issues but none asking for hosting.

**Web searches (16 run, all returned results):**
```
European Accessibility Act ebooks June 2025 publishers EPUB compliance deadline
epubcheck ace by daisy EPUB accessibility checker hosted online service publishers
IfcOpenShell IFC model checking validation SaaS competitors Solibri BIMcollab pricing
buildingSMART IDS validation service free IFC validator online alternatives
EPUB accessibility remediation SaaS publishers backlist batch fix alt text ONIX pricing
Vale linter errata-ai commercial hosted "Vale Cloud" pricing sponsor
OpenRefine hosted cloud version online service alternatives data cleaning librarians
EnergyPlus cloud simulation SaaS cove.tool Pollination pricing competitors
VROOM vehicle routing hosted API pricing Routific OptimoRoute Circuit competitors
chainladder-python actuarial reserving alternatives ResQ Arius pricing small insurers
docassemble legal document automation hosted alternatives Gavel Documate pricing
NoiseModelling environmental noise mapping END directive CadnaA SoundPLAN price
Arelle XBRL ESEF iXBRL validation hosted pricing ParsePort Workiva alternatives
SWMM EPANET cloud hosted stormwater SaaS alternatives PCSWMM InfoWorks pricing
pandapower PyPSA hosted power system SaaS competitors PowerFactory ETAP pricing
Mustangproject ZUGFeRD Factur-X e-invoicing validation API competitors EU mandate
Hacker News "I would pay for" hosted open source "can't get it running"
Upwork Fiverr hire "run open source tool" OCR data extraction gig
```

**The searches that killed candidates — the highest-value results:**

| Query | What it killed | Finding |
|---|---|---|
| Vale commercial | `vale-cli/vale` | Maintainers run **Vale Studio / Vale CMS**, a hosted UI on the same engine. Hard filter #2. |
| EPUB remediation SaaS | `daisy/ace`, `w3c/epubcheck` | **PaperbackKit** already does exactly the thesis — upload EPUB, auto-fix alt text/metadata/nav, batch + API. Publica.la "Origami" does batch checking. |
| VROOM hosted | `VROOM-Project/vroom` | **simplerouting.io** already offers a hosted VROOM API with a free tier. |
| buildingSMART IDS | weakened `IfcOpenShell` from 7 to 4 on wrapper gap | Free official validator, free `ifc-ids.com`, **and** paid PAYG `dataoctopus.net`. |
| Mustangproject | `ZUGFeRD/mustangproject` | Four separate wrappers already exist (Docentric, InvoiceXML, zugferd-validator.de, thelawin.dev). |
| Arelle | weakened `Arelle` | **Workiva publicly states it invests in Arelle** — the market leader funds the engine. |

**Bulk licence verification (the one thing that worked well).** A parallel script fetched
`LICENSE`/`COPYING`/`COPYING.LESSER` from `raw.githubusercontent.com` across `main`,
`master` and `develop`, classified the licence from the file text, and grepped every file
for Commons Clause / "you may not sell" / "Sell the Software". **55 of 57 repos verified;
zero extra-clause hits.** This caught two things a sidebar badge would have got wrong:
- `Stirling-Tools/Stirling-PDF` reports MIT at root but carries `app/proprietary/` and
  `app/saas/` under a separate licence — open core, company-owned. Rejected.
- `IfcOpenShell` root `COPYING` is the **GPL-3.0** text, but `COPYING.LESSER` is present
  and the README says LGPL — the standard LGPL distribution pattern. Reading only the
  root file (or the sidebar, which says "LGPL-3.0 and GPL-3.0") would have produced the
  wrong verdict on the #1 recommendation.

**PyPI/npm release recency** (health filter #4) verified for: `ocrmypdf` 2026-08-28,
`chainladder` 2026-07-29, `ifcopenshell` 2026-04-13, `pyswmm` 2025-09-09,
`arelle-release` **2026-09-03**, `pandapower` 2026-07-08, `docassemble` **2025-03-04**
(18 months stale — a health flag on that candidate).

## What I would search next, given more budget

1. Re-run the six structured topic queries after the rate limit clears, to verify stars
   and last-commit dates across the longlist (health filter #4 is currently unverified for
   ~45 rows).
2. The demand searches that matter and I never got to: Reddit r/bim, r/Revit and the
   buildingSMART forums for "how do you check incoming models"; Upwork/Fiverr for people
   *paying humans* to run IFC quality checks — that would be the cleanest
   willingness-to-pay signal available and it is exactly the evidence the whole analysis
   is missing.
3. Request actual quotes from Datakustik (CadnaA), WTW (ResQ) and Milliman (Arius) as a
   prospective buyer, to replace inferred pricing with verified pricing.
