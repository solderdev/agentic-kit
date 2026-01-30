# 0001: Adopt Records For Spec-Driven Changes

type: decision
status: done
date: 2026-01-30 18:00:00

## Decision
Use `docs/records/` as the single place to capture change specs and durable decisions, committed alongside code changes.

## Rationale
- Keeps agent work anchored to a concrete, testable contract (acceptance criteria).
- Preserves “why” and constraints over time without introducing a full ticket/PR workflow.
- Makes Git history easier to scan (record + implementation together).

## Consequences
- Non-trivial changes should start with a new record based on `docs/records/TEMPLATE.md`.
- `done` records should not be rewritten; later changes should supersede via a new record.
