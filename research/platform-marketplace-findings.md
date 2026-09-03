# Platform & Accounting Marketplace Findings (2026-09-03)

[S] = web-search summary + URL; [I] = inference.

## THE HEADLINE: both dominant accounting platforms moved from "free distribution" to "pay to scale" within 12 months

### Xero retired its 15% revenue share on 2 March 2026
Replaced with a five-tier **developer platform fee based on connected orgs + monthly data egress**:
Starter **$0 / 5 connections** → Core → Plus → Advanced **$895/mo / 10,000 connections** → Enterprise (negotiated).
Egress overage **$2.40 AUD/GB** once free allowances (10/50/250 GB by tier) are exceeded.
**At least one existing developer reported their bill going from near-zero to >$17,000/year overnight.** [S] Accounting Today, ecommercenews.co.nz, publicaccountant.com.au, developer.xero.com/pricing
> A solo operator launches free on Starter (5 connected orgs) — fine for validation — but **the cost of crossing into Core/Plus at scale is an unknown; those two tiers' dollar figures were not found.** This must be modelled before writing a line of code.

### QuickBooks/Intuit made the parallel move
**App Partner Program** announced May 2025, live **28 July 2025**: flat monthly program fee by developer tier **plus usage-based API fees** as the customer base grows. [S] Intuit investor release

## Marketplace mechanics
| Marketplace | Gate | Fees | Discovery reality |
|---|---|---|---|
| **Xero App Store** | Certified App Partner: working integration + **≥3 active customers onboarded within a 30-day review window**; Sign-Up-with-Xero; evangelist review [S] | See above | >1,000 apps, 30+ categories [S] |
| **QuickBooks** | 3 gates: Technical (~3 days, 14 checks) → **Security (~7 days incl. penetration testing**, must remediate critical/high/medium) → Marketing (~5 days). **Annual re-review** [S] | New tiered program + usage fees | Not quantified |
| **Shopify** | Rebuilt submission pipeline Apr 2026 after Shopify admitted Feb 2026 review times blew out [S] | **15% up to $1M lifetime per app** (no longer resets annually), 20% above; free apps pay nothing [S] | **18,062 apps live, +610 in 30 days, +52% YoY new-app growth** as of 29 Apr 2026 — genuinely flooded [S] appstoreresearch.com. New anti-fake-review policy 6 Jul 2026 |
| **Atlassian** | Cloud Fortified being retired end-2026, replaced by "Atlassian Enterprise Certified" [S] | Connect apps **15% → 20% (1 Jan 2026) → 25% (1 Jul 2026)** — steep and fast-rising [S] | Not quantified |
| **WordPress.org** | Review backlog ~7 days in 2026; mandatory automated Plugin Check since Oct 2025 | Free, no rev-share | Not quantified |
| **Chrome Web Store** | Stricter "Limited Use" data policy enforced **from 1 Aug 2026** [S] | Free | "Flooded" with AI extensions; enforcement uneven — a banned extension returned under a new name [S] |
| **Zapier** | HTTPS API + OAuth2, dedicated test account, 2–4 week approval, no re-review [S] | Not found | Not quantified |
| **Make.com** | ~4–6 week review; **app must wrap a service not already integrated** (blocks duplicates) [S] | Not found | Not quantified |

## Candidate: NZ Construction Retention-Money Trust Compliance Ledger (Xero)
- **Construction Contracts (Retention Money) Amendment Act 2023**: retention money must be held on trust in a **separate NZ-registered bank account used solely for that purpose**, with quarterly reporting to every subcontractor. Fines to **$200,000 per offence plus $50,000 per director**. [S] legislation.govt.nz, Anderson Lloyd, Wynn Williams
- 5 named apps already in the Xero NZ store touch this: Retention Track, Payapps, Gojee, Workbench, RemitClear [S] — proves the segment pays.
- **Retention Track — closest positioning — had ZERO reviews** at time of search [S]: either very new or weak traction.
- None are pitched as *pure compliance* tools; they're job-management platforms with retention as a feature [I].
- Commencement/phase-in date of full obligations **NOT VERIFIED**.
- **Compliance flag:** never touch the money — tracking/reporting only — or risk NZ FSP Act 2010 and AML/CFT Act 2009 scope. NZ Privacy Act 2020 applies to subcontractor data.

## Candidate: Xero API egress cost monitor (sold to other Xero developers)
- Pain is dated, acute and quantified: the 2 Mar 2026 change, and the >$17,000/year bill shock [S].
- Every existing Xero app developer now has a live, recurring, quantifiable cost to manage — durable, not one-off.
- **NO COMPETITOR FOUND** — but the targeted competitor search never ran (budget exhausted), so treat as weak evidence of absence, **not proof**.
- **Platform risk is the highest of any candidate: Xero has an obvious incentive to build this into its own developer dashboard, which kills the product overnight.**
- Distribution is NOT marketplace search — buyers are developers. Would rely on Xero Developer community/Slack + SEO.

## Candidate: FX / difficult-receipt capture (the high-install-poor-rating pattern)
- **Hubdoc — bundled FREE with many Xero plans — carries the lowest rating of the major capture tools at 3.3–3.5★, vs Dext Prepare 4.8★ and AutoEntry 4.7★** [S] invoicedataextraction.com, softwareadvice.com.
- Hubdoc reportedly does not reliably extract foreign-currency amounts and struggles with handwritten, faded thermal and complex-layout receipts; captures header-level data only [S].
- **Why-now: NO EVIDENCE FOUND.** Evergreen gap, not a dated trigger. Weakest "why now".
- Both paid incumbents are rated 4.7–4.8★ — this is a hard field; the opportunity is the *specific* FX/messy-receipt gap, not general OCR.

## Candidate: QuickBooks↔Shopify reconciliation patch
- Intuit forced migration off the legacy connector in 2026. Users report the new app **does not create Sales Receipts**, gives no warning or re-sync ability, cannot map payment types to different bank accounts, and that **"80% of the features of the old app no longer work"** [S — paraphrased from review summaries].
- **Why now: strong and dated.**
- **Competitor landscape UNVERIFIED** — budget ran out before querying Webgility/Synder. Do not treat as a validated 3-competitor category.
- Steady-state likely **exceeds 3 hrs/week** given breakage risk on both APIs.

## Weaker candidates recorded
- **Micro cash-flow forecasting (Xero):** Float (5★, market leader, pricing scales with business size — a stated user complaint) and Fathom (**99,000 companies**, 13+ years) [S]. No dated trigger; low clone resistance.
- **Fixed-asset register for sole traders:** AssetAccountant (multi-jurisdiction incl. NZ), Asset.Guru (**sweet spot 500–20,000 assets** — a clear micro-end gap) [S]. But **Xero's native fixed-asset register is free**, capping willingness to pay. Weakest "why now" of all.

## Could not verify
Xero Core and Plus tier dollar pricing (only Starter $0 and Advanced $895/mo confirmed). Pricing for Retention Track, Payapps, Gojee, Workbench, Float, Fathom, Syft, AssetAccountant, Asset.Guru, Dext, AutoEntry — ratings found, **no dollar figures**. Slack listing fees. Competitors for the QuickBooks-Shopify patch. A2X. **Idea-level signals for Notion, Figma, Monday.com, Airtable and Webflow were never reached** — a material coverage gap against the assignment.
