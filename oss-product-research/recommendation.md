# Recommendation

## The headline you won't like

**Nothing cleared your 7.0 bar.** I am not going to inflate a score to hand you a winner.

| Candidate | Score | Passes your hard gates? |
|---|---|---|
| `chainladder-python` — actuarial reserving | 6.90 | **No** — cannot be sold without sales calls |
| `Arelle` — XBRL/iXBRL filing | 6.80 | Partly — deadline support spikes, wrong timezone |
| `IfcOpenShell` — IFC/IDS model checking | 6.60 | **Yes** |

**The thesis you asked me to test is mostly false in 2026.** I screened 57 repositories
and verified the licence file of 55 of them. The dominant reason for rejection wasn't
licence, or maintainer conflict, or dead repos — it was that **someone had already built
the wrapper**: 18 of the rejections. And mostly not funded startups. Solo operators and
small teams: `simplerouting.io` for VROOM, Data Octopus for IFC/IDS, PaperbackKit for EPUB
accessibility remediation, `zugferd-validator.de` for e-invoicing, Vale Studio for Vale.

The obvious gaps closed in roughly the last 24 months. The plausible reason is the same
one that makes this attractive to you: AI coding agents dropped the cost of building a
wrapper for everyone, not just for you. **Your edge cannot be "I can build it."**

Where a genuine wrapper gap survives, it survives for a reason — the buyer pool is small,
the buyer buys through procurement, or the compute is too expensive. I found no exception.

## What I'd actually do: IfcOpenShell, third on points

I am recommending the candidate ranked **third**, and you should understand why before
accepting it.

Your brief listed some things as scoring axes and others as requirements. Passivity,
self-serve billing, no sales calls, location-agnostic — those read as **gates**, not
axes. Applying them as gates:

- **`chainladder-python` (6.90) is out.** It has the best willingness-to-pay I found
  anywhere — ResQ has 500+ corporate customers, Arius sold to Akur8 which raised $120M.
  But insurers do not buy reserving software self-serve. Reserve estimates go into audited
  statements; buyers want model validation, documented methodology, and a human who will
  answer for it. That is a sales-and-assurance motion. It fails your gate outright, and no
  product decision fixes it.
- **`Arelle` (6.80) is out.** Healthiest repo on the list (a release landed the day before
  I checked) and mandatory-filing demand. But the wrapper isn't missing — it's crowded,
  and **Workiva, a public company, actively funds the same engine you'd build on.** Worse
  for you specifically: filing deadlines compress all support into a few weeks, and you'd
  be answering urgent European filing questions from New Zealand at 3am. That's a direct
  hit on both your passivity and location-agnostic requirements.
- **`IfcOpenShell` (6.60) is in.** Upload a model, get a report — no per-customer setup,
  no human in the loop, no procurement necessary at the individual/small-practice end.
  LGPL-3.0-or-later, verified from `COPYING.LESSER` and the README (the sidebar shows
  GPL-3.0, which would have been the wrong answer — the root `COPYING` file is the GPL
  text that always accompanies an LGPL distribution). Maintainer is donation-funded with
  no commercial tier. Python, well documented, with IDS support already implemented — the
  most agent-buildable codebase of the three. Budget is proven: Solibri from ~$185/user/
  month, BIMcollab Zoom ~€720/year.

It scores lower because its market is contested — and that is precisely the weakness that
two weeks and NZ$200 can test, whereas "insurers won't self-serve" cannot be tested away.

## The single biggest risk

**buildingSMART extends its free validation service to cover recurring IDS checking.**

They already run a [free IFC validator](https://validate.buildingsmart.org/). They own
the IDS standard. They have the brand, the neutrality, and no obligation to make money.
If they ship free automated IDS validation, your product's reason to exist largely
evaporates overnight. You cannot influence this, you cannot out-trust them, and you
cannot outspend them.

Everything else on the risk list is manageable. This one is not, and you should decide now
whether you are willing to build on top of it.

Second place, worth naming: your differentiation is **workflow, not technology**. Recurring
checks, revision history, BCF issues into existing tools — Data Octopus or BIMcollab could
add all of it. You are making a timing bet that they won't bother with the small end of
the market fast enough. That is not a moat.

## Tomorrow morning

**Do not open an editor.** Write one message and send it ten times.

Post in [OSArch](https://community.osarch.org/) and message ten BIM Managers at 20–200
person architecture, MEP or contracting firms on LinkedIn. Ask exactly one thing:

> "When you receive a model from a subconsultant, how do you currently check it has the
> properties your BIM Execution Plan requires — and what happened the last time one
> didn't?"

Do not describe a product. Do not mention IDS unless they do. You are testing one thing:
whether this is a **recurring** problem they already work around, or a one-off annoyance
that free validators already handle well enough.

Then work `build-plan-ifcopenshell.md` Phase 0. The green light needs all four:

1. ≥ 6 of 10 describe it as recurring **and** currently manual or unhandled
2. ≥ 3 of 10 have budget authority or a clear path at $199/month
3. ≥ 40 waitlist signups in 4 weeks, organic only
4. ≥ 500 combined monthly search volume across the 10 target queries

**Write those numbers down now, before you have data.** The failure mode for a solo
operator with an AI agent is that building is cheap enough to start before validating, and
sunk cost does the rest.

## One honest caveat about this research

The demand axis carries 25% weight, and I could not verify it for any candidate. GitHub's
search API rate-limited me (HTTP 429, one-hour lockout) and the web-search tool hit a
session quota mid-run. I found no dated, attributable "I would pay for this" evidence for
any of the three — so every one of them scores 5–6 on demand, and that alone is why none
reached 7.0.

**If IfcOpenShell's demand is genuinely an 8, it scores 7.35 and clears your bar.** Phase 0
is not ceremony; it is the missing 25% of this analysis. I have told you what I verified,
what I inferred, and what I couldn't establish, and I would rather hand you three honest
6.x candidates than one dressed-up 7.5.

---

**Files:** `longlist.md` (57 candidates, 55 licences verified) · `shortlist.md` (9 scored)
· `deep-dive-chainladder.md` · `deep-dive-arelle.md` · `deep-dive-ifcopenshell.md` ·
`build-plan-ifcopenshell.md`
