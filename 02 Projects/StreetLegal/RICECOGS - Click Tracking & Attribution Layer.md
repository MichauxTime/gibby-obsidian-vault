---
type: ricecogs
project: StreetLegal
status: approved-to-build
created: 2026-06-16
tags: [streetlegal, ricecogs, attribution, click-tracking, marketplace]
---

# RICECOGS — Click Tracking & Attribution Layer

> **Up:** [[00 Canon]] (traffic attribution = the closing layer) · [[StreetLegal Kitchen & Truck Marketplace]]

## TL;DR (one sentence)
Track every outbound click we send to a kitchen/truck, then prove it back to them ("we sent you X clicks this week") so claims convert and upgraded profiles sell themselves.

---

## Deep version

### The play (why this is the moat's cash register)
StreetLegal's marketplace is the moat; **attribution is how the moat makes money.** Same play Ben ran at Niche: connect a partner's Google Analytics read-only, build them a traffic dashboard, then the relationship is sticky because *we* own the proof of value. Here: city guide says "you need a commissary" → we hand them the kitchen list → we count the click → we email the kitchen "StreetLegal sent you 47 visits in Austin this month, 6 were ready-to-book." That email is the upsell.

### Scoring (1–10)
- **Reach (8):** Every kitchen/truck profile + every city guide that links out is a tracking surface. Scales with the marketplace itself.
- **Impact (9):** This is the closing layer. Turns free claims into paid upgraded profiles and gives us the single best retention argument (proven ROI). Direct revenue lever.
- **Confidence (7):** Proven pattern (Niche). Risk is data quality + getting partners to connect GA, not whether the play works.
- **Effort (5):** Click tracking is cheap (redirect + log). Per-partner GA read-only dashboards are the heavier lift; phase it.
- **Cost (3):** Mostly our own infra (redirect endpoint, Postgres table, email engine we're already building). Low marginal cost.
- **Opportunity-cost (low):** Reuses the triggered-email engine + marketplace data already on the roadmap; little new surface area.
- **Goal-fit (10):** Directly serves "prove value fast, get operators paying."
- **Strategic-fit (10):** No competitor connects permits→kitchens, and none can prove attribution. Double moat.

### Build phases
1. **Click capture (cheap, do first):** outbound links go through a tracked redirect (`/out?to=…&kitchen_id=…&src=city_guide`) → log to Postgres `outbound_clicks` (kitchen_id, target, source_page, city, ts, session). Respect "noindex until data real" — no fake counts shown until real traffic exists.
2. **Aggregation:** weekly/monthly rollups per kitchen/truck + per city.
3. **Triggered email:** "StreetLegal sent you X clicks" — rides the [[triggered-email engine]]. Prioritize kitchens with real, non-trivial counts.
4. **Cross-sell hook:** attribution tied to kitchen *location* → "you're getting traffic in Austin, we have a kitchen there" / "claim your profile to capture it."
5. **GA read-only dashboards (premium, last):** partner connects Google Analytics read-only; we build their traffic dashboard. This is the high-touch upsell — gate behind upgraded profile.

### Dependencies
- Triggered-email engine (sibling RICECOGS, to write)
- Marketplace profile/claim model ([[StreetLegal Kitchen & Truck Marketplace]])
- Own-data dashboard (internal view of these clicks)

### Risks / guardrails
- **Data honesty (Canon):** never show fabricated or thin attribution numbers. Hidden until real.
- **Privacy:** outbound redirect logging must not leak PII; aggregate, don't expose individual user sessions to partners.
- **Demo dashboards** (the paid-feature mockups) must be clearly labeled as examples, not real partner data.

### Definition of done (show-don't-claim)
- Live tracked redirect logging real clicks (verified row in Postgres + screenshot).
- One real weekly rollup for ≥1 kitchen.
- One sample "we sent you X clicks" email rendered (not necessarily sent) with real numbers.
