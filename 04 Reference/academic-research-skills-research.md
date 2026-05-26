# Academic Research Skills (ARS)

## What it is
A comprehensive Claude Code skill suite covering the full academic research-to-publication pipeline — literature review, paper writing, citation verification, peer review simulation, and integrity gating.

## The good
- 13-agent deep research team plus 12-agent paper-writing team with integrity gates built in
- Citation hallucination detection (motivated by Zhao et al. 2026 finding 146k hallucinated citations in one year across arXiv/bioRxiv)
- Claim-level audit mode (ARS_CLAIM_AUDIT=1) that fetches cited sources and verifies claims are actually supported
- Style Calibration learns your voice from prior work; Writing Quality Check flags AI writing patterns
- Ships as a Claude Code plugin installable in 30 seconds via /plugin marketplace

## The bad
- Cost: ~$4-6 per full 15k-word paper pipeline run — adds up fast for bulk use
- Full pipeline requires Pandoc + tectonic for DOCX/PDF output; Markdown only without optional deps
- Cross-model verification (ARS_CROSS_MODEL) requires separate API key management

## Watch out for
- Heavy dependency on Anthropic API key billing — not covered by Claude Code subscription; direct API calls violate Ben's hard rule about no direct API keys
- v3.8 claim audit ramp-on plan is deferred to post-calibration evidence — integrity guarantees are aspirational at current version

## Top 5 use cases for us (Gibby/StreetLegal/Stylograph context)
1. Produce research-grade permit and jurisdiction briefs for StreetLegal with citation verification baked in, not bolted on
2. Use the literature review pipeline to systematically scan academic papers on donor relations and handwritten communication efficacy for Stylograph pitch decks
3. Run the peer-review simulation agent on Stylograph pricing proposals or grant applications before external submission
4. Apply Style Calibration to train on Ben's existing writing samples so AI-assisted content matches his voice for outreach emails
5. Use the integrity gating (Stage 2.5 and 4.5 blocking checklists) as a QA layer for any content that goes to institutional clients

## Verdict
Watch — powerful integrity infrastructure but the API cost model and direct-key requirement conflict with current stack rules; revisit when Claude Code plugin billing is clarified.

## Source
https://github.com/Imbad0202/academic-research-skills
