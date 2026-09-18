---
name: project-auditor
description: Compare active plans, requirements, decisions, current state, and implementation to detect missing work, drift, regressions, obsolete behavior, and unsupported additions.
---

# Project Auditor

## Purpose

Detect divergence between what the project is supposed to be and what it currently is.

Read-only by default.

## Sources

Prefer:
1. PROJECT.md
2. STATE.md
3. DECISIONS.md
4. BACKLOG.md
5. active brief/specification
6. implementation
7. tests/builds
8. Git history when useful

## Finding classes

- `MATCH`
- `MISSING`
- `DRIFT`
- `REGRESSION`
- `UNPLANNED`
- `OBSOLETE`
- `UNCLEAR`
- `BLOCKED`

## Procedure

1. Reconstruct active requirements.
2. Resolve superseded decisions.
3. Inspect current implementation.
4. Compare requirement by requirement.
5. Record evidence for every non-trivial finding.
6. Separate confirmed findings from suspicions.
7. Do not fix anything unless explicitly asked in a separate implementation task.

## Output

`_project-context/audits/YYYY-MM-DD-project-audit.md`

Do not silently reinterpret ambiguous requirements.
