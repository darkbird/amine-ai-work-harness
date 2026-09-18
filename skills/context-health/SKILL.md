---
name: context-health
description: "Audit durable project memory for missing, stale, conflicting, unsupported, or risky context by comparing it with current project evidence."
---

# Context Health

## Purpose

Check whether `_project-context/` still reflects the real project.

This skill diagnoses memory quality. It does not repair application code and is read-only by default.

## Use when

- durable memory may be stale
- implementation changed outside the normal handoff flow
- a project has been inactive and is being resumed
- another agent reports contradictory state
- before a major handoff, delivery, or audit
- after importing or bootstrapping old project context

## Read first

Use bounded reading:

1. `PROJECT.md`
2. `STATE.md`
3. active entries in `DECISIONS.md`
4. recent worklogs
5. `BACKLOG.md`

Then inspect only the implementation, Git evidence, docs, tests, or configs needed to verify material claims.

If Git is unavailable, record that fact instead of treating it as an error.

## Finding classes

Use these labels:

- `HEALTHY` — durable context is supported by current evidence
- `MISSING` — important durable context is absent
- `STALE` — context was once plausible but is no longer current
- `CONFLICT` — durable sources disagree with each other
- `DRIFT` — current implementation differs from the recorded intended state
- `UNVERIFIED` — a material claim lacks enough evidence
- `ORPHANED` — backlog, decision, reference, or state item no longer has an active referent
- `SECRET_RISK` — durable memory appears to contain credentials or sensitive secret material

Do not produce a numeric health score.

## Checks

Evaluate only what evidence supports.

### Structure
- expected durable files exist
- required STATE sections are present
- dates and references are usable

### Project identity
- purpose, scope, stack, architecture, and environments still match the workspace

### Current state
- completed items are actually present or otherwise evidenced
- in-progress items still exist
- blockers are still active
- next actions have not already been completed

### Decisions
- active decisions are not contradicted by newer active decisions
- superseded or reversed decisions are marked
- implementation drift is identified without silently rewriting history

### Backlog
- completed items are not still presented as open
- obsolete items are marked
- dependencies still make sense

### Worklogs
- recent material work is represented in STATE
- worklogs do not claim verification that cannot be reproduced or evidenced

### Safety
- no passwords, API keys, tokens, cookies, private keys, or credentials are stored
- sensitive client information is not copied unnecessarily

## Procedure

1. Reconstruct the durable-memory claims.
2. Select the minimum external evidence needed to verify them.
3. Compare memory to evidence.
4. Record only material findings.
5. Separate confirmed findings from unresolved questions.
6. Recommend the smallest safe memory correction.
7. Do not modify durable memory unless the user explicitly asks for repair.

## Optional persisted report

Only when asked to save the audit, write:

`_project-context/audits/YYYY-MM-DD-context-health.md`

Use:

```markdown
# Context Health — YYYY-MM-DD

## Summary
## Findings
### [CLASS] Title
Claim:
Evidence:
Impact:
Recommended memory correction:

## Unresolved questions
## Sources inspected
```

## Repair mode

If the user explicitly asks to repair context:

- update only `_project-context/`
- preserve decision history
- do not convert uncertainty into fact
- avoid stylistic rewrites
- add a worklog entry for material corrections
- never modify application source as part of context repair

## Final report

Return:

```text
Healthy:
Findings:
Highest-priority correction:
Unresolved:
Files changed: none
```

Change the final line only when explicit repair or report persistence was requested.

## Completion criterion

The user can tell which durable-memory claims are trustworthy, which need correction, and what smallest action will restore reliable project continuity.
