# Repo Map

This page is a navigation aid: where things live and where to look first.

## Start Here
- `AGENTS.md`: agent rules + workflow (read first)
- `.agents/RECORDS.md`: change records (specs, decisions, work plans)
- `.agents/DESIGN.md`: high-level design, boundaries, invariants

## Change Records
- `.agents/records/`: records (specs + durable decisions)
  - `.agents/records/<branch>/`: branch-scoped records (`<branch>` is a directory-safe form of the git branch name)
  - `.agents/records/TEMPLATE.md`: template for new records

## Skills
- `skills/`: repository-local reusable skills (check here before external skill search)
  - `skills/doc-gardening/SKILL.md`: workflow for documentation health checks and small doc-fix passes

## Project Files
- `README.md`: minimal human overview
- `src/`: contains source code
