# 04 — Recommendation (Round 2, 2026-09-03)

*Round 1's recommendation is preserved as `04-recommendation-ROUND1-SUPERSEDED.md`. It was NZ-specific and died with the constraint change.*

---

## The headline

> ## Recommendation: build the **Multi-Jurisdiction Corporate Insolvency API**. It scored **75/100** against your 65 bar — the first candidate in this engagement to clear it, and it clears by ten points.

Round 1's best was 62, then 64 after your clarifications. Nothing cleared. **The difference is not that I searched harder. It is your third constraint change.** Raising the ceiling from 3 to 20 hrs/week made an entire class of business available — the class whose defence is accumulated maintenance work — and that is where every Tier 1 moat in this project turned out to live. Defensibility moved from 4/10 to 7/10, the largest single movement in the whole engagement.

**The product.** A normalised, real-time API and webhook feed of corporate insolvency filings from national gazettes. **Launch France, UK and Spain. Deliberately exclude Germany.**
**The buyer.** Credit-risk teams, trade-credit insurers, factoring and invoice-finance firms, procurement risk teams extending credit into Europe.
**The price.** US$300/month. **Six customers is the entire twelve-month goal.**

---

# The bear case (first, as instructed)

**1. Three competitors got here before you, all within about eighteen months.**
Prometiam, Insolvencies.live and getregdata are all live. You are not first. You are fourth into a space that has been noticed. None publishes pricing and all three are stuck at the same three countries, which is why I still rate it — but "nascent" is a nicer word for "already contested", and by the time you ship there may be six.

**2. Germany — the largest economy in the target region — is legally contested and excluded.**
German data-protection authorities are actively working with the NRW Ministry of Justice to make it *harder* for private providers to extract and republish insolvency data. That is a live regulatory fight, not settled law. Excluding Germany is the right call and it costs you the biggest market in Europe.

**3. Your sources can revoke access unilaterally and you would have no recourse.**
This is the failure mode with the best-documented history in this whole project: Twitter 2023, Reddit 2023, the Reddit `.json` shutdown in 2025–26, Salesforce revoking all Gainsight tokens with no notice in Nov 2025. A government gazette is more stable than a commercial API — but Germany proves the direction of travel is toward restriction, not openness.

**4. Spain requires scraping, and scrapers break.**
There is no official REST API. That is ongoing, unglamorous, brittle work. I have argued this is the moat; it is also genuinely the job, most weeks, forever.

**5. Being wrong is expensive, and you have no professional indemnity cover.**
A customer extends credit because your feed said a company was solvent. If you missed a filing, they lose real money. The €40,000 example that makes this idea compelling is the same example that describes your liability exposure. **Get limitation-of-liability terms drafted before the first customer, and price insurance in.**

**6. The base rates have not changed.**
54% of tracked indie products earn $0. 70% of micro-SaaS earn under US$1,000/month. NZ$3,000 ≈ US$1,800/month is still an above-median, roughly top-quartile outcome, and most attempts fail.

**7. My evidence is thinner than it looks.**
**Page fetching was blocked all session.** Every licence claim above — including France's Licence Ouverte permitting commercial redistribution, and the German dispute — rests on **search-result snippets, not the licence text itself.** For a business whose entire viability turns on redistribution rights, that is not good enough to build on. **Verifying those three licences by reading them is the first task, and it could kill this outright.**

---

# The case for it

**1. It has the only real user-voice evidence in the engagement.**
Round 1 candidates were justified by statutes. This one has a GitHub request open since June 2024, and a founder's May 2026 account of a customer extending **€40,000 to a company that had filed for insolvency eleven days earlier** because their existing API had not caught it. That is a named buyer with a quantified loss.

**2. Three people built this and quit — which is the moat, demonstrated.**
The German scraper exists as a **DEPRECATED** Apify actor and three unmaintained GitHub repos. Three capable developers solved it and abandoned it, because keeping jurisdiction-specific parsers alive is a grind. **That is the answer to "what stops someone cloning this in three weeks" — nothing stops them building it; the evidence says they stop maintaining it.** An AI coding agent shortens the build and does nothing for the twenty-fourth month.

