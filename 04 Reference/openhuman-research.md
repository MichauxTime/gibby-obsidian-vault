# OpenHuman

## What it is
An open-source personal AI superintelligence desktop app with local memory storage, Obsidian-style markdown vault, and managed cloud services for model routing, web search, and OAuth integrations.

## The good
- Local-first design: memory tree and workspace config live on your machine, not a cloud
- Ships with Composio connector layer for 3rd-party integrations and OAuth flows
- Homebrew/apt/MSI install paths with proper package signing chains
- Multi-language README (EN, ZH, JP, KR, DE) signals strong community traction
- Trending on Product Hunt and TrendShift — momentum is real

## The bad
- Early beta with rough edges explicitly called out in the README
- Managed backend still required for real-time triggers and some hosted features — not fully air-gapped
- No-integrity-check script install is a footgun for less careful users

## Watch out for
- The managed backend means tinyhumans.ai has visibility into account sign-ins, model routing, and OAuth flows — read their privacy policy before storing sensitive business data
- Feature gaps between "bring your own everything" mode and the default managed experience are not well-documented

## Top 5 use cases for us (Gibby/StreetLegal/Stylograph context)
1. Replace the current ad-hoc Claude Code + memory files setup with a unified local AI workspace that persists context across tools
2. Use the Composio connector layer to wire Stylograph pilot-school integrations (Pitt, Notre Dame CRM flows) without custom OAuth code
3. Store StreetLegal jurisdiction research in the Obsidian-style vault with AI-queryable memory rather than flat markdown files
4. Local memory tree as a private alternative to cloud-stored customer context for Stylograph donor communications
5. Test as a lightweight agent harness for the StreetLegal outreach pipeline before committing to a heavier platform build

## Verdict
Watch closely — if the local memory + Obsidian vault integration matures past beta, this could replace the current fragmented Claude Code workspace setup.

## Source
https://github.com/tinyhumansai/openhuman
