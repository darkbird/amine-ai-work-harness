---
name: professional-memory
description: Maintain a cross-project evidence index of verified achievements, demonstrated capabilities, technologies, recurring client problems, and case-study candidates without copying project secrets or inventing expertise.
---

# Professional Memory

## Purpose

Build a durable cross-project professional memory from verified project evidence.

This is the layer that allows completed work to accumulate into a factual portfolio and capability history over time.

## Source rule

Professional memory may consume only:
- verified or partially verified proof-of-work records
- explicit user-approved project summaries
- commercial evidence derived from those records

It must not infer expertise from conversation alone.

## Central location

Prefer a dedicated workspace or repository:

```text
_professional-memory/
├── INDEX.md
├── ACHIEVEMENTS.md
├── CAPABILITIES.md
├── TECHNOLOGIES.md
├── CLIENT-PROBLEMS.md
├── PROJECTS.md
├── achievements/
└── case-studies/
```

Do not place cross-client confidential information into a public repository.

## Achievement ingestion

For every imported achievement record:

1. preserve project/source reference
2. preserve verification status
3. extract demonstrated capability
4. extract technology only if observed
5. extract problem type
6. record reusable commercial angle
7. avoid copying unnecessary client-sensitive details

## Deduplication

Treat two records as duplicates when they describe the same underlying completed work.

Do not inflate capability counts by importing the same achievement repeatedly from weekly reports, individual achievement files, portfolio drafts, or CV drafts.

The individual proof-of-work achievement is the preferred canonical record.

## CAPABILITIES.md

Organize demonstrated capabilities with supporting achievement IDs.

Do not state "expert" or "mastery" merely from frequency.

## TECHNOLOGIES.md

Track:
- technology
- projects where observed
- relevant verified achievements
- last observed date

Do not list technologies merely discussed but not used.

## CLIENT-PROBLEMS.md

Track recurring problem classes and map them to evidence.

## PROJECTS.md

Maintain a compact project index:
- project
- type
- time period
- safe public description
- strongest achievement references
- confidentiality note if needed

## Case-study candidates

Promote only when enough evidence exists to explain context, problem, constraints, approach, result, and verification.

## Privacy boundary

Never copy secrets, credentials, private personal data, confidential client data, or non-shareable source code.

## Completion criterion

Professional memory should answer:
- What have I actually built or solved?
- Which capabilities are demonstrated by evidence?
- Which technologies have I used in verified work?
- Which client problems have I solved before?
- Which projects can become strong case studies?
