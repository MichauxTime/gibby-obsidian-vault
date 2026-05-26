# AI Agent Tool Adoption Plan - 12-Factor, AgentMemory, CodeGraph, Supertonic

## Purpose
Adopt the strongest pieces of four promising agent/tooling projects without turning Gibby into a pile of hype-driven abstractions.

The four selected projects are:
- 12-factor-agents
- agentmemory
- codegraph
- supertonic

## Core decision
Adopt them in this order:
1. 12-factor-agents as operating doctrine
2. codegraph as the first implementation test
3. agentmemory as a careful continuity experiment
4. supertonic as an optional local voice layer

## Why this order
- 12-factor-agents helps decide how to build agent systems well
- codegraph has the clearest immediate practical upside with relatively low risk
- agentmemory could become extremely valuable, but bad memory is dangerous
- supertonic is useful, but less central unless voice becomes an active product/system need

## 1) 12-factor-agents adoption plan
### What to adopt
- own prompts
- own context window
- keep tools structured and explicit
- unify execution state and business state where possible
- pause/resume cleanly
- contact humans intentionally
- own control flow instead of over-trusting generic frameworks
- keep agents small and focused
- prefer stateless reducer thinking where useful

### What not to cargo-cult
- do not import the doctrine wholesale just because it sounds correct
- do not add complexity where deterministic code is enough
- do not create multi-agent structure where a simple workflow is better
- do not use “agentic” language to justify weak product design

### Implementation target inside Gibby/OpenClaw
- promote the useful pieces into AGENTS.md / operating rules / project design docs
- use it as a review lens for new agent workflows
- use it especially for pause/resume, human escalation, and state/control design

### Success criteria
- better agent workflow design decisions
- fewer brittle “prompt + tools + hope” implementations
- cleaner distinction between deterministic logic and model judgment

## 2) codegraph adoption plan
### Why it is first
It offers the highest-confidence immediate win for coding-agent work:
- faster codebase understanding
- fewer token-hungry explore loops
- better impact analysis before edits
- local-only, no API dependency

### Intended uses
- large repo orientation
- architecture Q&A in real repos
- pre-edit impact tracing
- route/handler understanding in app repos
- affected-test discovery

### Risks
- stale or incomplete graph could mislead the agent
- limited value on small repos
- usefulness depends on whether the agent actually uses the tools correctly

### Guardrails
- test on real repos before trusting it broadly
- prefer it as an accelerator, not as a replacement for reading critical code
- verify whether answers improve in speed/cost/clarity rather than assuming they do

### Implementation target
- install locally on Mac mini
- connect to relevant coding-agent surfaces
- test first on one medium/large repo that actually matters

### Success criteria
- lower repo exploration friction
- materially better repo answers from coding agents
- clear evidence that it saves time/tokens/tool churn

## 3) agentmemory adoption plan
### Why it matters
This is the strongest candidate for shared agent continuity across sessions and tools.

### Intended uses
- preserve technical project memory
- remember architecture decisions and prior fixes
- reduce re-explaining across coding sessions
- support cross-agent continuity where that continuity is actually helpful

### Main concerns
- memory pollution
- false or stale memory retrieval
- cross-agent contamination
- hidden complexity in tuning consolidation / decay / recall behavior

### Guardrails
- start in a controlled test scope
- define what kinds of memory are allowed vs undesirable
- treat retrieval quality as the make-or-break metric
- do not let it silently become a source of hallucinated authority

### Implementation target
- sandboxed/shared-memory pilot before broad rollout
- ideally test against active coding/project continuity needs, not toy examples

### Success criteria
- real reduction in repeated setup/context explanation
- high-value recall with low junk retrieval
- no major trust loss from incorrect memory injection

## 4) supertonic adoption plan
### Why it matters
It could become the best local no-API voice layer for assistant workflows or products.

### Intended uses
- local assistant TTS
- private/offline voice output
- cheap internal narration
- possible product-level accessibility or read-aloud features

### Main concerns
- voice quality may be “good local model” rather than truly great
- multilingual quality likely varies
- operational setup is non-trivial versus managed cloud APIs

### Guardrails
- judge by ear, not by README claims
- test real use cases, not just one demo sentence
- do not ship it into customer-facing experiences unless quality genuinely clears the bar

### Implementation target
- local evaluation first
- keep only if it is clearly good enough

### Success criteria
- strong enough quality for real repeated use
- low operational pain
- meaningful value from staying local/offline

## Recommended execution sequence
### Phase 1
- write this plan into the shared Obsidian vault
- install and test codegraph

### Phase 2
- extract 12-factor-agent principles into Gibby operating/design docs
- begin agentmemory pilot design

### Phase 3
- run agentmemory pilot
- evaluate supertonic if voice becomes active priority

## Practical decision labels
- 12-factor-agents → adopt conceptually now
- codegraph → implement and test now
- agentmemory → test carefully next
- supertonic → evaluate opportunistically

## Current recommendation
If only one implementation happens immediately, it should be codegraph.

If only one conceptual shift happens immediately, it should be using 12-factor-agents as a design filter rather than a framework choice.

## Note for future Gibby/Claude
Do not treat any of these as mandatory stack defaults just because they looked promising once. Re-earn trust through live use.
