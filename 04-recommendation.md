# 04 — Recommendation

**Run date 2026-09-03.**

---

## The headline, stated plainly

> ## Nothing cleared your 65-point bar.
> The best candidate scored **62**. I am not going to nudge it to 66 so this document has a happier ending.

Per §7 of your brief, this is a legitimate and valuable result, and I am reporting it as the primary finding rather than burying it. What follows is the best of a weak field, its flaws named, and — most importantly — **the specific, cheap research that would move it above or below the bar.**

**Conditional recommendation: Candidate A — the NZ Construction Retention-Money Trust Compliance Ledger — subject to a hard Phase 0 gate that costs you about NZ$0 and roughly 12 hours.**

If Phase 0 fails, the correct action is to stop, and the plan in `05-build-plan.md` is written to make stopping easy.

---

# The bear case (written first, as instructed)

**1. The demand is inferred from a statute, not observed in a human being.**
This is the most serious flaw and it maps exactly onto your own definition of "validated". I verified that the law exists, that it is binding, and that penalties reach $200,000 per offence plus $50,000 per director. I did **not** find a single NZ contractor saying this is painful, a single review complaining about existing tools, or a single forum thread asking for a better option. Every attempt to retrieve primary forum content in this run failed. A legal obligation is a *reason* someone might buy; it is not evidence that they will.

**2. Nobody knows how big this market is — including me.**
There is no verified count of NZ businesses that actually hold retention money. Most of NZ's ~5.36 million people are irrelevant here; most construction firms are sole traders who *receive* retentions rather than hold them. The population with the obligation could plausibly be 400 or 4,000, and those two numbers are the difference between "no business" and "viable business". I could not resolve it.

**3. The moat is thin and I am not going to dress it up.**
Trust-ledger arithmetic and a quarterly report format are not hard. An AI coding agent builds this in weeks — which means anyone else's AI coding agent also builds it in weeks. The honest defence is correctness, accumulated reviews, and NZ-specific regulatory attention. The *real* protection is that the market is probably too small for a serious competitor to bother with — which is the same fact as "this business likely caps out at US$3–10k/month". Those are not two findings; they are one finding wearing two hats.

**4. It sits exactly on your 3 hrs/week ceiling, not comfortably under it.**
My estimate is ~3.0 hrs/week at steady state. Estimates like that are usually optimistic.

**5. Five competitors already exist in the adjacent space, and I could not price any of them.**
Retention Track, Payapps, Gojee, Workbench and RemitClear all touch retentions. I could not verify a single price for any of them, which means the pricing strategy in `03-deep-dives.md` rests on value logic rather than market evidence.

**6. The base rates are brutal and apply to you.**
**54% of tracked indie products earn $0. 70% of micro-SaaS earn under US$1,000/month. The median is about US$500/month.** US$3,000/month is a top-10–20% outcome among products that actually launch and are actively worked. The cleanest genuinely-zero-audience comparable found made roughly **US$40,000 in total revenue over 14 months** — not US$3,000/month.

**7. Your 12-month target is probably 12–18 months, and possibly never.**
That is what the evidence supports. I would rather say it now.

**8. My research was materially degraded and you should discount accordingly.**
Page fetching was blocked entirely, and the session's search budget was exhausted. **No claim in any of these documents was verified by opening the source page.** Several planned searches never ran. Notion, Figma, Monday.com, Airtable and Webflow were never examined at all. This is not a complete search of the space and should not be treated as one.

---

# The case for it anyway

Against that, four things are true, and they are the reasons this is still the pick.

**1. The forcing function is real, verifiable, severe, and recurring.**
Retention money must sit in a separate trust account. Quarterly reports to every subcontractor are mandatory. Penalties reach $200,000 per offence and $50,000 per director. Unlike a checklist that a business does once, **the quarterly reporting obligation recurs forever** — which is the subscription shape almost every other candidate lacked. This is the only survivor whose legal obligation and revenue model point the same way.

**2. It is the operator's home market, and that advantage is real rather than sentimental.**
Right timezone, so async support is genuinely async rather than a 12-hour lag. A credible local vendor rather than an anonymous offshore one. Reachable trade associations. No cross-border VAT/GST exposure — recall that the UK has a **nil VAT threshold** for non-established sellers and the EU charges from the first euro, both of which this sidesteps entirely by selling NZ-domestic B2B. Every other candidate required selling into a market where the operator is a stranger at an awkward hour.

