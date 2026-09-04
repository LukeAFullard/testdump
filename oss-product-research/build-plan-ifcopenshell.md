# Build plan — IFC/IDS model compliance checking on `ifcopenshell`

Written to be executed by an AI coding agent. Each phase is independently testable by you
without reading code.

**Read this first:** this candidate scored **6.60**, below your 7.0 bar. The plan is
deliberately front-loaded with a kill gate. Phase 0 costs under NZ$200 and about two
weeks, and it is designed to end the project if the evidence isn't there. Do not skip it,
and do not soften the threshold after you see the result.

---

## Stack decisions (fixed once, here)

| Choice | Decision | Why |
|---|---|---|
| Language | **Python 3.12** | Not negotiable — `ifcopenshell` is a Python library. Everything else follows from this. |
| Web framework | **Django 5** | Auth, admin, ORM, migrations and sessions ship in the box, which deletes most of Phase 2. Enormous training corpus, so agents write it well. |
| Frontend | **HTMX + Tailwind + Django templates** | Server-rendered. No SPA build step, no API-versioning problem, no second language. An agent producing HTML fragments is far more reliable than one producing React state logic. |
| Queue | **Redis + RQ** | IFC parsing must not run in a request. RQ is markedly simpler than Celery and sufficient. |
| Database | **Neon (managed Postgres)** | Managed, scale-to-zero, cheap at this size. Never self-manage Postgres. |
| Object storage | **Cloudflare R2** | Zero egress fees. Materially important: IFC files are 100MB–2GB and you will move them repeatedly. |
| Hosting | **Fly.io** | Web + worker processes, scale-to-zero workers, regions near your users. Alternative: Render. |
| Billing | **Paddle** (merchant of record) | Handles global sales tax/VAT from a New Zealand entity. This is the single most important non-technical choice for your constraints. Lemon Squeezy is the fallback. |
| Auth | **django-allauth** | Email + Google. Boring and complete. |
| Email | **Resend** | Transactional only. |
| Errors | **Sentry** | Free tier is enough at this scale. |
| Uptime | **Healthchecks.io** (worker heartbeats) + **Better Stack** (HTTP) | Phase 4. |
| Analytics | **Plausible** | Simple, no cookie banner. |

**Licence guardrail, applied from Phase 1 and enforced forever:** depend only on
LGPL-licensed IfcOpenShell modules. **Never** import or vendor `blenderbim`/Bonsai — it is
GPL-3.0 and would force you to open-source the product. Pin `ifcopenshell` to an exact
version; it is pre-1.0 and breaks between minor releases.

---

## Phase 0 — Validate before building

**Objective.** Establish whether BIM Managers will pay for *recurring, tracked* model
checking, given that one-off validation is already free.

**In scope:** landing page, waitlist, 10 ICP conversations, keyword volume check,
competitor teardown.
**Out of scope:** any product code whatsoever. No repo, no infrastructure.

**Technical tasks**
1. Single static landing page (Astro or plain HTML on Cloudflare Pages). Headline states
   the recurring-checking wedge explicitly, not "IFC validation".
2. Waitlist email capture → a Google Sheet or Buttondown. Ask one qualifying question:
   *"What do you use today to check incoming models?"*
3. A pricing section showing the three real tiers ($49 / $199 / $499) with a "Notify me"
   button per tier. Record which tier is clicked — stated price preference is weak
   evidence, but tier clicks are cheap to collect.
4. Keyword volume check on the 10 long-tail queries in the deep dive, using Ahrefs or
   Semrush free tier, or Google Keyword Planner.
