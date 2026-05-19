---
name: davidskills-review
description: DavidSkills review module. Use when validating implementation against approved SkillDocs.
---

# DavidSkills: Review

Use when the immediate next action is **Review** (compliance / drift), not new feature planning or ad-hoc coding.

Assume the router classified **Review**. If not, reroute.

## Load order

1. Read `../davidskills/workflows/03-review.md`
2. Read `../davidskills/workflows/engineering-standards.md` — verify applicable sections for the stack in scope
3. Identify the active feature folder under SkillDocs; ask if unknown
4. Load `task.md` (active phase), `design.md`, `test.md`, `verification.md`, feature `architecture.md` when present, then project-level `architecture.md`
5. When broad refactors apply, read stack maintenance protocols referenced in SkillDocs (e.g. `../davidskills/protocols/php-maintenance-mode.md`) and verify mode matches approvals
6. Read shared `../davidskills/protocols/custom-*.md` only when the review step depends on them

## Required behavior

- Output itemized discrepancies with doc references; do not silently normalize drift.
- Reviewers do not implement fixes unless the user explicitly switches to Development.
