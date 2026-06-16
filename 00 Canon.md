---
type: canon
status: living
created: 2026-06-16
tags: [canon, moc, source-of-truth]
---

# 00 Canon — Source of Truth

The load-bearing truths. Small on purpose. If everything is "important," nothing is — so this stays curated. Every project/system note should link **up** to the relevant Canon entry here, and the weekly graph-linker enforces those connections automatically.

> Rule for what belongs here: a truth is **Canon** only if getting it wrong would break trust, waste real money, or send a project the wrong direction. Behavioral/working-style rules live in auto-memory; this is product + decision Canon.

## Hard Rules (do-not-violate)
- **Acknowledgment ≠ action.** Every agreed item gets a real tracked status (doing now / scheduled / RICECOGS-queued) or is plainly killed. No floating "yes I'll do that."
- **RICECOGS for everything**, even tiny ones, with a planning stage before bigger builds.
- **Show, don't claim.** Nothing is "done" without verification the user can see (live URL, screenshot, test).
- **No direct API keys** for user-facing features — subscription-routed / local paths only.
- **Noindex until the data is real.** Build new pages/profiles hidden (noindex / not in sitemap) until the underlying data is genuine and verified. Never ship thin or fake-data pages to the index — it burns trust and SEO. Flip to indexable only once the data is real.
- **CAU is dead.** Never reopen.

## Core Product Bets
- [[StreetLegal Kitchen & Truck Marketplace]] — full profiles for every kitchen + truck, claim/upsell model, proven via traffic attribution. The marketplace is the moat.
- Commissary-kitchen ↔ permit integration is StreetLegal's defensible differentiator (no competitor connects them). See [[Permit Requirements (MOC)]] → [[Commissary Kitchen Requirements]].
- Traffic attribution ("we sent you X clicks") is the closing layer that converts claims and upsells.

## Key Decisions
- Kitchen/truck media hosted on **S3** (2026-06-16).
- Two-tier ranking: Permit Ease Grade (live) + Overall Friendliness (planned). See methodology canon.

## How Canon works
- Add an entry here only when it clears the bar above.
- New project notes link up to the relevant bullet using [[wikilinks]].
- Weekly `obsidian-graph-linker` cron re-connects old ↔ new and flags missing RICECOGS.
- Revisit this whole file monthly — prune what's stale, promote what's proven.
