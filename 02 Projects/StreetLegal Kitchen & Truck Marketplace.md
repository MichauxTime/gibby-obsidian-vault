---
type: project
status: active
created: 2026-06-15
tags: [streetlegal, marketplace, kitchens, trucks, profiles, triggers, attribution]
---

# StreetLegal Kitchen & Truck Marketplace

The marketplace layer of StreetLegal: full profiles for every commissary kitchen and food truck, built by us, monetized via claim + enhanced-profile upsell, and proven valuable through traffic attribution.

## Core model
- Build a profile for **every** kitchen and truck we can find (more pages = better SEO, users stay on-platform).
- Pre-fill everything from their website + reasonable assumptions (e.g. pizza truck → pizza oven).
- Owner claims profile → controls it, unlocks more.

## Kitchen profiles
- One **public hero image** (relevant, scraped from their site). Rest held in profile, unlocked on claim/upgrade (carousel).
- Equipment list, reviews, special notes, call-outs to all trucks, availability calendar (trucks see who's open when).
- Their website linked **only here** for now — unlock more exposure with upgrade. (This also routes 100% of their referral traffic through us = clean attribution.)
- Premium tiers: more images, sponsored listings, triggered emails on their behalf, "send your kitchen to every new truck that signs up."

## Truck profiles
- Simpler. List what's on the truck (equipment) so we can suggest best-fit kitchens.

## Reviews (both sides)
- User-generated content; reason for owners to claim/control.
- Email owner on each new review; let them respond on-platform.

## Triggered emails (build out)
- New profile created → notify the truck/kitchen.
- Market milestone: "5 kitchens now in your market" (scale to market size).
- New kitchen in your area (or weekly digest of additions — likely best).
- **Traffic-proof email:** "We sent you X clicks this week/month — are you seeing it?" (see Attribution below).

## Click tracking & traffic attribution (NEW — 2026-06-15)
The value-proof + closing layer. Tiers:
1. **Outbound click tracking (build now, easy):** redirect/tracker on every outbound link to kitchen/truck sites. Since our profile is the only place their site is linked, 100% of referral traffic flows through us = clean, defensible attribution.
2. **"We sent you X clicks" trigger email:** strongest claim-your-profile hook yet — proof of value, not just "claim it."
3. **GA read-only dashboard offer (higher-touch, the closer):** offer to connect to their Google Analytics (read-only) and build them a traffic dashboard. (Ben ran this exact play at Niche — connect GA, show "here's your traffic, here's where to target.")
4. **Location cross-sell loop:** tie attribution to our kitchen locations — "you're getting a lot of traffic in Austin; we have a kitchen available there." Ties the two products together, proves conversions, closes the loop.

## QA / maintenance discipline
- **Crawler QA agents** (kitchen-crawler, truck-crawler): act as the owner, audit each profile against their website, flag anything wrong/outdated. Needs a RICECOGS.
- **Not set-and-forget:** revisit everything monthly — relevance, accuracy, clean code.
- All sub-systems should each have a RICECOGS, linked in Obsidian, rolling up into this project note.

## Open RICECOGS to write
- [ ] Cursive connection real-fix (in progress — separate)
- [ ] Kitchen/truck profile QA crawler
- [ ] Triggered-email engine
- [ ] Click-tracking & attribution

## Related
- [[00 Canon]] — this project is Canon's primary product bet ("marketplace is the moat")
- [[StreetLegal Master Note]] — operating note for all StreetLegal
- [[Kitchen Image Enrichment + Premium Profiles]] — image scraping + premium gating spec
- [[Reviews + Truck Auto-Profiles]] — reviews surface + truck pre-build pipeline
- [[StreetLegal - Kitchen and Truck UX Decisions Jun 12]] — locked UX decisions for truck discovery + kitchen dashboard
- [[Kitchen Booking - Video Content Plan]] — video content pipeline for kitchen booking launch
