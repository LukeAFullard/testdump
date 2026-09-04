# Deep dive #3 — `IfcOpenShell` → automated IFC/IDS model compliance checking

**Weighted score: 6.60 / 10. Below your 7.0 bar — but the only shortlist candidate that
passes every one of your hard gates.**

Ranked third on points, recommended first for action. The reasoning is in
`recommendation.md`; the short version is that the two higher scorers fail requirements
you wrote down as non-negotiable, and this one fails only on a contested market — which
is the one weakness Phase 0 can cheaply test.

---

## The repo

| Fact | Value | Source & date |
|---|---|---|
| Repo | `IfcOpenShell/IfcOpenShell` | [github.com/IfcOpenShell/IfcOpenShell](https://github.com/IfcOpenShell/IfcOpenShell), checked 2026-09-04 |
| Stars / forks | 2.8k / 959 | same page, 2026-09-04 |
| Open issues | 1.1k | same page, 2026-09-04 |
| Version | v0.9.0 shown on repo; PyPI `ifcopenshell` 0.8.5 uploaded 2026-04-13 | [pypi.org/pypi/ifcopenshell/json](https://pypi.org/pypi/ifcopenshell/json), 2026-09-04 |
| Licence | **LGPL-3.0-or-later** for the libraries | **Verified 2026-09-04**: [COPYING.LESSER](https://raw.githubusercontent.com/IfcOpenShell/IfcOpenShell/master/COPYING.LESSER) contains the LGPL-3.0 text, and the README states "IfcOpenShell is an open source (LGPL) software library". Grepped for Commons Clause / "may not sell" — **zero hits**. |
| **Licence trap** | The `blenderbim` / Bonsai add-on is **GPL-3.0-or-later** | README per-module licence table, 2026-09-04. **Do not link or vendor that module.** |
| Funding | Community donations via Open Collective | Repo page, 2026-09-04 |

**Why this matters:** the licence check here is exactly the case your brief warned about.
The repo's root `COPYING` file is the **GPL-3.0** text, which is what a careless check
(or the GitHub sidebar, which shows "LGPL-3.0 and GPL-3.0") would report. The libraries
are actually LGPL — confirmed by the presence of `COPYING.LESSER` alongside it, which is
the standard LGPL distribution pattern, plus the README's explicit statement and its
per-module table. **LGPL has no network-use clause, so a hosted SaaS calling these
libraries is clean**, provided you don't statically link modifications and don't touch
the GPL Blender add-on.

**What it does and why it's hard.** IFC is the ISO standard exchange format for building
models. IfcOpenShell parses it, and — the hard part — evaluates its *geometry* via an
OpenCASCADE-based kernel, so you can reason about actual shapes, not just attributes. It
also implements **IDS** (Information Delivery Specification), buildingSMART's standard for
expressing "this model must contain these objects with these properties". Parser plus
geometry kernel plus rule engine is a multi-year effort by specialists. **Verified** from
the README module table.

**Health:** strong. 2.8k stars, 959 forks, active PyPI releases. The 1.1k open issues are
a scope signal (it's a huge project), not abandonment. Passes hard filter #4.

## The gap

`ifcopenshell` is a Python library. Writing an IDS specification by hand means authoring
XML against a spec. Running checks means writing a script. Doing it on every model
revision means building CI.

The BIM Manager who *needs* this cannot do any of it. They received a model from a
subconsultant this morning, they suspect it's missing fire ratings on half the walls, and
their options are: open it in Solibri if the firm bought a seat, eyeball it in a viewer,
or accept it and find out during construction.

The product: connect a model source → author IDS rules in a UI → every new model revision
is checked automatically → get a report plus BCF issues that flow into the coordination
tools they already use → see whether quality is improving across revisions.

## The buyer

- **Role:** BIM Manager or BIM Coordinator. Sometimes titled Digital Delivery Lead.
- **Organisation:** 20–200 person architecture practice, MEP engineering consultancy, or
  a mid-size main contractor. Big enough to receive models from others, too small for a
  Solibri site licence.
- **Why them:** they are contractually accountable for model quality against a BIM
  Execution Plan, and they get blamed when bad data reaches site.
- **What they do today:** manual spot-checks in a free viewer; the
  [free buildingSMART validator](https://validate.buildingsmart.org/) for schema
  conformance; or nothing systematic. **Verified** that the free option exists.
- **Budget:** proven — [Solibri lists from ~$185/user/month](https://www.solibri.com/our-offerings)
  and BIMcollab Zoom runs ~€720/year. **Verified from vendor and comparison pages.**

## Evidence of demand

| Claim | Status | Evidence |
|---|---|---|
| Firms pay real money for model checking today | **Verified** | Solibri ~$185/user/mo; BIMcollab Zoom ~€720/yr; Solibri Premium quoted ~€2,772/yr in a comparison |
| IDS is a real, adopted standard with tooling | **Verified** | buildingSMART publishes it; IfcOpenShell implements it; [ifc-ids.com](https://ifc-ids.com/) and [Data Octopus](https://dataoctopus.net/) both build on it |
| Free basic validation already exists | **Verified — and this is bad news** | [validate.buildingsmart.org](https://validate.buildingsmart.org/), 250MB file limit, schema + normative rules |
| A paid PAYG competitor already exists | **Verified — worse news** | [Data Octopus](https://dataoctopus.net/) offers 3 free checks then pay-as-you-go IFC↔IDS checking |
| BIM Managers want *recurring, tracked* checking rather than one-off validation | **NOT VERIFIED** | This is the entire wedge and I have no direct evidence for it. Phase 0 exists to test exactly this. |

## Competitive landscape

| Product | Positioning | Pricing | Source |
|---|---|---|---|
| Solibri | Deep model checking, compliance, clash | from ~$185/user/month; Premium ~€2,772/yr | [solibri.com](https://www.solibri.com/our-offerings) |
| BIMcollab Zoom / Cloud | BCF issue management + IFC/IDS checking | Zoom ~€720/yr | [bimcollab.com](https://www.bimcollab.com/en/plans/bimcollab-full-platform/) |
| buildingSMART Validation Service | Free schema/normative conformance, 250MB limit | **Free** | [validate.buildingsmart.org](https://validate.buildingsmart.org/) |
| ifc-ids.com | Free, in-browser, no upload, no signup | **Free** | [ifc-ids.com](https://ifc-ids.com/) |
| Data Octopus | IFC↔IDS checker, 3 free then PAYG | PAYG | [dataoctopus.net](https://dataoctopus.net/) |
| Autodesk Navisworks | Clash detection, bundled with AEC Collection | Bundled | — |

**The wedge that's left — and it is narrow.** Everything above is either *one-off
validation* (upload a file, get an answer, leave) or *expensive per-seat desktop
software*. Nothing serves **continuous, automated, tracked** checking: rules authored
once, run on every revision, with history showing whether the model is getting better and
BCF issues pushed into the coordination workflow. That is a workflow product rather than
a validator, and workflow products retain where validators don't.

**Be clear-eyed:** this wedge is a hypothesis about buyer behaviour, not an observed gap.

## The product

**Core loop:** connect model source → rules run on every new revision → issues land in
the coordinator's workflow → quality trend is visible over time.

**v1 screens:** (1) project + model upload/connection; (2) IDS rule authoring in plain
language, exporting standards-compliant IDS XML; (3) run report — pass/fail per rule with
the offending elements listed; (4) BCF export; (5) revision-over-revision trend.

**Explicitly NOT in v1:** 3D viewer (buy or embed later — building one is a trap), clash
detection (Navisworks/Solibri own it, and it's a different algorithmic problem), model
authoring, cost/4D, direct Revit plugin.

**The 3D viewer decision matters.** Every instinct will say "add a viewer". Resist it
through v1: your value is the report and the trend, not the pixels, and a viewer is where
solo projects go to die.

## Business model

| Tier | Price | For |
|---|---|---|
| Solo | US$49/month | Independent BIM consultant, 3 projects |
| Team | US$199/month | Practice, 10 projects, 5 users |
| Firm | US$499/month | Unlimited projects, API, SSO |

Free tier: **yes, but bounded** — 3 model checks per month, files under 100MB. The free
tier here is a distribution channel, not charity: it competes directly with ifc-ids.com
for the top-of-funnel and costs little. Merchant of record: Paddle or Lemon Squeezy.

**Cost to serve:** the real variable. Large IFCs (500MB–2GB) need memory, and parsing is
minutes of CPU with multi-GB RAM. Budget **US$15–35 per active customer per month** on
queue workers that scale to zero. Cap file sizes per tier and make large-model processing
a Firm-tier feature. This is the axis to watch: if customers routinely push 2GB federated
models, gross margin degrades fast.

## Distribution plan

1. **OSArch and the openBIM community.** [community.osarch.org](https://community.osarch.org/)
   is where IfcOpenShell's actual users are, and they are unusually receptive to open
   tooling. Tactic: publish a free, genuinely useful IDS authoring tool (writing IDS XML
   by hand is the acknowledged pain point) and let it seed the paid product.
2. **Long-tail SEO against queries that currently return only GitHub, specs and forum
   threads.** Specifically: "how to write an IDS file", "IDS validation IFC free",
   "check IFC properties missing", "IFC quality check BIM execution plan",
   "BCF export from IFC check", "ifcopenshell IDS example", "IfcOpenShell check property
   set", "validate IFC against BIM execution plan", "IDS XML example fire rating",
   "automated IFC model checking CI". **Inferred from the results I saw; not
   volume-verified — do that in Phase 0.**
3. **buildingSMART chapters and BIM LinkedIn.** IDS is new enough that "how do I actually
   use IDS" content has an audience, and national chapters run events hungry for
   practical material.

Note the geography advantage: openBIM is strongest in Europe and Australasia, and
Australia/NZ has an active BIM community you can reach in your own timezone.

## Realistic financial model

Assumptions: launch month 5 (Python + a well-documented library makes this the fastest
build of the three); ARPU US$150; churn 4%/month (SMB software churns); free-to-paid
conversion 3%; infra scaling with usage; no paid acquisition.

| Month | Pessimistic customers / MRR | Base customers / MRR | Base infra cost |
|---|---|---|---|
| 5 | 0 / $0 | 2 / $200 | $60 |
| 9 | 3 / $350 | 12 / $1,500 | $250 |
| 12 | 6 / $700 | 24 / $3,300 | $450 |
| 18 | 11 / $1,300 | 45 / $6,400 | $800 |
| 24 | 16 / $1,900 | 68 / $9,900 | $1,200 |

**Base case month 24: ~US$119k ARR, ~US$105k after infra.**
**Pessimistic: ~US$23k ARR.**

The base case assumes the recurring-checking wedge is real. If BIM Managers only ever
want one-off validation, the free tools cap you at the pessimistic line permanently.

## Why this will fail

**Why hasn't anyone built it already?** Partly they have — Data Octopus sells PAYG IDS
checking and buildingSMART gives away validation. But the deeper reason is that
**construction buys software through firms, not individuals.** The BIM Manager who wants
your tool usually cannot expense $199/month without IT and finance sign-off, and the firm
that can sign off already has an Autodesk AEC Collection with Navisworks in it. The
individual enthusiasm you'll encounter at Phase 0 will not convert cleanly into card
swipes, and that gap between enthusiasm and purchase is the classic AEC-software killer.

**What happens when the upstream maintainer adds a hosted tier?** IfcOpenShell is
donation-funded with no commercial arm, so a direct hosted competitor is unlikely.
The realistic threat is **buildingSMART extending its free validation service to cover
IDS at scale**. They have the standard, the brand, the neutrality and no need to make
money. If they ship free recurring IDS validation, your product's reason to exist mostly
evaporates. This is the single largest strategic risk and it is entirely outside your
control.

**Realistic revenue ceiling.** Architecture/engineering/contracting firms in the 20–200
person band, in openBIM-adopting markets, with a BIM Manager, willing to buy self-serve:
plausibly tens of thousands globally, of which a solo operator might reach a few hundred.
At $150 ARPU that's a **ceiling around US$1–3M ARR**, realistically US$100–300k. A good
solo business, not a venture outcome.

**How do the first 50 paying customers find out?** The honest answer is the free IDS
authoring tool plus OSArch plus SEO, and it will take 12–18 months. There is no paid
acquisition channel that works at $150 ARPU in this market — AEC ad inventory is priced
for Autodesk. If the free tool doesn't spread on its own, you have no plan B, and that
is a genuine single point of failure in the distribution strategy.

**What breaks if the repo changes its API or licence?** LGPL-3.0 is irrevocable for
released versions and you could fork. The live risk is **API churn: the library is
pre-1.0** (PyPI 0.8.5, repo showing v0.9.0), and IfcOpenShell has historically made
breaking changes between minor versions. Your entire product sits on top of it. Mitigate
by pinning exact versions, wrapping every call behind your own interface, and holding a
regression corpus of real IFC files you re-run on every upgrade. Budget real time for
upgrades — treat them as projects, not chores.

**The thing that should worry you most:** your differentiation is workflow, not
technology. Anything you build, Data Octopus or BIMcollab can add. You are betting that
they won't bother with the small end of the market fast enough — a timing bet, not a moat.

## Risks and mitigations

| Risk | Severity | Mitigation |
|---|---|---|
| buildingSMART ships free recurring IDS validation | **High** | None structural. Differentiate on workflow (BCF, trends, integrations) rather than on validation itself. Watch their roadmap. |
| Free competitors cap willingness to pay | **High** | Price the free tier deliberately; make the paid value *recurrence and history*, which free one-off tools cannot match |
| Pre-1.0 API churn in IfcOpenShell | Medium-High | Pin versions; wrap the library; maintain a regression corpus of real IFCs |
| **GPL contamination via the Bonsai/BlenderBIM module** | **High if ignored, trivial if not** | Depend only on LGPL modules. Add a CI check asserting no GPL-licensed IfcOpenShell module is in the dependency tree. |
| Large-model compute erodes margin | Medium | Per-tier file-size caps; scale-to-zero workers; charge for big models |
| Firms buy through procurement, not cards | **High** | Target the individual consultant and small practice first; accept that mid-size firms need a different motion you may not want |
| Construction is slow to adopt | Medium | Long runway assumption baked into the model above |
| Licence revocation | Very low | LGPL-3.0 irrevocable for released code; fork is viable |
