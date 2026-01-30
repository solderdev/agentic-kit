# Agent Instructions (Read First)

This repository is a lean template for **agentic, spec-driven changes**.

## Read Order
1) `AGENTS.md`: these rules
2) `docs/index.md`: repo map
3) `docs/design.md`: general design document
4) Any relevant files under `docs/records/` (especially the latest relevant records)

## How Changes/Extensions Work (Records)
Use **records** as the contract between programmer and an agent for non-trivial changes:
1) Create a new file: `docs/records/NNNN-short-slug.md` using `docs/records/TEMPLATE.md` (`status: proposed`).
  - Keep the record small, concrete, and testable.
2) Get feedback and approval from the programmer (you).
  - Update the record to `status: accepted` (spec approved).
3) Implement the change.
4) Finalize record: Update the record status to `done` (implemented + verified) and fill in **Verification** (exact commands run / results).

### Record Rules
- Record IDs are chronological and numbered; use the next available `NNNN`.
- Do not delete or rewrite `done` records; if something changes later, add a new record (next `NNNN`) that `supersedes:` the old one.
- Prefer explicit, testable acceptance criteria over broad narratives.

## Change Discipline
- Keep diffs minimal; avoid opportunistic refactors.
- If you must make a structural/architecture change, capture the "why" in the record.
- If a change affects architecture/boundaries/invariants, update `docs/design.md`.
- Don’t add new dependencies unless the record explicitly calls for it (and note the tradeoff).
- Make sure logging and code comments are clear and concise.

## Rules
- never use git for commits or similar. git commands are read only!
- do not hard-code any secrets
