---
name: workspace-bootstrap
description: "Initialize durable project memory for a workspace from verified local evidence without modifying application source code or overwriting existing context."
---

# Workspace Bootstrap

## Purpose

Initialize `_project-context/` so a fresh agent can understand and resume a project without relying on chat history.

This skill is for discovery and initialization. After bootstrap, `project-memory` becomes the normal continuity skill.

## Use when

- opening a workspace that has no durable project memory
- adopting an existing codebase or project folder
- project context exists only in scattered docs or implementation
- the user asks to initialize, onboard, map, or bootstrap a workspace

## Safety boundary

By default, write only inside `_project-context/`.

Do not:
- modify application source code
- change dependencies
- deploy or publish
- alter databases
- rewrite Git history
- create commits unless explicitly requested
- store passwords, API keys, tokens, cookies, private keys, or credentials
- infer client facts, metrics, outcomes, or business impact without evidence

## First check

Before scanning broadly:

1. Check whether `_project-context/` exists.
2. If it contains meaningful `PROJECT.md` and `STATE.md`, do not rebuild it.
3. In an existing initialized project, switch to `project-memory` for normal recovery or `context-health` for consistency checking.
4. Create only missing durable-memory files when safe.

## Evidence scan

Use the smallest evidence set that can establish the project accurately.

Prefer:

1. workspace root and project markers
2. README and project documentation
3. dependency/runtime manifests and lockfiles
4. framework/build configuration
5. Git status, remote, branch, and relevant recent history when Git is available
6. application entry points and high-level architecture
7. routes, schemas, models, or CMS structures when materially relevant
8. test configuration and recent test evidence when available
9. deployment/environment configuration without secret values
10. existing project notes

Do not read the entire codebase when a bounded sample establishes the same fact.

## Evidence classes

For every material fact, internally classify it as:

- `Verified` — directly supported by inspected evidence
- `Unresolved` — important but not established
- `Conflict` — sources disagree and the discrepancy is not resolved

Do not persist assumptions as facts.

## Files to initialize

Create this durable structure when absent:

```text
_project-context/
├── PROJECT.md
├── STATE.md
├── DECISIONS.md
├── BACKLOG.md
└── worklog/
```

Optional directories such as `proof-of-work/`, `commercial/`, and `audits/` may be created only when another skill needs them.

## PROJECT.md

Store slow-changing verified facts:

- project purpose
- product/client only when evidenced
- target users or audience
- scope
- success criteria when documented
- constraints
- stack and versions when discoverable
- architecture
- environments and public/local URLs
- authoritative references

Add an `Unresolved` section for important unknowns rather than guessing.

## STATE.md

Use:

```markdown
# Current State

Last updated: YYYY-MM-DD

## Current objective
## Completed
## In progress
## Blocked
## Next actions
## Known issues
## Important references
## Unresolved
```

Only verified completed work belongs in `Completed`.

## DECISIONS.md

Initialize the file even if no durable decisions can be reconstructed.

Only record a historical decision when evidence clearly establishes:
- what was decided
- why or from what source
- whether it is still active

Never manufacture a reason from implementation alone.

## BACKLOG.md

Capture unresolved work only when supported by:
- explicit TODO/backlog/spec text
- failing tests or errors
- documented missing requirements
- current state evidence

Do not convert every possible improvement into backlog.

## Bootstrap worklog

Create `_project-context/worklog/YYYY-MM-DD-bootstrap.md` with:

```markdown
# Bootstrap Worklog — YYYY-MM-DD

## Sources inspected
## Verified project facts
## Files initialized
## Conflicts found
## Unresolved information
## Verification performed
## Recommended next action
```

## Idempotency

A second run must not reset the project memory.

When files already exist:
- preserve existing durable facts
- fill only clearly missing structure
- do not duplicate decisions or backlog items
- do not replace user-authored wording merely for style
- report a no-op when no safe bootstrap change is needed

## Final report

Return:

```text
Project:
Stack:
Verified state:
Files created:
Files updated:
Conflicts:
Unresolved:
Next action:
```

## Completion criterion

A new session can load `project-memory` and understand the project purpose, verified current state, blockers, and next executable action without using previous chat history.