**3. The incumbents are visibly weak, not merely present.**
**Retention Track — the closest-positioned competitor — had zero reviews.** None of the five existing tools is a pure compliance product; they are job-management platforms with retention bolted on. That is a genuine underserved segment inside an occupied market, which is exactly the definition of "low competition" your brief demanded — as opposed to the empty-market red flag it warned against.

**4. It survives the kill questions better than anything else found.**
It is not being absorbed by an incumbent's free tier (unlike AU Payday Super). Its buyer is not also its cloner (unlike the Xero egress monitor). It is not gated on a deadline that expires before launch (unlike Companies House). It is not one-off (unlike the LTMP builder). It is not consumer-priced (unlike the landlord dashboard).

### Why it beat the other two
- **Beat Candidate B (AU Payday Super, 56)** on platform risk and passivity. B's feature absorption by Xero and MYOB is not a risk — it is already happening, and the buyer already owns the software doing the absorbing. B also breaches the hours ceiling at 3–4 hrs/week.
- **Beat Candidate C (Xero egress monitor, 55)** on defensibility and platform risk. C has the best pain evidence in the entire run and the worst structural position: Xero can delete the product by shipping one dashboard feature, and the customer is a developer who can build it themselves in a weekend.

---

# When a runner-up would have been the better call

**Choose B (AU Payday Super) instead if:** Phase 0 shows the NZ retention pool is under ~800 businesses. Australia's market is roughly 5× larger, and a smaller share of a bigger market beats a large share of a market that does not exist. Accept in exchange that you are racing Xero and MYOB to a feature they are already building, and that the hours ceiling will break.

**Choose C (Xero egress monitor) instead if:** you are willing to trade durability for speed, and you want revenue inside 60 days rather than 5 months. It has the fastest time-to-first-customer, the lowest support load, and a genuinely quantified pain ($17,000/year). Treat it explicitly as a **12–18 month cash play that Xero will probably kill**, not as a business to hold. Given the operator profile — no audience, limited hours, wants durability — I do not recommend this, but it is the rational pick for someone optimising for speed over longevity.

**Choose none of them if:** Phase 0 fails on Candidate A and you are unwilling to accept B's or C's named wounds. That is a respectable outcome. See below.

---

# What additional research would change this answer

Cheap, specific, and high-leverage — roughly 12 hours and almost no money.

### Would move Candidate A *above* the bar
1. **Resolve the denominator.** Find the number of NZ businesses that hold retention money. Sources: MBIE construction sector statistics, Stats NZ business demography by ANZSIC construction subclass, Registered Master Builders and Specialist Trade Contractors Federation membership counts. **A pool above ~1,500 moves demand evidence from 11 to ~15 and the total to ~66.**
2. **Get user voice.** Ten conversations with NZ head contractors or their bookkeepers about how they currently handle the trust ledger and quarterly reports. If even three describe it as painful and current tools as inadequate, demand evidence moves from 11 to 15+.
3. **Price the incumbents.** Retention Track, Payapps, Gojee. This alone converts the pricing strategy from logic to evidence.
4. **Confirm the Act's commencement and current obligations** with a NZ construction lawyer or MBIE directly. Removes the regulatory-risk deduction.

### Would move it *below* the bar, and should be checked first
1. **The pool is under ~800 businesses** → not a business. Stop.
2. **Xero or a major NZ construction platform ships retention-trust compliance natively** → kill-question 3 fires. Check the roadmaps.
3. **The five incumbents already do this well and cheaply** → the "no pure compliance tool" premise collapses.

### Would change the whole picture
- **Re-run this research with page fetching enabled and a raised search budget.** Notion, Figma, Monday.com, Airtable, Webflow, trades certification trackers, self-storage, commercial cleaning and equipment hire were never examined. **The single highest-value action available is not building anything — it is finishing the search.**
- **Confirm whether the target is US$3,000 or NZ$3,000.** NZ$3,000/month ≈ US$1,800/month, which needs roughly 20 customers at NZ$149/month instead of 34. That change alone would likely push Candidate A above the bar.

---

## What I would actually do, if you want it in one paragraph

Spend the next two weeks on Phase 0 and nothing else. Do not write code. Find out how many NZ businesses hold retention money and talk to ten of them. That costs you almost nothing and resolves the single unknown that decides whether this is a business or a hobby. If the number is healthy and three of ten people describe real pain, build it — and price it at NZ$149/month, not NZ$79, because the arithmetic in `03-deep-dives.md` shows that one decision halves the hardest part of the job. If the number is small or nobody cares, stop, and go finish the research that this session's blocked network and exhausted search budget prevented me from completing.
