---
type: ricecogs
project: StreetLegal
status: queued
created: 2026-06-16
tags: [streetlegal, ricecogs, email, lifecycle, attribution]
---

# RICECOGS — Triggered Email Engine

> **Up:** [[00 Canon]] · [[StreetLegal Kitchen & Truck Marketplace]] · feeds [[RICECOGS - Click Tracking & Attribution Layer]]

## TL;DR (one sentence)
A reusable event-driven email engine that fires the right message at the right moment — "we sent you X clicks," weekly events + new-in-area kitchens, claim-your-profile nudges — and is the delivery rail every StreetLegal growth loop plugs into.

---

## Deep version

### Why it's foundational
Almost every StreetLegal growth loop ends in an email: attribution proof, engagement digests, claim/upsell nudges, permit-deadline reminders. Building one solid triggered-email engine once means attribution, weekly engagement, and lifecycle nudges all ride the same rail instead of being rebuilt three times. LaunchQ already taught the hard lesson: sending email isn't enough — reply handling and deliverability matter.

### Scoring (1–10)
- **Reach (8):** Every operator + waitlisted/engaged user is reachable.
- **Impact (8):** It's how value gets *proven* and upsells get *asked for*; without it the marketplace data just sits there.
- **Confidence (7):** Email infra is well-understood; risk is deliverability/spam + reply handling.
- **Effort (6):** Moderate — templating + trigger rules + send infra + suppression/unsub + reply destination.
- **Cost (3):** Subscription-routed / existing transactional provider; NO direct API-key product dependency.
- **Opportunity-cost (low):** Shared rail amortized across many loops.
- **Goal-fit (9):** Directly drives claims, upsells, retention.
- **Strategic-fit (8):** Proof-of-value emails are the closing layer.

### Architecture
1. **Trigger sources:** events table (attribution rollup ready, new kitchen in user's area, profile claimed, permit deadline, waitlist signup).
2. **Audience rules:** prioritize engaged / waitlisted users; suppress unsubscribed; frequency caps.
3. **Templates (light design system):** weekly engagement digest (events + new-in-area kitchens, REAL high-quality images with graceful fallback), attribution proof ("we sent you X clicks"), claim-your-profile, upsell.
4. **Send + deliverability:** verified domain (SPF/DKIM/DMARC), suppression list, unsubscribe, bounce handling.
5. **Reply handling (LaunchQ lesson):** replies must land somewhere real and monitored — not a black hole.
6. **Tracking:** opens/clicks feed back into the attribution + engagement loops (closing the cycle).

### Hard rules
- NO direct API keys for the send path — subscription-routed / existing infra.
- Real images only in digests; designed fallback if missing (no broken placeholders).
- Verify events shown are actually free + available to all users before sending an events digest.

### Definition of done
- Engine fires at least one real triggered email end-to-end (trigger → audience → render with real data → send → reply lands somewhere monitored), verified with a real rendered sample and a delivered test. Weekly engagement digest + attribution proof are the first two templates live.
