# CodeGraph Evaluation - First Real Repo Test

## Date
2026-05-24

## Repo tested
`/Users/gibby.ai/.openclaw/workspace/first-client-engine/product`

## Why this repo
The earlier StreetLegal folder test was not representative because the top level was dominated by temp scripts, content files, and HTML-heavy artifacts.

This repo was a better evaluation target because it contained real application logic with Python and JavaScript files, named modules, and actual workflow code that an agent might need to understand quickly.

## Result
CodeGraph performed well enough on this repo to justify keeping it installed.

## What worked
- successful initialization and indexing
- indexed 14 files
- built 145 nodes and 316 edges
- project structure view was useful
- symbol search was useful
- context-building for a real architecture question was useful

## Real test question
"How does the review queue flow from capture to API response?"

## Useful output observed
CodeGraph surfaced a compact map centered around these functions/files:
- `review_flags`
- `append_review`
- `normalize_review_shape`
- `analyze`
- `do_POST`
- `load_store`
- `save_store`
- queue/review-related modules

This was the first output that felt like real acceleration rather than a toy demo.

## Important limitations discovered
- CodeGraph was not useful on the current `streetlegal/` top-level folder as tested
- content-heavy or HTML-heavy directories are a weak fit
- repo choice matters a lot
- the installed CLI surface did not expose every richer command mentioned in some README examples
- confirmed working CLI commands in this test: `init`, `status`, `files`, `query`, `context`
- attempted `callers`, `callees`, and `impact` commands were not present in the CLI build tested

## Current judgment
### Keep installed
Yes.

### Best use cases
- real application repos
- codebase orientation
- architecture tracing
- pre-edit workflow understanding
- reducing wasteful search/explore loops

### Weak use cases
- article/content trees
- HTML-heavy directories
- repos so small that normal search is already cheap

## Decision
Keep CodeGraph installed in Claude Code and Codex CLI.

Use it selectively on real code repos, not as a universal knowledge tool.

## Next step
Design the AgentMemory pilot carefully before installing or connecting it broadly.
