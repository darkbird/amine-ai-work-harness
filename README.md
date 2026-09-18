# Amine AI Work Harness — v0.3.0

OpenWork-first Agent Plugin for durable project continuity, workspace bootstrap, context health, grounded implementation, audits, proof-of-work, commercial evidence, and cross-project professional memory.

## OpenWork installation path

Use the modern OpenWork Cloud / organization plugin flow, not the legacy desktop `From GitHub` compatibility importer.

Recommended path:

1. Connect GitHub as an OpenWork Source.
2. Select `darkbird/amine-ai-work-harness`.
3. Let OpenWork detect the root Agent Plugin manifest.
4. Import/publish the plugin to your organization Library or marketplace.
5. Grant access to yourself or the intended team.

The repository intentionally uses the root Agent Plugin manifest:

```text
plugin.json
skills/
```

There is no `.claude-plugin/` compatibility shim.

## Skills

1. `workspace-bootstrap`
2. `project-memory`
3. `session-handoff`
4. `context-health`
5. `technical-grounding`
6. `project-auditor`
7. `evidence-capture`
8. `proof-of-work`
9. `commercial-evidence`
10. `weekly-review`
11. `professional-memory`

## V0.3 continuity flow

```text
new or adopted workspace
        |
        v
workspace-bootstrap
        |
        v
_project-context/
        |
        +----> project-memory ----> resume work
        |
        +----> session-handoff ---> persist session state
        |
        +----> context-health ----> detect stale or conflicting memory
```

`workspace-bootstrap` is idempotent: it initializes missing durable memory from verified workspace evidence and must not rebuild a mature `_project-context/`.

`context-health` is read-only by default: it checks durable memory against current evidence and reports missing, stale, conflicting, drifted, unverified, orphaned, or secret-risk context without automatically rewriting it.

## Memory model

Each project owns its private durable memory:

```text
_project-context/
```

Cross-project professional evidence belongs in a separate private workspace:

```text
_professional-memory/
```

Do not centralize client secrets or confidential source material.

## Evidence rules

- Chat history is supporting context, not the primary project source of truth.
- Do not invent metrics, outcomes, implementation status, or Git evidence.
- If Git is unavailable, record that fact and continue.
- Only verified completed work belongs in durable completed state.
- Preserve decision history rather than silently rewriting it.
- Never store credentials or secret material in durable memory.

## Context7

Context7 is not bundled as a second MCP configuration.

`technical-grounding` uses it when already available in OpenWork/OpenCode.

## Recommended operating flow

```text
workspace-bootstrap
  -> project-memory
  -> project work
  -> session-handoff
  -> context-health
  -> evidence-capture
  -> proof-of-work
  -> professional-memory
  -> commercial-evidence
```

Not every skill runs every session. Use the smallest skill set needed for the task.

## Automation prompts

Ready-to-paste prompts are available under `automation-prompts/`.

Recommended cadence:
- new/adopted workspace: Workspace Bootstrap manually
- after substantial sessions: Context Consolidator
- periodic consistency check: Context Health Check
- before delivery: Project Audit
- Friday: Proof of Work Builder
- weekly: Professional Memory Sync
- Sunday: Weekly Review
