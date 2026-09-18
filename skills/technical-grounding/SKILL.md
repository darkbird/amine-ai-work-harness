---
name: technical-grounding
description: Ground version-sensitive implementation decisions in current documentation. Prefer Context7 when available and verify installed dependency versions before relying on APIs.
---

# Technical Grounding

## Purpose

Reduce errors caused by stale knowledge, version mismatch, or guessed APIs.

## Use before

- unfamiliar framework/library APIs
- authentication/authorization changes
- framework configuration
- SDK/API integrations
- ORM/database changes
- dependency upgrades
- deployment/infrastructure configuration
- version-sensitive code review

## 1. Inspect actual versions

Use package manifests, lockfiles, plugin metadata, runtime version files, and configs.

Never assume latest.

## 2. Define a concrete documentation question

Include observed version and project constraints.

## 3. Use Context7 when available

Preferred flow:
1. resolve the exact library
2. prefer version-matching docs
3. query a concrete implementation question
4. make focused follow-ups only when necessary

Never store Context7 credentials in project files.

## 4. Compare docs with code

Check:
- current API usage
- deprecated patterns
- version mismatch
- intentional legacy patterns
- compatibility constraints

Do not rewrite code merely because docs show a newer pattern.

## 5. Implement narrowly

If implementation is requested:
- make the smallest justified change
- follow project conventions
- avoid unrelated refactors
- preserve compatibility when required
- update tests when appropriate

## 6. Verify

Use the narrowest useful verification: typecheck, tests, build, browser flow, lint, or framework-specific validation.

Documentation does not replace runtime verification.

## Fallback

If Context7 is unavailable, prefer official/local documentation and avoid claiming version-specific certainty without evidence.

Persist only project-relevant technical conclusions through `project-memory`, not raw documentation dumps.
