# Agent Instructions (Read First)

This repository is a lean template for **agentic, spec-driven changes**.

## TL;DR
For non-trivial changes, follow the Records workflow below: create record → get approval → implement → verify → mark `done`.

## Read Order
1) `AGENTS.md`: these rules
2) `.agents/INDEX.md`: repo map
3) `.agents/RECORDS.md`: change records (specs, decisions, work plans)
4) other files and locations can be found in the repo map.

## How Changes/Extensions Work (Record)
CRITICAL: When writing new features or significant refactors or fixes, use a **Record** (as described in .agents/RECORDS.md) from design to implementation.

## Change Discipline
- Default to the smallest possible diff; avoid opportunistic refactors.
- If a change affects architecture/boundaries/invariants/entry points, update `.agents/DESIGN.md`.
- Don’t add new dependencies unless the record explicitly calls for it (and note the tradeoff).
- Keep logging and code comments clear and concise.
- Choose the smallest change that satisfies the acceptance criteria; avoid new abstractions unless required for the current scope.

## Small-Slice Rule (Required)
- Prefer new small module/function over expanding large files.
- One Record should target one behavior change.
- If implementation spans multiple concerns, stop and split into multiple Records.

## Rules
- Git is read-only for the agent.
  - Allowed: `git status`, `git diff`, `git log`, `git show`, `git blame`
  - Not allowed: `git commit`, `git add`, `git push`, `git reset`, `git rebase`, `git checkout`, `git tag`
- keep secrets separate from the code

## Useful Commands
- Build: `xxx`
