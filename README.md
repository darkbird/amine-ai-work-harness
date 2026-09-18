# Amine AI Work Harness — v0.2.0

OpenWork-first Agent Plugin for durable context, grounded implementation, audits, proof-of-work, commercial evidence, and cross-project professional memory.

## Important change from v0.1.0

v0.2.0 no longer uses `.claude-plugin/plugin.json`.

It uses the root Agent Plugin manifest supported by OpenWork:

```text
plugin.json
skills/
```

## Skills

1. `project-memory`
2. `session-handoff`
3. `technical-grounding`
4. `project-auditor`
5. `evidence-capture`
6. `proof-of-work`
7. `commercial-evidence`
8. `weekly-review`
9. `professional-memory`

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

## Context7

Context7 is not bundled as a second MCP configuration.

`technical-grounding` uses it when already available in OpenWork/OpenCode.

## Recommended flow

```text
project work
  -> session-handoff
  -> project-memory
  -> evidence-capture
  -> proof-of-work
  -> professional-memory
  -> commercial-evidence
```

## Automation prompts

Ready-to-paste prompts are available under `automation-prompts/`.

Recommended cadence:
- after substantial sessions: Context Consolidator
- before delivery: Project Audit
- Friday: Proof of Work Builder
- weekly: Professional Memory Sync
- Sunday: Weekly Review