**3. Six customers.**
At US$300/month the entire target is six businesses, roughly one every seven weeks, from a European credit-risk buyer pool numbering in the thousands and enumerable by name and title on LinkedIn and through trade bodies. That is the lowest penetration requirement of anything in either round, and it is a prospecting task, not a marketing one.

**4. It passes the fulfilment test cleanly.**
Customer seven costs nothing extra. One feed serves everyone. Under a 20-hour ceiling the temptation is to drift into an agency; this product structurally cannot.

**5. Incumbents are structurally, not incidentally, slow.**
Large aggregators license bulk feeds rather than running jurisdiction-specific scrapers, so they lag **3 to 21 days**. That is an architectural choice they will not reverse for a small segment — the most durable kind of incumbent weakness.

### Why it beat the other two
- **Beat B (producer licensing, 68)** on the gate. B's entire product depends on NIPR/NAIC data access whose terms I could not verify — a single point of failure that could be fatal on day one. A's equivalent question (licences) is at least answerable from public documents.
- **Beat C (EPR mapping, 65)** on evidence and defensibility. C has **no direct "I would pay for this"** anywhere, and its redistribution licence is unconfirmed for every jurisdiction rather than confirmed for two of three.

---

# When a runner-up would have been the better call

**Choose B (producer licensing) if:** licence verification kills A, *and* NIPR/NAIC turns out to grant reasonable programmatic access. B has a bigger, richer buyer and the strongest proof of spend in the project (**AgentSync contracts averaging over $100k/yr**). Its wound is one phone call away from being resolved or fatal — find out early.

**Choose C (EPR mapping) if:** you want the lowest maintenance load (6–10 hrs/wk) and the cleanest legal story once verified, and you value the **12 August 2026 PPWR** deadline as a live hook. Accept weaker demand evidence.

**Reconsider freight carrier-fraud vetting if:** you can obtain professional indemnity insurance and enforceable limitation-of-liability terms. **It had the best raw demand evidence in the project** — cargo theft ~$725M in 2025, up 60%; FMCSA double-brokering complaints up from ~2,000 to 8,000+ — and I cut it on liability, not on market.

**Build nothing if:** the three licences do not verify and NIPR/NAIC is closed. That is a real possible outcome and it costs you two weeks to discover instead of six months.

---

# What research would change this answer

**Would confirm A (do these first, ~1 week, ~NZ$500):**
1. **Read the actual licences** — Licence Ouverte 2.0 (France), OGL v3.0 (UK), Law 37/2007 (Spain). Confirm commercial redistribution of corporate insolvency notices, and confirm the UK personal-data exclusion does not swallow the corporate use case. **This is the single highest-value hour available and it can kill the project.**
2. **A short opinion from an EU data lawyer** on the German position, and on whether it signals contagion to France or Spain.
3. **Sign up to Prometiam and Insolvencies.live**, learn their real pricing, coverage and latency. You cannot position against competitors you have not used.
4. **Ten conversations** with credit-risk or trade-credit underwriting staff: how do they learn a European counterparty has filed, how late is it, what would timely notice be worth?

**Would kill A:**
- Any of the three licences prohibits commercial redistribution → stop.
- The German restriction turns out to be an EU-wide direction of travel → the whole category is a melting iceberg.
- The three incumbents are already fast, cheap and well covered → you are fourth with no edge.

**Still outstanding from earlier rounds:** Notion, Figma, Monday, Airtable and Webflow were finally examined this round; **trades certification tracking, self-storage, commercial cleaning and equipment hire were never reached.**

---

## What I would actually do

Spend one week reading three licence documents and talking to two competitors' signup flows. If the licences permit redistribution, spend the following week on ten conversations with credit-risk staff. Only then write code — starting with France, because its licence is the clearest, and adding the UK and Spain once the first customer is paying. Price at **US$300/month from the first invoice**; do not launch at US$49 and hope to raise it. Leave Germany alone until the NRW dispute resolves, and say so publicly — being the vendor who is visibly careful about data protection is an asset with exactly this buyer.

And get the liability wording drafted before customer one, not after.
