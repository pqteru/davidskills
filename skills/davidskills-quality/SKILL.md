---
name: davidskills-quality
description: DavidSkills quality gate. Use after implementation and before declaring a phase complete—neutral checks plus applicable stack-specific quality skills for touched paths.
---

# DavidSkills: Quality

Use as a **pre-completion gate** after Development work on touched files, before claiming the phase done.

Do not substitute Quality for Planning or Review.

## Load order

1. Read `../davidskills/protocols/document-system.md`
2. Read `../davidskills/workflows/05-quality.md`
3. Read `../davidskills/workflows/quality-neutral.md` and apply **before** stack-specific checks
4. Inspect changed paths; load **every** applicable `davidskills-quality-*` sibling skill whose scope matches (read each skill’s description; do not preload unrelated stacks)
5. Fix failures before final `task.md` / `verification.md` writeback

## Required behavior

- Run neutral checks first, then all applicable stack quality skills.
- Treat missing required verification as a failed gate when `task.md` / `design.md` demands evidence.