5. Competitor teardown: sign up for [Data Octopus](https://dataoctopus.net/) and use its
   3 free checks. Run the [buildingSMART validator](https://validate.buildingsmart.org/)
   and [ifc-ids.com](https://ifc-ids.com/) on a real IFC. Write down precisely what each
   does *not* do.

**Non-technical tasks (the actual work)**
6. Ten conversations with BIM Managers at 20–200 person firms. Recruit from
   [OSArch](https://community.osarch.org/), buildingSMART chapter events, and LinkedIn.
   Ask what they did the last time they received a bad model — never pitch.
7. Post the free IDS-authoring idea on OSArch and measure genuine reaction.

**Acceptance criteria** — you can verify all of these yourself:
- [ ] Landing page live, 10+ conversations completed and written up
- [ ] Keyword volumes recorded for all 10 queries
- [ ] A written page describing exactly what the three free/cheap competitors don't do

**Green-light threshold for Phase 1 — all four must hold:**
1. **≥ 6 of 10** interviewees describe checking incoming models as a *recurring* problem,
   not a one-off, **and** say they currently do it manually or not at all.
2. **≥ 3 of 10** state they have budget authority or a clear path to it at $199/month.
3. **≥ 40 waitlist signups** within 4 weeks from organic posting only (no ads).
4. Combined monthly search volume across the 10 queries **≥ 500**.

**Kill criteria — stop the project if any of these:**
- Fewer than 4 of 10 see it as recurring → the wedge doesn't exist and free tools win.
- Interviewees say "we already have Solibri" more than 5 times → your segment is smaller
  than assumed.
- buildingSMART announces recurring/automated IDS validation → the strategic risk landed
  before you started.
- Waitlist under 15 after 4 weeks → you have no distribution channel and no plan B.

**Time:** 2 agent-sessions (landing page, teardown writeup) + your own interview time.
**Calendar: 14–21 days**, interview scheduling being the constraint.
**Cost:** domain ~NZ$25/yr, Cloudflare Pages free, Buttondown free tier, keyword tool
NZ$0–150 for one month. **Total under NZ$200.**

---

## Phase 1 — Thin vertical slice

**Objective.** Prove end to end that a real IFC file plus a real IDS specification
produces a correct, useful report.

**In scope:** file upload, background parse, IDS execution, HTML report.
**Explicitly out:** authentication, billing, multi-tenancy, styling beyond legibility,
IDS authoring UI, BCF, 3D viewer.

**Technical tasks**
1. Django project; single app `checks`. Models: `Project`, `ModelUpload`, `CheckRun`,
   `RuleResult`.
2. Upload endpoint accepting `.ifc` up to 500MB, streaming directly to R2 (never through
   application memory).
3. RQ worker task: download from R2 → `ifcopenshell.open()` → run `ifcopenshell.ids`
   against a supplied `.ids` file → persist per-rule pass/fail with the failing element
   GlobalIds.
4. Report view: rules down the page, pass/fail, failing element counts, expandable element
   lists with `GlobalId`, `Name`, `IfcType`.
5. Handle the failure modes explicitly and visibly: corrupt IFC, unsupported schema
   version (IFC2X3 vs IFC4 vs IFC4X3), out-of-memory, timeout.
6. **Assemble a regression corpus now** — 10–15 real IFC files spanning schema versions
   and sizes, from [buildingSMART sample files](https://technical.buildingsmart.org/) and
   OSArch. Every future `ifcopenshell` upgrade re-runs against this corpus.
7. Pin `ifcopenshell==0.8.5` exactly. Add a CI check that fails the build if any
   GPL-licensed IfcOpenShell module appears in the dependency tree.

**Acceptance criteria** — verifiable by you, without reading code:
- [ ] Upload a real 200MB+ IFC via browser; a report appears within 5 minutes
- [ ] The report correctly identifies walls missing a fire-rating property, checked by
      hand against the model in a free viewer
- [ ] A deliberately corrupted IFC produces a clear error, not a crash or a hang
- [ ] All 15 corpus files process without unhandled exceptions
- [ ] IFC2X3 and IFC4 files both work

**Time:** 6–8 agent-sessions. **Calendar: 10–14 days.**
**Cost:** Fly.io ~US$15/mo, Neon free tier, R2 ~US$2/mo. **~US$20/month.**

**Kill criteria:** if `ifcopenshell` cannot reliably process real-world files at
acceptable memory/time — specifically if typical 500MB models need more than 8GB RAM or
10 minutes — unit economics break and the product is not viable at $49–199/month. Stop,
or reprice around large models before continuing.

---

## Phase 2 — Make it a product

**Objective.** A stranger can sign up, pay, and use it without you being involved.

**In scope:** auth, tenancy, billing, onboarding, quotas, error handling.
**Out:** IDS authoring UI, BCF, trends, integrations.

**Technical tasks**
1. `django-allauth`: email + Google. Email verification on.
2. `Organisation` model; every `Project` belongs to one; enforce tenant scoping in a
   single queryset mixin used everywhere. Write tests that assert cross-tenant access
   returns 404.
3. Paddle integration: three plans, checkout, webhook handling for
   created/updated/cancelled/payment-failed. Store subscription state locally; never call
   Paddle on the hot path.
4. Quota enforcement by tier: projects, checks/month, max file size. Return a clear
   upgrade prompt, not an error.
5. Onboarding: on first login, offer a sample IFC + sample IDS so the user reaches a
   report in under 60 seconds without owning a model.
6. Transactional email via Resend: verification, check-complete, payment-failed.
7. Sentry on web and worker. Structured logging with a run ID.

**Acceptance criteria:**
- [ ] From an incognito window: sign up, pay with a Paddle test card, run a check, receive
      the completion email — with zero manual involvement from you
- [ ] Cancelling in Paddle downgrades the account within one minute
- [ ] Exceeding quota shows an upgrade prompt, not a stack trace
- [ ] A second account cannot see the first account's projects (verify by trying)
- [ ] Paddle invoice shows correct GST/VAT treatment for a non-NZ buyer

**Time:** 8–10 agent-sessions. **Calendar: 14–21 days.**
**Cost:** ~US$40/month infra; Paddle takes 5% + 50c per transaction.

**Kill criteria:** if fewer than 3 of the Phase 0 waitlist convert to paid within 30 days
of launch, the willingness-to-pay assumption is wrong. Stop before Phase 3.

---

## Phase 3 — Make it good

**Objective.** Deliver the workflow wedge — the thing free validators structurally cannot
do.

**In scope:** IDS authoring UI, BCF export, revision-over-revision trends.
**Out:** 3D viewer, clash detection, Revit plugin.

These three tasks are **independent and can be built in any order or in parallel.**

1. **IDS authoring UI** — the highest-value item and the strongest lead magnet. Plain
   language rule builder ("All IfcWall must have property FireRating in Pset_WallCommon")
   exporting standards-compliant IDS XML. Validate output against the buildingSMART IDS
   schema. Include a rule template library for common BIM Execution Plan requirements.
2. **BCF export** — issues flow into BIMcollab, Solibri and Revit. Use the LGPL `bcf`
   module from IfcOpenShell (verified LGPL-3.0 in the README module table). This is what
   makes the product fit an existing workflow rather than replacing it.
3. **Revision trends** — upload revision N+1 of the same model; show which rules improved,
   regressed or stayed broken. **This is the retention mechanic and the actual moat
   against one-off validators.** Build it even though it looks least urgent.

**Acceptance criteria:**
- [ ] Author a rule in the UI without hand-writing XML; the exported `.ids` validates
      against the buildingSMART schema and runs in another IDS tool
- [ ] Export BCF; open it successfully in BIMcollab Zoom or Solibri
- [ ] Upload two revisions; the trend view correctly shows improvement and regression

**Time:** 10–14 agent-sessions. **Calendar: 21–30 days.**
**Cost:** ~US$60–120/month as usage grows.

**Kill criteria:** if month-2 retention is under 40% with trends and BCF shipped, the
workflow wedge is false — users only ever wanted one-off validation, which is free
elsewhere. Stop and reconsider.

---

## Phase 4 — Make it passive

**Objective.** It runs, and mostly fixes itself, without you.

**Technical tasks**
1. **Self-healing:** automatic retry with backoff on transient worker failures; dead-letter
   queue; per-job memory ceilings so one enormous model cannot take down the worker;
   hard timeouts with a user-visible "model too large for your tier" message.
2. **Monitoring/alerting:** Healthchecks.io heartbeat from the worker; Better Stack on the
   web endpoint; Sentry alerts routed to email. Alert only on things you would act on —
   alert fatigue is how solo operators end up ignoring real outages.
3. **Support deflection:** docs site (Django templates or Astro) covering the 15 questions
   from Phase 0/2; an in-app error catalogue where every error message links to its own
   docs page.
4. **Status page** (Better Stack free tier).
5. **Automated dunning** via Paddle for failed payments; no manual chasing.
6. **Weekly digest email to yourself:** signups, checks run, failures, MRR. One email,
   not a dashboard you have to remember to open.
7. **Backups:** verify Neon PITR; a monthly restore drill you actually perform.

**Acceptance criteria:**
- [ ] Kill a worker mid-job; the job retries and completes without your intervention
- [ ] Upload a deliberately oversized file; it fails cleanly with an upgrade prompt and no
      alert fires
- [ ] Every error message in the app links to a docs page that answers it
- [ ] You take 7 days off; the weekly digest arrives and nothing needed you

**Time:** 6–8 agent-sessions. **Calendar: 14 days.**
**Cost:** ~US$30/month additional tooling.

**Kill criteria:** if you're spending more than 4 hours/week on support once docs exist,
it is not passive and does not meet your requirement.

---

## Phase 5 — Growth

**Objective.** Execute the three distribution channels.

1. **Free IDS authoring tool**, unauthenticated, no signup, at its own URL. Genuinely
   useful standalone. Every export footer: "Run this automatically on every revision →".
   This is channel one, lead magnet, and SEO asset in one artefact.
2. **SEO content**: one page per long-tail query from the deep dive. Each page must solve
   the problem completely on the page — partial answers to get an email will fail in this
   community.
3. **Community**: OSArch, buildingSMART national chapters, BIM LinkedIn. Publish the IDS
   template library openly.

**Acceptance criteria:**
- [ ] Free tool live and shared in at least 3 communities
- [ ] 10+ SEO pages published; at least 3 ranking in the top 10 for their query at 90 days
- [ ] Organic signups exceed referral signups by month 3 of this phase

**Time:** ongoing, 2–4 agent-sessions/month plus your writing.
**Cost:** ~US$20/month (Plausible).

**Kill criteria:** if 6 months of content produces under 100 organic signups/month, you
have no scalable channel; at $150 ARPU the business cannot fund paid acquisition, so
reconsider.

---

## Ordering and parallelism

```
Phase 0 ──[hard gate: all 4 thresholds]──► Phase 1 ──► Phase 2 ──► Phase 3 ──► Phase 4
   │                                          │                       │
   │ (may overlap: a 1-day technical spike    │                       │
   │  during Phase 0 to confirm ifcopenshell  │                       │
   │  handles a real 500MB file)              │                       │
   │                                          │                       │
   └──────────────────────────────────────────┴───────────────────────┴──► Phase 5
                                                    (start Phase 5 content
                                                     during Phase 3 — SEO
                                                     takes months to compound)
```

- **Phase 0 → 1 is a hard gate.** Nothing else is.
- **One exception to "no code in Phase 0":** a single-day spike loading a large real IFC
  with `ifcopenshell` to measure memory and time. That de-risks the Phase 1 kill criterion
  cheaply, and it's the one thing that could invalidate the whole plan on technical rather
  than market grounds.
- **Phase 3's three tasks are mutually independent** — parallelise freely.
- **Start Phase 5 SEO writing during Phase 3.** Content takes 3–6 months to rank; starting
  it at launch wastes a quarter.
- **Phase 4 can partly overlap Phase 3**, but monitoring must land before your first
  paying customer depends on uptime.

## Totals

| | Agent-sessions | Calendar | Cumulative cost |
|---|---|---|---|
| Phase 0 | 2 | 14–21 days | <NZ$200 |
| Phase 1 | 6–8 | 10–14 days | ~US$20/mo |
| Phase 2 | 8–10 | 14–21 days | ~US$40/mo |
| Phase 3 | 10–14 | 21–30 days | ~US$60–120/mo |
| Phase 4 | 6–8 | 14 days | ~US$90–150/mo |
| **To a passive, paid product** | **32–42** | **~3–4 months** | **under US$200/mo** |

The infrastructure cost is not the risk. The risk is that Phase 0 says yes when it should
have said no — which is why the thresholds are written down before you start.
