# Amine AI Work Harness — v0.2.4

OpenWork-first Agent Plugin for durable context, grounded implementation, audits, proof-of-work, commercial evidence, and cross-project professional memory.

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

There is no `.claude-plugin/` compatibility shim in this version.

## Why

The legacy desktop GitHub importer installs GitHub bundles through the desktop cloud-plugin registry. Current desktop cloud sync can then treat a GitHub-only plugin as removed because it is absent from the organization cloud snapshot. The modern Source / Plugin Directory flow keeps the plugin represented in the organization catalog and avoids that mismatch.

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
