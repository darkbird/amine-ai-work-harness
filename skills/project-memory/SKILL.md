---
name: project-memory
description: Maintain durable project context across sessions using source-of-truth files for project identity, current state, decisions, backlog, and work history.
---

# Project Memory

## Purpose

Keep project continuity independent from any single conversation.

Chat history is working memory. Project files are durable memory.

## Use when

- starting or resuming an existing initialized workspace
- the user asks where the project stands
- context is fragmented or contradictory
- a milestone or durable decision must be persisted
- another skill needs reliable current project state

If durable context is absent or only placeholder-level, use `workspace-bootstrap` first.

If durable context exists but may be stale or contradictory, use `context-health` before rewriting it.

## Durable context

Prefer:

```text
_project-context/
├── PROJECT.md
├── STATE.md
├── DECISIONS.md
├── BACKLOG.md
├── worklog/
├── proof-of-work/
└── commercial/
```

## Source priority

Read in this order:

1. `PROJECT.md`
2. `STATE.md`
3. `DECISIONS.md`
4. recent `worklog/*.md`
5. `BACKLOG.md`
6. relevant project documentation
7. Git history/diffs when useful
8. current implementation
9. conversation history as supporting context only

When sources conflict:
- prefer a newer explicit active decision over older notes
- prefer implementation evidence for implementation state
- do not guess when the conflict remains unresolved
- flag unresolved contradictions

## PROJECT.md

Store slow-changing facts only:
- project purpose
- client/product
- audience
- scope
- success criteria
- constraints
- stack
- architecture
- environments and URLs
- authoritative references

## STATE.md

Answers: "Where are we now?"

Required sections:

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
```

Only verified completed work belongs in `Completed`.

## DECISIONS.md

Record decisions future agents must respect:

```markdown
## YYYY-MM-DD — Decision title

Decision:
Reason:
Supersedes:
Status: Active | Superseded | Reversed
```

Never silently rewrite decision history.

## BACKLOG.md

Keep unresolved work separate from current-state prose.

Useful fields:
- item
- status
- dependency
- source/reason
- next action

## Resume procedure

1. Read durable context.
2. Inspect additional evidence only where gaps exist.
3. Return current objective, confirmed progress, blockers, and next executable action.
4. Distinguish facts from assumptions.
5. Do not modify application source unless implementation was explicitly requested.

## Consolidation procedure

1. Identify new verified facts.
2. Update STATE.md.
3. Append durable decisions.
4. Update backlog statuses.
5. Add a dated worklog when meaningful work occurred.
6. Avoid unnecessary duplication.

## Secret handling

Never store passwords, API keys, tokens, cookies, or private credentials.

## Completion criterion

A fresh agent can understand the project, current state, decisions, blockers, and next action without reading the full chat.
