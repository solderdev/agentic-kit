# Agent Instructions (Read First)

This repository is a lean template for **agentic, spec-driven changes**.

## TL;DR
For non-trivial changes, follow the Records workflow below: create record → get approval → implement → verify → mark `done`.

## Read Order
1) `AGENTS.md`: these rules
2) `docs/index.md`: repo map
3) `docs/design.md`: general design document
4) Any relevant files under `docs/records/` (especially the latest relevant records)

## How Changes/Extensions Work (Records)
Use **records** as the contract between programmer and an agent for non-trivial changes.

### Status Semantics (Required)
- `proposed`: drafted, not approved
- `accepted`: spec approved (only after explicit approval)
- `done`: implemented + verified (Verification section filled)

Allowed transitions: `proposed → accepted → done` (no skipping).

### Workflow
1) Create a new file: `docs/records/<branch>/<id>-short-slug.md` using `docs/records/TEMPLATE.md` (`status: proposed`).
  - Keep the record small, concrete, and testable.
2) Get feedback and approval from the programmer (you).
  - Update the record to `status: accepted` (spec approved).
3) Implement the change.
4) Finalize record: Update the record status to `done` (implemented + verified) and fill in **Verification** (exact commands run / results).

### Record Rules
- Records are stored under a branch-scoped directory: `docs/records/<branch>/...`.
  - `<branch>` is derived from the current git branch name, but sanitized for directory safety (e.g. `/` becomes `_`).
- Record IDs are time-sortable and filesystem-safe: UTC timestamps in `YYYYMMDDTHHMMSSZ` format (example: `20260204T110750Z`).
  - If a filename already exists, use the next second (`...51Z`, `...52Z`, etc.).
- Do not delete or rewrite `done` records; if something changes later, add a new record that `supersedes:` the old one.
- Prefer explicit, testable acceptance criteria over broad narratives.

## Change Discipline
- Default to the smallest possible diff; avoid opportunistic refactors.
- If a change affects architecture/boundaries/invariants/entry points, update `docs/design.md`.
- Don’t add new dependencies unless the record explicitly calls for it (and note the tradeoff).
- Keep logging and code comments clear and concise.

## Rules
- Git is read-only for the agent.
  - Allowed: `git status`, `git diff`, `git log`, `git show`, `git blame`
  - Not allowed: `git commit`, `git add`, `git push`, `git reset`, `git rebase`, `git checkout`, `git tag`
- do not hard-code any secrets

## Useful Commands
- Build: `xxx`
