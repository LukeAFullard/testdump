# Data Products, Rebuild Plays & Platform Tailwinds — Findings (2026-09-03)

[S] = web-search summary with URL; [I] = inference.

## NZ Open Banking / Customer and Product Data Act
- Regulated open banking live **1 Dec 2025** for ANZ/ASB/BNZ/Westpac; nine third parties already live at launch. [S] apicentre.paymentsnz.co.nz
- **Akahu** is the dominant NZ intermediary (130+ org customers), **$0.15/successful payment request** — a real, priced rail. [S] akahu.nz/pricing
- Kiwibank must complete rollout by **30 Nov 2026** (~95% consumer coverage). [S]
- **PLATFORM RISK HIGH:** the Payments NZ API Centre **ceases operating end of September 2026**, standards continuity passing to MBIE/CPDA. [S] Mitigation: build on Akahu's abstraction, not raw bank APIs.
- **Clone resistance LOW** — anyone can plug into Akahu. Moat would have to be workflow/UX.
- Could not identify the nine live third parties or Akahu's reseller terms (budget exhausted).

## HS-code / import-duty classification API
- Incumbent "Tariffs API" at **$199/mo for 100k calls**, positioned against Avalara. [S] tariffsapi.com
- **Avalara publishes no pricing** — custom enterprise quote only [S] developer.avalara.com — confirming an underserved self-serve tier.
- 4 named players: Avalara, Zonos, GingerControl, Tariffs API.
- Clone resistance LOW–MEDIUM; real moat is keeping country duty-rate changes current — which is also a real maintenance burden against the 3 hr ceiling.
- WCO IP position on reproducing HS nomenclature text **NOT confirmed**.
- "Why now" (2025–26 tariff volatility) is **[I] inference, not evidenced**.

## Vendor-sunset rebuild plays — pattern real, these instances CLOSED
- **InkFrog** (Wix-owned eBay tool): shutdown announced 29 Apr 2026, effective 1 Jun 2026. [S] valueaddedresource.net — **7+ competitors already positioned within weeks** (Frooition, Nembol, CedCommerce, Webinterpret, 3Dsellers, GeekSeller, MyListerHub).
- **Delighted** (Qualtrics NPS tool): signups blocked 1 Jul 2025, full shutdown 30 Jun 2026. [S] Price anchor 100 responses/mo = $39, 500 = $249. **6 competitors already positioned.**
- **Verdict:** today is 3 Sept 2026 — 3 and 2 months after these shutdowns. By the time a sunset is visible in search results, 6–8 competitors have moved. Watch for announcements **weeks** old, not months. Clone resistance for this class is inherently LOW.

## US restaurant health-inspection data
- Rat Radar aggregates 34 US cities [S] ratradar.com; Foodspark sells inspection scraping as a service [S].
- "No single API aggregating this data nationally... not structured for automated extraction" [S] origami.chat — confirms fragmentation and labour cost.
- Clone resistance **MEDIUM–HIGH if narrow** (per-jurisdiction integration accumulates), but hundreds of differently-formatted government sites = weekly breakage risk. Restrict to one state/metro.
- "Why now" **WEAK** — evergreen, no fresh catalyst.

## NZ building consents — RED FLAG, do not build without legal check
- ~67 territorial authorities, no centralised consents API. [S] building.govt.nz
- **NO COMPETITORS FOUND.** Per the brief's rule this is a red flag. Likely cause: consent applications carry homeowner personal information and NZ Privacy Act treatment of bulk commercial redistribution is unresolved. **Licence/legality NOT confirmed** — the most consequential unresolved question in the set.

## NZ Charities Register — legally clean, commercially thin
- 27,800+ charities, daily updates, open OData/JSON/CSV API, no auth. **CC BY 3.0 NZ — commercial reuse explicitly permitted.** [S] charities.govt.nz, catalogue.data.govt.nz
- But the official data is already free, structured and complete — nothing to accumulate that a competitor can't replicate in an afternoon. No moat.

## MCP monetisation — REJECT (the trap the brief warned about)
- **"Over 20,000 MCP servers in the wild... less than 5% have ever made a single dollar."** [S] synthesized from dev.to sources.
- Reported successes are self-reported and vendor-sourced (a $2,000/mo Apify claim; a "$10K MRR in six weeks" claim explicitly flagged unverified). Confirmed real numbers are tiny: Lemon Squeezy $45.50/30 days, Ghost Pro $19/mo, Buttondown $10/mo. [S]
- Payment rails now exist (MCPize/Stripe Connect, x402) — a genuine <18-month tailwind — but actual paid usage is a near-zero long tail with unverifiable outliers promoted by platforms that profit from the hype. **Hyped ecosystem, thin real market.**

## Confirmed-clean licences (for contrast)
NZ Charities Register (CC BY 3.0 NZ); US CPSC/SaferProducts recall data (US public domain, no API key).

## Could not verify
Nine NZ open-banking third parties; GETS tender-data redistribution terms; vessel/aircraft registry terms; Rat Radar and Foodspark pricing; eBay Developer API terms; per-county health-department ToS; Akahu reseller terms; Formbricks licence; WCO HS nomenclature IP.
NZ Companies Office/Insolvency Register: guidance **discourages** maintaining a copied database ("onus is on you to ensure... complies with the Privacy Act") — ambiguous, neither clean permission nor clean ban.
