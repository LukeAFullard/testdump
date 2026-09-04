# Deep dive #2 — `Arelle/Arelle` → XBRL/iXBRL for small filers

**Weighted score: 6.80 / 10. Below your 7.0 bar. Partially fails your passivity gate,
and sits inside a domain you asked me to avoid.**

---

## The repo

| Fact | Value | Source & date |
|---|---|---|
| Repo | `Arelle/Arelle` | [github.com/Arelle/Arelle](https://github.com/Arelle/Arelle), checked 2026-09-04 |
| Stars / forks | 232 / **359** | same page, 2026-09-04 — note forks exceed stars, the signature of a library that gets embedded rather than admired |
| Open issues | 92 | same page, 2026-09-04 |
| Commits | 10,253 on `master` | same page, 2026-09-04 |
| Licence | **Apache-2.0** | Read from [LICENSE.md](https://raw.githubusercontent.com/Arelle/Arelle/master/LICENSE.md), 2026-09-04. Grepped for Commons Clause / "may not sell" — **zero hits**. |
| PyPI | `arelle-release` 2.44.7, uploaded **2026-09-03** | [pypi.org/pypi/arelle-release/json](https://pypi.org/pypi/arelle-release/json), checked 2026-09-04 |
| Maintainer | The Arelle organisation, support@arelle.org | Repo page, 2026-09-04 |

**What it does and why it's hard.** XBRL is the machine-readable format regulators
require for financial statements. Arelle is a full processor — taxonomies, dimensions,
calculation and definition linkbases, formula linkbase, inline XBRL extraction — and it
is **certified by XBRL International as a Validating Processor**, with built-in support
for filer-specific rule sets including the SEC's Edgar Filer Manual and the ESMA ESEF
Reporting Manual. The specification stack is genuinely brutal; correctness here is a
multi-year effort. **Verified** from the project's own documentation.

**Health: excellent — the best on the shortlist.** 10,253 commits and a release uploaded
the day before I checked it. Comfortably passes hard filter #4.

**Licence: Apache-2.0.** Permissive, patent grant included, no service restriction. As
clean as it gets. **Verified by reading the file.**

## The gap

Arelle is a processor with a GUI, a CLI, a Python API and a web-service API. A large
filer hands it to its finance-systems team. A 40-person listed company in Helsinki, or a
UK small company that must file iXBRL accounts, has nobody to hand it to.

The product would be: upload your accounts (Excel or Word) → map facts to the taxonomy
with assistance → generate valid iXBRL → validate against the regulator's rule set →
download the filing package with a plain-English report of what would have been rejected.

## The buyer

- **Role:** Financial Controller or Group Reporting Manager (not the CFO — the person who
  actually assembles the filing).
- **Organisation:** a small listed company in an ESEF jurisdiction (EU regulated market),
  or a small accounting practice that files iXBRL accounts on behalf of client companies.
- **The accounting practice is the better ICP.** They file many times per year, feel the
  pain repeatedly, buy tools without a procurement committee, and already pay for filing
  software.
- **What they do today:** pay a service bureau per filing, or use their existing
  accounts-production software's iXBRL module, or outsource the tagging entirely.

## Evidence of demand

| Claim | Status | Evidence |
|---|---|---|
| iXBRL filing is legally mandatory in major jurisdictions | **Verified** | Arelle ships rule sets for SEC EFM and ESEF Reporting Manual; [XBRL International lists certified software](https://software.xbrl.org/) |
| The engine is in live institutional use | **Verified** | PyPI release dated 2026-09-03; 10,253 commits |
| A large commercial market exists on top of it | **Verified** | [Workiva describes its investment in Arelle](https://www.workiva.com/solutions/xbrl-and-ixbrl) and claims more iXBRL facts filed with the SEC than any other provider |
| Small filers are underserved specifically | **Inferred** | Follows from the vendor list skewing enterprise; I did not verify pricing at the small end |
| Anyone is asking for a cheaper self-serve option | **NOT VERIFIED** | No dated forum post, issue, or job listing found |

## Competitive landscape

| Product | Positioning | Pricing | Source |
|---|---|---|---|
| Workiva | Enterprise reporting platform; largest SEC iXBRL filer | Enterprise, quote-only | [workiva.com](https://www.workiva.com/solutions/xbrl-and-ixbrl) |
| ParsePort | ESEF/iXBRL conversion specialist; now Workiva-associated | Quote-only | [Workiva support page for ParsePort](https://support.workiva.com/hc/en-us/articles/43991137319956-ParsePort-Conversion-Tool) |
| Certified vendor list | Dozens of certified processors | Various | [software.xbrl.org](https://software.xbrl.org/) |
| Arelle itself | Free, technical | Free | [arelle.org](https://arelle.org/arelle/) |

**This is the problem.** The wrapper is not missing — it is *crowded*, and the biggest
wrapper is a public company that actively invests in the same open-source engine you'd be
building on. Your wedge is only the bottom of the market, where the buyers are least
willing to pay and the incumbent is "our accounts software already does it."

## The product

**Core loop:** upload accounts → assisted tagging against the taxonomy → validate →
download filing package.

**v1 screens:** (1) upload; (2) tagging workspace with taxonomy search and suggestions;
(3) validation results in plain English, ranked by whether they block acceptance;
(4) package download + filing checklist.

**Explicitly NOT in v1:** direct submission to regulators (that requires credentials and
accreditation you don't want), consolidation, multi-entity, audit workflow, XBRL taxonomy
authoring.

## Business model

| Tier | Price | For |
|---|---|---|
| Per-filing | €249 per filing | Occasional filer |
| Practice | €399/month, 10 filings | Small accounting practice |
| Unlimited | €999/month | Practice with a filing season |

Per-filing pricing matches how the buyer thinks about the cost. Merchant of record
(Paddle/Lemon Squeezy) handles EU VAT — essential here since the market is EU-centric and
you are not.

**Cost to serve:** validation is CPU-cheap; the cost is storage and a queue. **€2–6 per
customer per month.**

## Distribution plan

1. **A free public validator.** Put ESEF/iXBRL validation online for free, no signup, and
   let it rank. This is the single strongest move: it is genuinely useful, it costs
   almost nothing to serve, and it puts you in front of exactly the person with a filing
   problem at the moment they have it.
2. **Long-tail SEO on error messages.** Filers search the literal validation error text.
   Publish a page per common ESEF/EFM error code explaining what it means and how to fix
   it. These queries currently return specification PDFs and vendor brochures.
   **Inferred from search behaviour, not volume-verified.**
3. **Accounting-practice channels** — professional body newsletters and LinkedIn groups
   for small practices in ESEF jurisdictions.

## Realistic financial model

Assumptions: launch month 7 (the tagging UI is the long pole); ARPU €350; churn 3%/month
(practices churn when filing season ends); infra €200–500/month; heavy seasonality around
filing deadlines.

| Month | Pessimistic customers / MRR | Base customers / MRR |
|---|---|---|
| 7 | 0 / €0 | 2 / €500 |
| 12 | 3 / €800 | 10 / €3,200 |
| 18 | 6 / €1,800 | 22 / €7,300 |
| 24 | 9 / €2,800 | 34 / €11,500 |

**Base case month 24: ~€138k ARR. Pessimistic: ~€34k ARR.** The seasonality is real —
expect most revenue and nearly all support load compressed into two or three months.

## Why this will fail

**Why hasn't anyone built it already?** They have. Repeatedly. There is a
[certified-vendor list](https://software.xbrl.org/) with dozens of entries. The reason
nobody has built the *cheap self-serve* version is that filings are high-stakes and
low-frequency: a controller files once or twice a year, and when the alternative to
€249 is "my accounts software already produces it" or "the service bureau charges €800
and takes responsibility", the cheap tool loses. Low frequency also destroys the SaaS
retention model — you're selling an annual event, not a habit.

**What happens when the maintainer adds a hosted tier?** Arelle is a non-profit
organisation and unlikely to. The realer version: **Workiva already funds Arelle's
development.** You would be building a business on an engine partly sustained by the
market leader, who can match any feature and outspend you on trust.

**Realistic revenue ceiling.** Small filers in ESEF jurisdictions plus small practices
that would buy self-serve: a few thousand, reachable maybe in the hundreds. **Ceiling
around €500k–1M ARR**, realistically far less.

**How do the first 50 paying customers find out?** The free validator is a genuinely good
answer here — better than for either other candidate — because the search intent is sharp
and transactional. But conversion from "validated my file free" to "paid €249" is
unproven, and 50 customers in a market this specialised is a year of work.

**What breaks if the repo changes?** Apache-2.0 is irrevocable for released code. The
real fragility is different: **regulators change their rule sets annually.** If Arelle
lags a rule-set update, your customers' filings fail at the worst possible moment and it
is your brand that wears it. You would be permanently downstream of someone else's
release schedule during the only weeks that matter.

**The gate problem:** filing deadlines mean support load arrives in a spike. A solo
operator in New Zealand serving European filing deadlines will be answering urgent
questions in the wrong timezone during the exact weeks the customer cannot wait. That is
a direct hit on your passivity and location-agnostic requirements.

## Risks and mitigations

| Risk | Severity | Mitigation |
|---|---|---|
| Deadline-driven support spikes in a hostile timezone | **High** | Extensive self-serve docs; explicit SLA disclaiming real-time support; avoid the submission step entirely |
| Regulator rule-set changes break filings | **High** | Track Arelle releases; automated regression tests against sample filings; publish a status page |
| Workiva/ParsePort move down-market | Medium | Compete on price and speed only |
| Financial-reporting adjacency | Medium | **Flagged explicitly:** you asked to avoid financial regulation. You would not be a regulated entity, but you'd be in the failure path of a regulated filing. |
| Low purchase frequency kills retention | **High** | Per-filing pricing rather than pretending it's a subscription |
| Licence change | Very low | Apache-2.0, non-profit steward |
