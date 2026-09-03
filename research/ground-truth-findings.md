# Ground Truth: What Actually Earns Money, and What Kills It (2026-09-03)

[S] = web-search summary + URL; [SELF-REPORTED] = founder-claimed, unverifiable; [I] = inference.

## BASE RATES — the most important numbers in this whole run
- **54% of tracked Indie Hackers products earn $0.** [S] (consistent 2023–2024)
- **70% of micro-SaaS earn under $1,000 MRR.** Median across ~1,000 tracked products ≈ **$500/mo**. [S] https://freemius.com/blog/state-of-micro-saas-2025/ , https://saasranger.com/blog/micro-saas-revenue-reality-what-1000-founders-actually-earn/
- Only ~5% cross ~$8,333/mo. Median for products that reach profitability at all ≈ $4,200 MRR. [S]
- **US$3,000 MRR is therefore a top-10–20% outcome among products that launch and are actively worked — not a median.**

## CHURN — mechanically hostile at this price point
| Segment | Monthly churn | Source |
|---|---|---|
| B2B SaaS average 2025 | 3.5% | [S] vitally.io |
| SMB-focused SaaS | 3–7% (31–58%/yr) | [S] venasolutions.com |
| **Customers paying under $50/mo** | **6–8.6% monthly** | [S] optif.ai |
| "Good SaaS" benchmark | <1%/mo | [S] — **does not apply at this price point** |

> At sub-$50/mo pricing, plan for **6–8% monthly churn**. Acquisition must outrun the leak just to hold flat. A one-month spike to $3k is not a $3k business.

## WHAT CHANNEL ACTUALLY GOT THE FIRST CUSTOMERS
- MicroConf State of Independent SaaS: **50% of founders rely primarily on communities and referrals**; **47%** name integrations/partnerships/communities/forums as their most dependable growth source — a shift away from paid ads as CAC rose through 2025. [S] https://microconf.com/founders/0-10k-arr
- Consistent tactical pattern: **pick one channel and stay in it ~90 days** before adding a second. [S]
- Cold email at this scale: one reported campaign converted **~1 client per 50 emails** (79.6% open, 1.85% close). [SELF-REPORTED]
- **"Zero audience" success stories usually aren't.** RemoteOK's founder already had Nomad List. The cleanest genuinely-cold-start example found — JobBoardSearch.com — made **~$40k total revenue over ~14 months** on <$100/mo costs. That is the realistic analog for this operator.

## PLATFORM RUG-PULLS — the best-dated failure mode
| Event | Date | Casualty |
|---|---|---|
| Twitter/X free API cut | Feb 2023 | Tweetbot, Twitterrific, Talon [S] |
| Reddit API pricing | Jun 2023 | **Apollo** (would have cost $20M/yr), Sync, ReddPlanet [S] |
| Reddit `.json` + Pushshift shutdown | 2025–26 | "The entire ecosystem of Reddit scrapers and data pipelines" [S] |
| **Salesforce revoked all Gainsight app tokens and pulled them from AppExchange** | **Nov 2025** | Gainsight-published apps — a marketplace unilaterally suspending third-party apps **with no notice period** [S] helpnetsecurity.com |
| IDX+ (real estate) | multi-year | Founder made $60k in sales, **spent it all on maintenance** as the host changed HTML [S] |
| Shopify stricter compliance webhooks/GDPR | from Aug 2025 | Rising cost-of-staying-listed for solo apps [S] |

## FEATURE ABSORPTION BY INCUMBENTS
- OpenAI's native PDF chat reportedly obsoleted ChatPDF, PDF.ai, AskYourPDF. [S]
- Jasper's wrapper business "collapsed" as frontier models matched it. [S]
- Dedicated graveyard trackers now exist: **"Killed by AI" (111 tracked shutdowns)**, "Killed by OpenAI", "Killed by LLM". [S] https://mixtpatrik.github.io/killedbyai/

## HAS THE AI CODING BOOM CHANGED THE PICTURE? (the brief's §4 tension)
- **App Store submissions up ~60% YoY in Q1 2026, +104% in April alone** [S — directionally sourced, not pinned to one URL].
- **Shopify: ~600 apps tagged "AI".** **Chrome Web Store: 5,191 AI-tagged extensions in the "work" category alone.** [S]
- Lovable reached **$200M ARR by late 2025** — the tooling to spin up competitors fast is itself a large funded business. [S]
- **NO EVIDENCE FOUND** of a specific named "cloned in a weekend by an AI agent" incident. Saturation evidence is real and dated; the instant-clone narrative remains plausible but unevidenced.

## VALUATION (for the eventual exit question)
- Acquire.com median **3.9x SDE**, steady through 2024–25; at the $1–5k MRR tier closer to **2–3x annual SDE**. [S] blog.acquire.com Jan 2026
- Flippa: bootstrapped SaaS under $1M ARR averages **2.85x annual profit**; revenue multiples climb from **1.4x under $50k revenue** to 3.5x above $1M. Buyers favour **churn below 6%**. [S] flippa.com/blog/saas-multiples/

## VERDICT ON THE TARGET
**Budget 12–18 months to first reach US$3,000 MRR, with real probability mass on "never gets there".** Twelve months is the optimistic case within a sample that already skews winners. Survivorship bias is severe: founders who tried for a year and got nowhere do not write case studies.

---

# THE EIGHT KILL QUESTIONS (used directly in Stage 3)

1. **Distribution-first.** Can you name the ONE channel you'll work for 90 straight days, and why it works without an existing following? "I'll figure out marketing after I build it" → **kill**.
2. **Platform risk.** Does it depend on an API/marketplace/feed you don't control? Could access be revoked or re-priced with under 90 days' notice (Twitter, Reddit, Gainsight all were)? Can't say "the business survives that" in one sentence → **kill or demote to a side-feature**.
3. **Feature absorption.** If the dominant platform shipped this natively next quarter, would the product still have a reason to exist? If the value-add is "a nicer UI on a frontier-model API call" → **kill**.
4. **Churn math.** At sub-$50/mo assume **6–8.6% monthly** churn. Can you outrun that leak on 3 hrs/week? If outrunning it needs a content treadmill or manual outreach forever → **kill**.
5. **Support load.** Can you handle support in 3 hrs/week at 200+ customers? Burnout in post-mortems is a *support and isolation* problem, not only a growth problem → **redesign for self-serve or kill**.
6. **Saturation.** Search the target marketplace today. Given the 2025–26 submission surge, if 5+ close competitors exist and you have no distribution edge → **kill**.
7. **Standing.** Does the idea target a niche where the operator has credible pre-existing standing? If not, expect the JobBoardSearch trajectory (~$40k over 14 months), not an 8-month story.
8. **Value pricing.** Is the price anchored to a dollar amount of value returned, or just to competitors' prices? If the latter → **re-price before building further**.

## Could not verify
Category-specific sale multiples; a named "cloned overnight" case study; a named "market too small" post-mortem; LinkedIn/TikTok/Meta 2025–26 API changes; independent verification of ANY self-reported MRR figure. Search budget (200/200) exhausted mid-research; five planned queries never ran.
