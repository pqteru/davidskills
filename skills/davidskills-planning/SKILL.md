---
name: davidskills-planning
description: DavidSkills planning module. Use for architecture, SkillDocs authoring, task shaping, or rewriting planning artifacts for Python and/or PHP work.
---

# DavidSkills: Planning

Use when the immediate next action is **Planning**.

If the work becomes implementation, review, or measured debugging, **reroute**.

## Load order

1. If mapping or `.davidskill` repair is required, read `../davidskills-workspace-setup/SKILL.md`; otherwise skip.
2. Read `../davidskills/workflows/01-planning.md`
3. Read `../davidskills-grill/SKILL.md` as the default planning interview style
4. Read `../davidskills/protocols/planning-tracks.md` and follow the selected track
5. If Python is in scope, read `../davidskills/templates/design-python.md` before finalizing `design.md`
6. If PHP is in scope, read `../davidskills/templates/design-php.md` before finalizing `design.md`
7. Read `../davidskills/protocols/implementation-readiness-gate.md` before requesting implementation approval
8. Read shared `../davidskills/protocols/custom-*.md` only when a planning step explicitly depends on captured install-wide rules

Do not read Development, Review, Performance, or Quality workflows unless the task reroutes.

## Required behavior

- Keep SkillDocs bounded and decision-complete for the active phase before asking for implementation approval.
- **Python:** `uv` only for env and dependencies in planning contracts.
- **PHP:** Composer-based dependency and script contracts.
- After updating planning docs for a new implementation phase, **stop** for explicit user approval before Development begins.
