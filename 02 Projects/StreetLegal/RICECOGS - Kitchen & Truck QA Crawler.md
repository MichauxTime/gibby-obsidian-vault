---
type: ricecogs
project: StreetLegal
status: queued
created: 2026-06-16
tags: [streetlegal, ricecogs, qa, marketplace, crawler]
---

# RICECOGS — Kitchen & Truck QA Crawler

> **Up:** [[00 Canon]] · [[StreetLegal Kitchen & Truck Marketplace]]

## TL;DR (one sentence)
A cron that crawls every kitchen/truck profile like a skeptical user and flags broken images, dead links, missing data, and ugly fallbacks — so the marketplace always looks finished, never half-built.

---

## Deep version

### Why it matters
The marketplace is the moat, and Ben cares intensely about visual polish — a broken hero image or an empty profile reads as "abandoned product" and kills trust on the exact pages we want operators to claim and pay for. Manual spot-checking doesn't scale to hundreds of profiles. A QA crawler keeps the whole surface presentable continuously.

### Scoring (1–10)
- **Reach (9):** Every kitchen + truck profile, every linked-out URL.
- **Impact (7):** Directly protects conversion on claim/upsell pages; prevents the "looks broken" trust hit.
- **Confidence (8):** Crawling + assertions is well-trodden; low ambiguity.
- **Effort (4):** Light — headless fetch + a rules checklist.
- **Cost (2):** Own infra + cheap model.
- **Opportunity-cost (low):** Reuses image/data work already underway.
- **Goal-fit (8):** "Prove value fast" requires the surface to look done.
- **Strategic-fit (7):** A polished marketplace is the differentiator.

### What it checks per profile
1. **Hero image:** present, loads (HTTP 200, not expired CDN), correct aspect, not a broken placeholder. If fallback card is shown, confirm it's the designed one, not a broken `<img>`.
2. **Data completeness:** name, city, address, the commissary/permit linkage, contact — flag thin profiles (ties to "noindex until data real").
3. **Links:** outbound website/social links resolve (and, once attribution ships, route through `/out?...`).
4. **Consistency:** light design system respected, no leftover lorem/test data, no dark-theme leakage.
5. **Sort/surface:** image-backed + complete profiles actually surface at the top of /dashboard/kitchens.

### Output
- A QA report: count healthy vs flagged, top issues, and a prioritized fix list. Image-backed-but-broken and thin-profile-indexed are highest severity.
- Optionally auto-fix the trivial ones (e.g. re-cache an expired image) and only escalate the rest.

### Definition of done
- Cron crawls all profiles, emits a health score + flagged list with reasons, and verifies the top-of-page profiles render real images. Catches at least the known fragile cases (expiring CDN hero URLs, null cover_photo_url shown as broken).
