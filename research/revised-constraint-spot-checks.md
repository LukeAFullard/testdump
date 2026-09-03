# Spot Checks Under the Revised Constraints (2026-09-03)

My own searches, run after the constraint change (forget NZ / online-only / 20 hrs per week). [S] = search-result summary with URL; [I] = inference.

## Kills CONFIRMED — these were previously "unverified competition", now verified

**QuickBooks↔Shopify reconciliation patch — DEAD, competition verified crowded.**
The Stage 3 kill rested partly on an unverified competitor landscape. It is now verified and it is busy:
- **A2X from $29/mo** [S] apps.shopify.com/a2x
- **Synder from $65/mo** [S] apps.shopify.com/synder
- **Webgility $109–139/mo** — QBO/Xero from $129/mo annual (800 orders, 2 channels); QuickBooks Desktop from $109/mo (500 orders, 1 channel) [S] erpresearch.com
- **MyWorks** — the only major option with two-way inventory sync [S] weintegrate.co
The maintenance objection dissolves at 20 hrs/week, but the competition objection does not. **Stays dead.**

**Sales-tax / VAT rate APIs — DEAD on saturation.**
Named incumbents: Zamp, Avalara AvaTax, Vertex, TaxJar, Sovos, Stripe Tax, Anrok [S] zamp.com, taxcloud.com. One minor data-currency weakness surfaced (a VAT API refreshing EU rows live but **non-EU rows only quarterly** [S] unirateapi.com) but the category is contested by well-funded vendors. Not a solo entry.

## HS-code / import duty — DOWNGRADED from "promising lead" to "contested"
An earlier agent flagged this as a possible self-serve gap below Avalara. My own checks say the gap is largely taken:
- **Zonos: $2 + 10% of duties and taxes per order** — published, self-serve-shaped [S] gingercontrol.com
- **GingerControl: request-based tiers, 1,000 → 100,000+ requests/day**, and it publishes an article explicitly targeting **"7 Trade Compliance Tools for SMB Importers Under $500K Annual Duties"** [S] gingercontrol.com — that is precisely the underserved segment, and a competitor is already marketing into it
- **Avalara** remains sales-quote-only with a **1.1/5 BBB rating from 31 reviews, 53 complaints closed in 12 months**, and setup criticised as taking "weeks to months" [S] zamp.com — the incumbent weakness is real, but two vendors are already exploiting it
**Verdict: the incumbent is genuinely bad, and that is exactly why the gap already has occupants.**

## Denied-party / sanctions screening — same shape, same outcome
- **Descartes: ~$3,000 per user per year for basic, scaling past $100,000** for enterprise scope [S] tradecompliancesoftware.org — a textbook "enterprise vendor ignores small buyers" setup
- But the low end is already served: **ComplyAdvantage from ~$99/mo**, **sanctions.io priced per screening with a public calculator**, and **Shipping Solutions** explicitly aimed at small and mid-market exporters [S]
Sanctions lists change constantly, so the maintenance-moat logic applies — but again, occupied.

---

## ⚠️ The meta-finding: the "underserved segment below an enterprise incumbent" play is itself now crowded

Four independent checks today — tariff classification, sanctions screening, sales-tax APIs, e-commerce accounting sync — followed an identical pattern:

1. A genuine enterprise incumbent with opaque, sales-quote-only pricing and poor reviews. ✅ The gap is real.
2. **Two to four self-serve entrants already sitting in that gap at US$29–199/month.** ❌ The gap is filled.

This is the AI-coding-boom effect showing up in the data rather than in argument. It corroborates the Stage-1 ground-truth finding (**App Store submissions up ~60% YoY in Q1 2026; Shopify at 18,062 apps with +52% YoY new-app growth; 5,191 AI-tagged Chrome extensions in one category**) and it sharpens the brief's §4 tension considerably:

> **"An underserved segment inside a crowded market" was the brief's own definition of acceptable low competition. That strategy is now itself crowded, because it is the obvious move and AI tooling made it cheap to execute.**

**Implication for candidate selection.** Simply finding a bad expensive incumbent is no longer sufficient evidence of opportunity — by 2026 it is close to zero evidence, because everyone can see the same signal and act on it within weeks. What still discriminates:
- Data or integration work that **compounds over years** and cannot be caught up by a fast follower (the maintenance moat of §6.1 in `00-brief-review.md`).
- Buyers who are **genuinely hard to reach** — no marketplace, no search intent, only a trade directory and a compliant email.
- Domains where **being wrong is expensive**, so trust and track record matter more than features.
- **Regulatory or licensing gates** that take real time to pass.

Anything whose only defence is "the incumbent is expensive and bad" should now be assumed to have two competitors you have not found yet. **Check before believing a gap is open.**

---

## Spot checks 5 and 6 — the pattern holds

**Security questionnaire automation for small SaaS vendors — DEAD on saturation.**
Fits the new constraints well on paper: expensive recurring pain, enumerable buyers (any B2B SaaS), global and online. But the field is full: **Wolfia, Vanta, Conveyor, SafeBase, SecurityPal AI, Delve, Skypher, AutoRFP.ai** [S] bitsight.com, skypher.co, wolfia.com. **AutoRFP.ai publishes from $899/month**; **SafeBase offers a free tier** [S] autorfp.ai. Squeezed from both ends.

**Developer tools / package-registry distribution — useful mechanics, no clear opening.**
- **The VS Code Marketplace has NO built-in payment support** — sellers must bolt on an external processor (Dodo Payments, Gumroad, Stripe) [S] superframeworks.com. A marketplace-mechanics fact worth knowing before choosing it as a channel.
- GitHub Marketplace reportedly contributes ~$200M annually to GitHub's revenue [S] fueler.io.
- A widely-repeated claim that "the median solo developer with a successful micro SaaS earns $3K–$10K MRR within 12–18 months" [S] bigideasdb.com — **note the word "successful" is doing all the work here, and the source is a content-marketing site.** This is survivorship bias restated as a statistic. It does **not** contradict the Freemius base rate (70% under US$1,000/mo, median ~US$500).

## Running tally: six spot checks, six occupied gaps

| # | Gap checked | Enterprise incumbent | Already occupied by |
|---|---|---|---|
| 1 | Tariff / HS-code classification | Avalara (quote-only, **1.1/5 BBB**) | Zonos, GingerControl, Easyship |
| 2 | Denied-party / sanctions screening | Descartes (**$3k–$100k+/yr**) | ComplyAdvantage (~$99/mo), sanctions.io, Shipping Solutions |
| 3 | QuickBooks↔Shopify sync | — | A2X $29, Synder $65, Webgility $109–139, MyWorks |
| 4 | Sales-tax / VAT APIs | Vertex, Avalara | Zamp, TaxJar, Stripe Tax, Anrok, Sovos |
| 5 | Security questionnaire automation | — | Wolfia, Conveyor, SafeBase, Skypher, AutoRFP.ai $899 |
| 6 | SaaS sunset tracking (meta-idea) | — | SunsetProof already runs a 2025–2027 tracker |

**Six for six is not bad luck. It is a structural fact about 2026** and it is the strongest empirical support in this whole project for the brief's §4 tension. The corollary for candidate selection stands: **treat "the incumbent is expensive and badly reviewed" as close to zero evidence**, and require a defence that is *time-accumulated* rather than *insight-based*.
