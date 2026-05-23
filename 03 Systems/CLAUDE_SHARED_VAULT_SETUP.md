# Claude Shared Vault Setup

## Goal
Let Claude and Gibby read/write the same Obsidian vault so project memory is shared.

## Vault path
`/Users/gibby.ai/.openclaw/workspace/obsidian`

## Setup
1. Open Claude with filesystem access to the workspace
2. Point Claude at the vault path above
3. Tell Claude this vault is the default durable knowledge layer
4. Tell Claude:
   - project notes, decisions, blockers, architecture, research -> write to Obsidian
   - source code changes -> still belong in GitHub

## Simple shared rules
- Do not casually rename top-level folders
- Do not delete notes without a clear reason
- Prefer updating existing project notes before creating duplicates
- Put quick messy captures in `00 Inbox`
- Put day logs in `01 Daily`
- Put project truth in `02 Projects`
- Put operating rules in `03 Systems`
- Put reusable templates/docs in `04 Reference`
- Put major choices in `05 Decisions`
- Put retros/audits in `06 Reviews`

## Human prompt to give Claude
"Use `/Users/gibby.ai/.openclaw/workspace/obsidian` as the shared project memory vault. Treat it as the default place for durable notes, decisions, blockers, architecture, and research. Keep code/version history in GitHub, not Obsidian. Prefer updating existing notes over creating duplicate ones."
