# AgentMemory Pilot Result - First Recall Test

## Date
2026-05-24

## Pilot target
`/Users/gibby.ai/.openclaw/workspace/first-client-engine/product`

## Pilot lane
- Codex only
- technical continuity only
- no broad OpenClaw rollout
- no personal/social memory mixing

## Goal
Test whether a second-pass task on the same repo would benefit from prior orientation memory instead of behaving like a full cold-start every time.

## What happened
### Pass 1
A memory-backed Codex orientation run was used to map:
- entry points
- core modules
- storage path
- likely end-to-end review flow

### Pass 2
A second Codex task was run on the same repo asking:
- what is the likely highest-value improvement to the review pipeline?
- what is being recalled versus re-verified?

## Result
This was the first useful signal that the AgentMemory pilot may actually help.

The second pass did not behave like a blind cold restart. It produced a tighter answer and explicitly separated:
- recalled understanding
- re-verified current facts

That distinction is important and healthy.

## Best improvement identified during recall pass
Add a hard confidence / escalation gate so that low-trust or failed LLM review outcomes are automatically marked `needs_attention` instead of quietly blending into normal pending queue flow.

### Likely implementation points
- `api_server.py` — primary policy point for `/review`
- `llm_review.py` — confidence/provenance normalization
- `sqlite_store.py` — persistence additions if needed
- `queue_summary.py` — explicit surfacing of escalated/low-confidence cases

## Why this was a meaningful test
This was not just a vague summary task.
It required:
- remembering repo structure
- using prior architectural understanding
- re-checking only the critical pieces
- producing a practical recommendation grounded in the live code

That is close to the real continuity value we actually want.

## Current verdict
### What is now true
- AgentMemory pilot setup is working
- Codex-only narrow pilot was the right first move
- there is now initial evidence of useful recall behavior

### What is not yet proven
- long-horizon retrieval quality
- contamination resistance over many sessions
- correction/deletion workflow quality in real messy use
- whether it remains useful after more varied tasks accumulate

## Recommendation
### Keep going
Yes, but keep it narrow.

### Do not do yet
- full rollout across all agents
- broad shared-memory default
- social/personal/technical memory blending
- claiming the pilot is already fully proven

## Practical next stance
- keep AgentMemory running
- keep the pilot scoped to technical continuity use
- treat memory as advisory, not authority
- expand only if more follow-up tasks continue to show clean recall

## Final summary
CodeGraph is a keeper for real code repos.
AgentMemory is now promising enough to continue, but only under narrow guardrails.
