---
date: 2026-07-06
status: active
tags:
  - gibby-system
  - model-fallbacks
  - reliability
---

# AI Runtime Fallback Audit - 2026-07-06

Ben flagged that work had been stuck for roughly two days because Anthropic and Codex hit caps and the fallback paths were not configured properly. This is a repeat failure class, not a one-off quota annoyance.

## Decision

The model-match fallback rule remains global: every model-backed workflow needs an explicit fallback ladder, visible degraded state, and a recovery path when primary providers return. This applies to interactive agents, crons, image generation, voice, review agents, and browser/workflow automation.

Related: [[Model-Match Fallback Ladder]] if/when promoted into the vault.

## Audit Command

Run from the workspace:

```bash
python3 ops/model_fallback_audit.py --json
```

The first run on 2026-07-06 returned 4 findings:

- Critical: `agents.list.codex-thread` is an ACP Codex runtime with no OpenClaw-visible fallback ladder.
- High: `agents.defaults.imageModel` uses `openai/gpt-image-2` with an empty fallback list.
- High: `openclaw cron list --json` fails because the CLI rejects `~/.openclaw/openclaw.json` as invalid, which weakens shell-based recovery.
- Medium: `cron-map.html` has 25 cap-sensitive model rows with no fallback metadata.

## Repair Order

1. Fix CLI recovery first so shell/cron repair remains available even when chat surfaces are capped.
2. Add or route around the `codex-thread` no-fallback ACP path so interactive Discord work can fall back to local/Claude/OpenAI alternatives deliberately.
3. Add structured fallback metadata to cron payloads or to the cron inventory generator, then audit/update high-impact crons first.
4. Add an image-generation fallback or a clear degraded/manual queue path for image jobs.
5. Wire `ops/model_fallback_audit.py` into a daily/heartbeat guard so no-fallback routes become visible before caps burn a day.

Daily guard registered: OpenClaw cron `ai-runtime-fallback-audit` (`60313b85-6f72-43c2-a728-ebfe3d0ceec2`), 8:05 AM ET, local model `ollama/qwen3-coder:30b`, normal delivery quiet.

## Notes

- Do not "solve" this by hardcoding direct OpenAI/Anthropic API keys. Use subscription-backed routes, local models, or explicit degraded paths.
- Local Qwen/Ollama can be primary for bounded background work, but user-facing quality changes must be visible.
- A fallback that merely returns weak text does not count. It must meet the workflow's quality and latency floor.
