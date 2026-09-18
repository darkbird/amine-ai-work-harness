# Context Health Check

Use `context-health`.

Audit the current workspace's durable project memory against current project evidence.

Rules:
- Read `_project-context/` first.
- Use bounded implementation, documentation, test, and Git inspection only where needed.
- If Git is unavailable, record that fact and continue.
- Do not modify application source code.
- Do not deploy.
- Do not change dependencies.
- Do not repair context automatically.
- Do not invent missing project facts.
- Do not produce a numeric score.
- Flag missing, stale, conflicting, drifted, unverified, orphaned, or secret-risk context.

Return a compact health summary with:
- healthy areas
- material findings
- highest-priority correction
- unresolved questions
- whether a manual context repair is recommended
