# Record Guidelines

This document describes the requirements for an execution plan ("Record"), a design document that a coding agent can follow to deliver a working feature or system change.

## Status Semantics (Required)
- `proposed`: drafted, not approved
- `accepted`: spec approved (only after explicit approval)
- `done`: implemented + verified (Verification section filled)

Allowed transitions: `proposed → accepted → done` (no skipping).

## Record Workflow
1) Create a new file: `.agents/records/<branch>/<id>-short-slug.md` using `.agents/records/TEMPLATE.md` (`status: proposed`).
  - Keep the Record small, concrete, and testable.
2) Get feedback and approval from the programmer (you).
  - Update the Record to `status: accepted` (spec approved).
3) Implement the change. Update `.agents/DESIGN.md` if necessary.
4) Finalize Record: Update the Record status to `done` (implemented + verified) and fill in **Verification** (exact commands run / results).

## Record Rules
- Records are stored under a branch-scoped directory: `.agents/records/<branch>/...`.
  - `<branch>` is derived from the current git branch name, but sanitized for directory safety (e.g. `/` becomes `_`).
- Record IDs are time-sortable and filesystem-safe: UTC timestamps in `YYYYMMDDTHHMMSSZ` format (example: `20260204T110750Z`).
  - If a filename already exists, use the next second (`...51Z`, `...52Z`, etc.).
- Filename convention: `.agents/records/<branch>/<id>-short-slug.md`.
  - `<branch>` is a directory-safe form of the git branch name (unsafe characters become `_`).
  - `<id>` is a UTC timestamp in `YYYYMMDDTHHMMSSZ` format.
- Subtopics in `.agents/records/TEMPLATE.md` are proposed defaults and may be changed, removed, or added as needed.
- Do not delete or rewrite `done` Records; if something changes later, add a new Record that `supersedes:` the old one.
- If a change can be split up in multiple Records do it. Focus on smaller tasks.
- Prefer explicit, testable acceptance criteria over broad narratives.
- Records are considered a living memory of the project development and agents should consult old records.
- When authoring a Record, follow RECORDS.md _to the letter_. If it is not in your context, refresh your memory by reading the entire RECORDS.md file. Be thorough in reading (and re-reading) source material to produce an accurate specification. When creating a spec, start from the skeleton and flesh it out as you do your research.
- Every Record is a living document. Contributors are required to revise it as progress is made, as discoveries occur, and as design decisions are finalized.
