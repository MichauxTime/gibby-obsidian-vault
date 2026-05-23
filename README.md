# Gibby Obsidian Vault

This vault is the durable knowledge layer for Ben + Gibby.

## Purpose
- Capture decisions, project state, architecture, ideas, blockers, and lessons
- Keep high-signal knowledge out of chat-only memory
- Complement GitHub, not replace it

## Relationship to GitHub
- **Obsidian** = knowledge, docs, reasoning, plans, project memory
- **GitHub** = source code, diffs, branches, commits, PRs, rollback
- Rule: if code changes, GitHub should be updated by default
- Rule: if understanding changes, Obsidian should be updated by default
- This vault is also its own Git repo for note/version history

## Top-level folders
- `00 Inbox` — quick capture
- `01 Daily` — day logs
- `02 Projects` — one folder per active project
- `03 Systems` — operating rules, workflows, infra, agent behavior
- `04 Reference` — reusable notes, snippets, vendors, links, docs, templates
- `05 Decisions` — important choices and why
- `06 Reviews` — audits, retros, postmortems
- `07 Scratch` — temporary working notes

## Starter templates
- `04 Reference/Daily Note Template.md`
- `04 Reference/Project Note Template.md`

## Default expectation
After meaningful work:
1. update the relevant project note in this vault
2. if code changed, commit/push to GitHub by default
3. if a workflow changed, update the rule in `03 Systems`

This vault exists so nothing important stays trapped in chat.

## Shared-agent use
This vault is intended to be shared across Gibby and Claude.

See:
- `03 Systems/CLAUDE_SHARED_VAULT_SETUP.md`
- `03 Systems/SHARED_VAULT_EDITING_RULES.md`
- `03 Systems/ALL_AGENTS_VAULT_RULE.md`
