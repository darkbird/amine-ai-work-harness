# Architecture

```text
                           OPENWORK
                              |
                    OpenWork Agent Plugin
                              |
             +----------------+----------------+
             |                                 |
          SKILLS                         AUTOMATIONS
             |                                 |
             v                                 v
    workspace-bootstrap                scheduled triggers
             |
             v
      _project-context
             |
     +-------+--------+
     |                |
     v                v
project-memory   context-health
     |                |
     v                |
session-handoff       |
     |                |
     +-------+--------+
             |
             v
    technical-grounding
             |
          Context7
             |
             v
        project work
             |
      project-auditor
             |
      evidence-capture
             |
             v
        proof-of-work
             |
     +-------+--------+
     |                |
     v                v
commercial-evidence  professional-memory
     |                |
     v                v
portfolio / CV /   cross-project evidence base
proposals / content
```

## Separation of concerns

- Conversation = temporary working memory
- `workspace-bootstrap` = safe first initialization of durable project context
- `_project-context` = durable project memory
- `project-memory` = recover and maintain current project state
- `session-handoff` = persist verified session outcomes
- `context-health` = verify memory consistency against current evidence
- Skills = reusable methods
- Context7 = external/version-aware technical knowledge
- Proof-of-work = verified evidence layer
- `_professional-memory` = cross-project professional evidence
- Automations = triggers, not intelligence containers

## V0.3 lifecycle

```text
bootstrap once
    |
    v
resume <---- project-memory
    |
work
    |
handoff ----> durable state
    |
health check ----> findings or no-op
    |
resume
```

Bootstrap and health checks are deliberately bounded. They inspect enough evidence to establish or verify durable memory without reading the entire workspace by default.
