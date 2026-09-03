# Marketplace Payments Rails — the finding that saves months (2026-09-03)

[S] = search-result summary + URL. **Most "marketplace distribution" plans assume a checkout that does not exist.** Two separate questions must be asked of every platform: *is there a payments rail?* and *is the listing worth having for discovery?* On most platforms the answers are **no** and **yes, as one channel among several**.

| Platform | Real payments rail for a NEW solo dev in 2026? | Discovery | Fee / rev-share |
|---|---|---|---|
| **monday.com** | **YES — built-in Stripe checkout, and monetisation has been MANDATORY for all new marketplace apps since July 2024** [S] developer.monday.com/apps/docs/monetization | 850+ apps, 1.6M installs [S] businesswire.com | 85/15 split **after $200K lifetime revenue**; sub-threshold split **not disclosed publicly** |
| **Discord** | **YES — but developers must be based in US/UK/EU** [S] support-dev.discord.com — **excludes an NZ operator from Discord's own rail.** Skews consumer/gaming | Store-page surfacing | Not disclosed |
| **Canva** | **PARTIAL — application/invite only.** Eligibility requires "consistent MAU growth" [S] canva.dev/docs/apps/premium-apps/ | 300+ apps, 1B+ uses [S] | Individual agreements |
| **Figma** | **CLOSED TO NEW SELLERS.** Official support reply: *"we're not currently approving new creators to sell paid resources on the Community"* [S] forum.figma.com/t/no-approval-of-new-paid-plugin-creators/85160 — **a genuine trap for anyone assuming Figma works like Shopify** | Huge (10M+ designers), same-day listing for free plugins | N/A for new entrants |
| **Notion** | **NO.** No Notion-run billing for apps/integrations; only the separate Template Marketplace has Stripe onboarding, and that is for static templates. The **May 2026 "3.5 Developer Platform"** (Workers, CLI, Agent SDK, webhooks) added **no payment rail** [S] notion.com/releases/2026-05-13 | Plain directory listing, no ratings/rankings | External Stripe only |
| **Airtable** | **NO.** Marketplace supports free apps only, no native revenue share [S] platformappstores.com. A developer asked in Airtable's own AMA why anyone would build for free with no incentive [S] community.airtable.com | Small; formal security/CLI review required | None |
| **Webflow** | **NO native billing for apps.** 300+ vetted apps, 10–15 business day review [S] developers.webflow.com | Real, curated (2FA, demo video, security review) | None documented |
| **Slack** | **NO.** "A discovery engine, not a billing platform" — no checkout, no subscription management [S] dodopayments.com | 2,600+ apps | None |
| **Zapier** | **NO.** "Premium app" only gates the integration behind Zapier's own paid plans — **Zapier keeps that revenue; it is not a developer payout** [S] help.zapier.com | Massive: 7,000–9,000+ integrations, 3M+ users, 100K+ paying customers [S] | None — pure discovery |
| **Make.com** | **NO** — "it is the partner's responsibility to bill their customers" [S] developers.make.com | 3,000+ apps; requires an active Partnership Agreement | None |
| **HubSpot** | **NO billing**, but **0% revenue share** [S] | 2,000+ apps, **2.5M+ active installs** (Oct 2025) [S] community.hubspot.com | 0% |
| **ClickUp** | **NO third-party marketplace at all** — it is an open *feature request*, not a shipped product [S] feedback.clickup.com | **No real third-party discovery** | N/A |

## Two structural findings worth more than any single idea

**1. Make.com's anti-duplicate policy is a genuine, rare structural moat.** Make "tries to avoid duplicate situations and will only accept an app if [the incumbent developer is] not actively developing it" [S] developers.make.com. **Being the first native app for a given service can effectively lock out later native competitors** — a Tier 2 defence that no other platform here offers. A cloner would be forced into a worse HTTP-module workaround.

**2. Webflow sunset native User Accounts on 29 January 2026**, killing native recurring subscriptions and pushing all such customers onto third parties [S] webflow.com/updates/deprecating-logic-and-user-accounts. A dated, forced migration — the strongest "why now" in the platform sweep.

## Candidates arising
- **Make.com first-native-app for an underserved vertical.** Concrete verified example: **Buildium (property management) is not on Zapier at all** — "there's no plug-and-play way to trigger actions from Buildium" [S] beyondprograms.ca; property managers reportedly spend **$8,400–$14,200/year** on middleware, developer maintenance and failure recovery to patch the gap [S]; and **Tenant Turner launched its own Zapier integration in July 2025 "to meet growing demand"** [S] tradingview.com — the category is actively contested.
- **Notion compliance-grade backup.** A solo founder runs "Notion Backups" at ~**US$2,300 MRR** on $6/$10/$24 tiers [SELF-REPORTED] indiehustle.co. Notion trashed pages are permanently deleted after 7/30/90 days by plan, and version history is admin-deletable [S] backups.so. But competitors are many (SimpleBackups $49–$299/mo, ProBackup, BackupLABS) and clone resistance is LOW.
- **HubSpot silent workflow-failure alerting.** A HubSpot Ideas thread "Workflow Error Notifications" was **still being updated 19 Sept 2025** [S] community.hubspot.com, and HubSpot's native tooling is passive log review only [S]. **But this is an obvious, oft-requested, low-effort HubSpot feature — highest absorption risk of anything found.**
- **Webflow post-sunset subscription reconciliation.** Vendor-neutral reconciliation across Stripe + Memberstack/Outseta + Webflow CMS. Memberstack $25/$39/$79/$399 [S]. Positioned complementary, not head-on.

## Could not verify
monday.com's revenue split **below** the $200K threshold. Whether an NZ operator could access Discord Premium Apps via a US entity. Canva's actual MAU bar. Backups.so pricing. Current top-voted un-built items on Make's Idea Exchange.
