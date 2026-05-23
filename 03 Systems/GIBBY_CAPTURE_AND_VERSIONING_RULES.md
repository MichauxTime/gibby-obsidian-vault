# Gibby Capture and Versioning Rules

## Core rule
Ben should not have to remind Gibby to preserve important work.

Default expectation:
- **Knowledge changes** -> write to Obsidian
- **Code changes** -> commit to GitHub
- **Process changes** -> update system docs

## What must go to Obsidian by default
- project status changes
- architecture decisions
- launch checklists
- research findings worth reusing
- bugs/root causes
- deployment notes
- blockers and caveats
- naming decisions
- content strategy decisions
- links/resources that change how Gibby should operate

## What must go to GitHub by default
- any source code change
- config changes inside a tracked repo
- UI/CSS/HTML/JS/Python changes in a tracked repo
- automation scripts that belong to a repo
- docs that are part of a repo's working history

## What does NOT belong only in chat
- final decisions
- root-cause findings
- new operating rules
- project structure changes
- reusable commands/workflows
- anything Ben is likely to need again later

## Minimum closeout after meaningful work
1. verify the actual result
2. write the durable note
3. commit code if code changed
4. mention any remaining blocker clearly

## Failure mode to avoid
"I fixed it but didn’t document it" and "I changed code but only if Ben explicitly asked for a commit."

That is no longer acceptable as the default.
