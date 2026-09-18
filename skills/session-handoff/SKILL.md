---
name: session-handoff
description: Close substantial work sessions with an evidence-based handoff that updates state, decisions, backlog, and worklogs so a new session can resume immediately.
---

# Session Handoff

## Purpose

Make the next session start from durable state rather than the previous conversation.

Follow `project-memory`.

## Use when

- ending a substantial session
- switching projects
- handing work to another agent
- an automation finishes meaningful work
- context is becoming long
- the user asks to save or consolidate the session

## Read first

Inspect:
1. STATE.md
2. DECISIONS.md
3. BACKLOG.md
4. relevant current-session changes
5. Git status/diff when relevant

## Classify outcomes

Separate:
- discussed
- decided
- attempted
- implemented
- verified
- blocked
- deferred

Never present discussed or attempted work as completed.

## Worklog

Create or append:

`_project-context/worklog/YYYY-MM-DD.md`

Structure:

```markdown
# Worklog — YYYY-MM-DD

## Session objective
## Work completed
## Files or areas changed
## Verification performed
## Decisions made
## Problems encountered
## Blockers
## Deferred / not completed
## Next recommended action
## Evidence
```

## Update durable context

After the worklog:
- update STATE.md
- add durable decisions
- update backlog statuses
- keep STATE.md compact
- preserve unresolved items

## Final handoff

Return:

```text
Completed:
Verified:
Blocked:
Next:
Context files updated:
```

Do not deploy, delete files, rewrite Git history, expose secrets, or fabricate completion.
