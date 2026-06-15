---
title: StreetLegal City Rankings & Grades Initiative
type: project
status: active
created: 2026-06-15
tags: [streetlegal, seo, rankings, grades]
---

# StreetLegal City Rankings & Grades Initiative

The "Niche.com for food trucks" play. We publish data-backed **grades and rankings** for every food-truck market, rolled up city → county → state → country. Each ranking page is a linkable SEO asset and the rollups create a defensible content moat competitors can't cheaply replicate.

## Hard rules
- **Build hidden first.** New ranking/grade pages ship `noindex` and stay OUT of the sitemap until the underlying data is real and complete. Do NOT make them findable/indexable until Ben signs off. (Same rule as the vendor-permit expansion.)
- **Never invent data.** A grade with no real cost/health/count data behind it is worse than no grade. Missing data → exclude, don't guess.
- **Reminder is standing.** Sunday 7:15 PM ET Discord reminder so Ben never loses track. Cron id `2051ce69-01aa-4cee-ab60-f02b776d628d` (isolated, codex runtime, delivers to #gibby-hq, failure-alerted).

## Ranking dimensions (multiple grades per market, Niche-style)
1. **Permit Ease Grade (A–F)** — BUILT. How easy + cheap to get legal. Cost 40% / Time 25% / Complexity 20% / Friction 15%. Script: `streetlegal/permit-grades/score_grades.py`.
2. **Health Department Ranking** — strictness/turnaround/inspection burden per jurisdiction. TODO.
3. **Overall Truck-Friendliness Ranking** — composite market score (permit ease + density + commissary supply + event volume). TODO.
4. **Food-Type / Cuisine Analysis** — which cuisines thrive in a market, # of trucks per type, and **gap analysis**: cuisines NOT yet present that the market could support. TODO — strong blog/SEO angle.
5. **Commissary Supply Gaps** — where commissary capacity is thin (e.g. "not enough fry-capable locations in this market"). Doubles as a B2B hook for existing/aspiring commissary owners. TODO.

## Rollup hierarchy
- **City** → the atomic unit, where searchers look
- **County** → real regulatory boundary (health permits are county-issued in most states); grade where ≥2 cities
- **State** → population-weighted rollup of city grades
- **Country** → national rankings/leaderboards
- **ZIP: explicitly NO** — not a permit jurisdiction; would be thin/duplicate pages that risk an SEO penalty.

## Inclusion thresholds (state)
- **FULL grade:** ≥5 cities incl. the largest metro
- **PROVISIONAL grade:** 3–4 cities (labeled as such)
- **<3 cities:** "coverage in progress," no grade yet

## Content / blog angles (each market)
- What truck types currently operate in [market]
- Which cuisines DON'T exist yet → opportunity for new operators
- Commissary capacity & gaps → opportunity for commissary builders
- Permit-ease + health-dept grade explainer per city/county/state

## Current status (as of 2026-06-15)
- **Permit Ease Grade:** 41 cities scored cleanly. 217 cities in dataset; 176 missing a first-year cost total (have fee tables but no summed total).
- **States clearing the 3-city bar:** CA — C (69.5, 6 cities, FULL) · TX — C (64.8, 7 cities, FULL) · FL — B (72.2, 4 cities, PROVISIONAL).
- **Highest:** FL (B). **Lowest:** TX (C, dragged by Austin/Plano/Fort Worth on cost).
- Files: `streetlegal/permit-grades/{score_grades.py, city_inputs.json, grades.json}`

## The single highest-value next step
**Cost-summing extraction pass:** 165 cities have component fee tables (license + health + fire + commissary) but no "Total First Year" row, so the scorer skipped them. Sum the components → unlocks ~165 more cities → pushes a dozen+ more states over the 3-city bar. This is the lever that turns 3 graded states into many.

## Open backlog
- [ ] Cost-summing extraction pass (unlocks most of the 165 stalled cities)
- [ ] Fix 65+ broken state→city links (state pages link to unpublished city guides) — see live-site audit 2026-06-15
- [ ] Dedupe 4 city slugs (jacksonville, raleigh, richmond, orlando) — double-counts cities in rollup
- [ ] Design health-department ranking rubric
- [ ] Design cuisine gap-analysis data model (need per-market truck inventory by cuisine)
- [ ] Design commissary supply-gap metric
- [ ] Build hidden/noindex ranking page template (city + county + state)
