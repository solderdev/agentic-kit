# Doc-Gardening Checklist

Use this checklist selectively based on scope. Run only relevant checks and keep diffs small.

## 1) Structural Integrity

- Confirm entry docs exist and are reachable from the primary map/index.
- Confirm major docs are cross-linked, not isolated.
- Confirm templates do not leak unresolved placeholders into active docs.

Useful commands:

```bash
rg -n "TODO:|\\[TODO|TBD" AGENTS.md .agents skills README.md
rg --files .agents skills
```

## 2) Link Health

- Check Markdown links in changed docs and resolve broken relative paths.
- Check references to non-existent files, moved files, or stale anchors.

Useful commands:

```bash
rg -n "\\[[^\\]]+\\]\\(([^)]+)\\)" AGENTS.md .agents skills README.md
```

Validation rule:
- For each referenced local path, verify the file exists in the repo.

## 3) Record Hygiene

- Check record status values are valid (`proposed`, `accepted`, `done`).
- Check status flow is respected for active work.
- Check every `done` record includes non-empty verification notes.
- Check filenames follow timestamp + slug convention and branch-scoped path rules.

Useful commands:

```bash
rg -n "^- status: " .agents/records
rg -n "^\\*\\*Verification:\\*\\*$|^- $" .agents/records
find .agents/records -type f | sort
```

## 4) Design/Instruction Consistency

- Check `AGENTS.md` stays concise and points to deeper sources instead of duplicating them.
- Check `.agents/INDEX.md` matches real directories and files.
- Check `.agents/DESIGN.md` reflects architectural boundaries and invariants when behavior changes.

Heuristic:
- If a doc claims behavior that cannot be found in code or records, flag as contradiction.

## 5) Freshness Signals

- Check for stale dates, abandoned TODOs, or sections marked complete without verification.
- Check whether ownership/review metadata exists when your team policy requires it.
- Prefer adding lightweight freshness markers only where useful; avoid metadata bloat.

## 6) Reporting Format

When finishing a gardening pass, report:

- Findings by severity with file references.
- Changes made (if any).
- Verification commands and outcomes.
- Deferred items requiring separate records.
