---
name: davidskills-quality
description: DavidSkills quality gate. Use after implementation and before declaring a phase complete—language-neutral checks plus Python and PHP specific rules when those files are in scope.
---

# DavidSkills: Quality

Use as a **pre-completion gate** after Development work on touched files, before claiming the phase done.

Do not substitute Quality for Planning or Review.

## Load order

1. Read `../davidskills/protocols/document-system.md`
2. Read `../davidskills/workflows/05-quality.md`
3. Read `../davidskills/workflows/quality-neutral.md` and apply **before** language-specific checks
4. Inspect changed paths’ extensions; load **every** match:
   - `.py` → read `../davidskills-quality-python/SKILL.md`
   - `.php` → read `../davidskills-quality-php/SKILL.md`
5. Fix failures before final `task.md` / `verification.md` writeback

## Required behavior

- Run neutral checks first, then all applicable language skills.
- Treat missing required verification as a failed gate when `task.md` / `design.md` demands evidence.
