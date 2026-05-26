# AgentMemory Pilot Plan

## Purpose
Test whether AgentMemory can create real cross-session continuity for coding and agent work without creating memory pollution, stale retrieval, or false authority.

This should be treated as a controlled pilot, not an automatic new default.

## Why this matters
The upside is large:
- less repeated explanation
- more continuity across coding sessions
- shared technical memory across agent surfaces
- reduced context-window waste

The downside is also large:
- persistent bad memory
- retrieval of stale decisions
- cross-agent contamination
- false confidence from remembered but wrong context

## Pilot decision
Do not roll this out broadly first.

Start with a narrow, deliberate pilot on one or two active coding lanes where continuity matters and where bad retrieval would be noticeable quickly.

## Recommended pilot scope
### Include first
- technical project memory only
- architecture decisions
- implementation rationale
- bug root causes
- prior fix history
- repo-specific preferences
- task continuity across multiple coding sessions

### Exclude first
- personal memory
- social/chat memory
- broad life/admin memory
- vague opinions without clear project value
- temporary hypotheses
- anything sensitive unless the storage/retrieval path is understood clearly

## Best pilot targets
### Good first targets
1. active app/code repos with recurring sessions
2. projects where the same architecture gets re-explained often
3. repos where prior bug context matters over time

### Bad first targets
1. noisy social/chat channels
2. broad all-project memory ingestion
3. mixed personal + technical memory pools
4. passive auto-capture everywhere without review

## Guardrails
### Guardrail 1: narrow domain first
Use one or two project lanes only. Do not let it ingest everything.

### Guardrail 2: memory types must be explicit
Prefer memories that can be evaluated as true/false/useful/not useful.

### Guardrail 3: retrieval quality decides the outcome
The pilot should pass only if retrieval is consistently helpful and low-noise.

### Guardrail 4: remembered context is advisory, not authority
AgentMemory should not outrank direct file checks, current repo state, or live verification.

### Guardrail 5: stale memory must be easy to detect and remove
A memory system without clean correction/deletion workflow is dangerous.

## What success looks like
- noticeably less repeated explanation
- helpful recall of prior architecture and fix context
- low junk retrieval
- low contradiction with current repo state
- enough trust that using it feels faster, not riskier

## What failure looks like
- wrong old decisions resurfacing as current truth
- noisy or irrelevant recall
- ambiguous memories crowding useful ones out
- the agent becoming more confident but less accurate
- extra complexity with little real continuity gain

## Pilot evaluation questions
1. Did it save real time?
2. Did it reduce repeated explanation?
3. Did it retrieve the right past context at the right time?
4. Did it surface stale or wrong context?
5. Did it create confusion between projects or agents?
6. Was correction/removal straightforward?
7. Did trust go up or down after a week of use?

## Proposed implementation sequence
### Phase 1 - design
- choose one target repo/workflow
- define allowed memory categories
- define disallowed memory categories
- define evaluation questions and rollback criteria

### Phase 2 - controlled install
- install AgentMemory locally
- connect only the chosen agent surfaces
- keep the blast radius small

### Phase 3 - observed usage
- use it in real work for a limited period
- capture examples of good recall and bad recall
- evaluate whether it is helping enough to expand

### Phase 4 - decision
- expand
- keep narrow
- or remove

## Recommended first pilot target
### Chosen pilot target
`/Users/gibby.ai/.openclaw/workspace/first-client-engine/product`

### Why this target
- real code repo
- recurring architecture/context value
- wrong retrieval should become obvious quickly
- good fit for technical continuity memory
- lower risk than turning memory on across broader mixed contexts

## Pilot rules for this target
### Allowed memory categories
- module/function responsibilities
- storage/data-flow notes
- bug root causes
- implementation decisions
- recurring workflow context

### Disallowed memory categories
- personal/user memory
- broad non-technical conversation memory
- speculative product strategy unless explicitly grounded
- temporary guesses presented as facts

## Current recommendation
### Recommendation
Test AgentMemory next as a narrow technical continuity pilot on `first-client-engine/product`.

### Not recommended yet
- full shared-memory default across all agents
- all-project ingestion
- chat + personal + technical memory blending
- wiring OpenClaw broadly before the coding-lane pilot proves clean

## Decision rule
AgentMemory earns broader rollout only if it proves:
- high-value recall
- low contamination
- easy correction
- clear time savings in real work

If not, it should remain experimental or be removed.
