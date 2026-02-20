---
name: doc-gardening
description: Audit and maintain repository documentation used by coding agents, including instruction maps, design docs, and execution records. Use when asked to clean up docs, check for stale or contradictory guidance, fix broken links or missing cross-references, enforce record status hygiene, or prepare small doc-gardening pull requests.
---

# Doc Gardening

## Overview

Run a repeatable documentation health workflow with small, verifiable edits. Keep agent instructions concise, cross-linked, and aligned with real repository behavior.

## Workflow

1. Define scope first.
- Identify which doc surfaces are in scope: `AGENTS.md`, `.agents/*`, feature docs, and templates.
- Confirm whether the task is audit-only or audit-plus-fix.

2. Build a quick map.
- Start from the repo map/index file, then walk outward to referenced files.
- Prefer progressive disclosure: load only files needed for the current check.

3. Run the checklist.
- Use `references/checklist.md` and run relevant checks only.
- Capture findings with severity and direct file references.

4. Apply minimal fixes.
- Prefer smallest diffs that restore correctness and navigability.
- Avoid broad rewrites unless explicitly requested.

5. Verify and summarize.
- Re-run relevant checks after edits.
- Report exactly what changed, what was verified, and remaining gaps.

## Output Contract

When producing results, include:
- `Findings`: ordered by severity with file references.
- `Changes`: list of docs updated.
- `Verification`: exact commands run and outcomes.
- `Follow-ups`: unresolved risks or deferred cleanup.

## Guardrails

- Keep `AGENTS.md` short and map-like; move heavy detail to deeper docs.
- Preserve historical records; never rewrite completed history to hide drift.
- Prefer explicit acceptance criteria and verification notes over prose.
- Do not invent architecture details not present in code or approved records.
- Flag contradictions explicitly when docs and code disagree.

## Reference

Use `references/checklist.md` as the primary audit checklist.
