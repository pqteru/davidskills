---
name: davidskills-planning
description: DavidSkills planning module. Use for architecture, SkillDocs authoring, task shaping, or rewriting planning artifacts.
---

# DavidSkills: Planning

Use when the immediate next action is **Planning**.

If the work becomes implementation, review, or measured debugging, **reroute**.

## Load order

1. If mapping or `.davidskill` repair is required, read `../davidskills-workspace-setup/SKILL.md`; otherwise skip.
2. Read `../davidskills/workflows/01-planning.md`
3. Read `../davidskills-grill/SKILL.md` as the default planning interview style
4. Read `../davidskills/protocols/planning-tracks.md` and follow the selected track
5. Read the stack-appropriate `../davidskills/templates/design-*.md` stub(s) before finalizing `design.md`
6. Read `../davidskills/protocols/implementation-readiness-gate.md` before requesting implementation approval
7. Read shared `../davidskills/protocols/custom-*.md` only when a planning step explicitly depends on captured install-wide rules

Do not read Development, Review, Performance, or Quality workflows unless the task reroutes.

## Required behavior

- Keep SkillDocs bounded and decision-complete for the active phase before asking for implementation approval.
- Record stack-specific dependency and script conventions in planning contracts (`design.md`, `architecture.md`).
- After updating planning docs for a new implementation phase, **stop** for explicit user approval before Development begins.
