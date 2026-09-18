# Changelog

## 0.3.0

- Added `workspace-bootstrap` for evidence-based, idempotent initialization of `_project-context/`.
- Added `context-health` for read-only detection of missing, stale, conflicting, drifted, unverified, orphaned, or secret-risk durable context.
- Added a Context Health automation prompt.
- Updated `project-memory` to hand uninitialized workspaces to `workspace-bootstrap` and stale-memory checks to `context-health`.
- Added bounded evidence-reading and explicit no-assumption rules for bootstrap.
- Documented the V0.3 continuity lifecycle.
- Kept application source, deployment, dependency, and secret handling outside bootstrap/context repair by default.

## 0.2.4

- Removed the temporary `.claude-plugin/plugin.json` compatibility shim.
- Removed the temporary preview-test fixture.
- Standardized the repository as a pure OpenWork/Agent Plugin with root `plugin.json`.
- Documented the modern OpenWork Source / Plugin Directory installation path.
- Avoids the legacy desktop GitHub importer path that can be misclassified as a removed cloud extension during desktop cloud sync.

## 0.2.3

- Fixed YAML quoting in `weekly-review`.
- Bumped the Agent Plugin and desktop compatibility manifests.

## 0.2.2

- Simplified the legacy desktop compatibility manifest.
- Kept root Agent Plugin metadata as canonical.

## 0.2.0

- Switched from `.claude-plugin/plugin.json` to OpenWork-supported root Agent Plugin `plugin.json`.
- Added `professional-memory`.
- Added `_professional-memory` templates.
- Added `professional-memory-sync` automation prompt.
- Kept the 8 previously validated skills.
- Clarified Context7 as external technical grounding, not project memory.
- Added OpenWork plugin-format documentation.

## 0.1.0

- Initial skill harness.
