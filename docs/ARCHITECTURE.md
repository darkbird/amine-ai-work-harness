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
  project-memory  <----------------  scheduled triggers
          |
  session-handoff
          |
          +----------------------+
          |                      |
          v                      v
 technical-grounding        project-auditor
          |                      |
       Context7                  |
          |                      |
          +----------+-----------+
                     |
                     v
                project work
                     |
             evidence-capture
                     |
                     v
                proof-of-work
                     |
          +----------+-----------+
          |                      |
          v                      v
 commercial-evidence      professional-memory
          |                      |
          v                      v
 portfolio / CV /      cross-project evidence base
 proposals / content
```

## Separation of concerns

- Conversation = temporary working memory
- `_project-context` = durable project memory
- Skills = reusable method
- Context7 = external/version-aware technical knowledge
- Proof-of-work = verified evidence layer
- `_professional-memory` = cross-project professional evidence
- Automations = triggers, not intelligence containers
