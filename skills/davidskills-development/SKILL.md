---
name: davidskills-development
description: DavidSkills development module. Use when implementing approved task.md work against SkillDocs contracts.
---

# DavidSkills: Development

## Entry gate

**Stop** until all are true:

1. `task.md` exists for the active SkillDocs feature.
2. The user has **explicitly approved** implementation in this session **or** `task.md` shows approved status for the active phase.
3. `../davidskills/protocols/implementation-readiness-gate.md` passes for the active planning surface.

If any fail: do not load workflows below; return to **Planning** and say what is missing.

---

Assume the router classified **Development**. If the task is no longer implementation, **reroute**.

## Load order

1. If mapping is missing or broken, read `../davidskills-workspace-setup/SKILL.md`; otherwise skip.
2. Read `../davidskills/workflows/02-development.md`
3. Read `../davidskills/workflows/engineering-standards.md` — apply sections that match the stack in scope
4. Load only the active phase in `task.md` and contracts it references (`design.md`, `test.md`, `verification.md`, architecture as needed)
5. Before non-trivial refactors, read stack maintenance protocols referenced in SkillDocs when applicable (e.g. `../davidskills/protocols/php-maintenance-mode.md`)
6. Read shared `../davidskills/protocols/custom-*.md` only when the current step depends on them

Do not read Planning, Review, or Performance workflows unless rerouting.

## Required behavior

- No code changes without explicit approval and a passing readiness gate.
- Follow `task.md` linearly; respect handoff/stop markers.
- After substantive implementation, run **`../davidskills-quality/SKILL.md`** before declaring the phase complete, then update `task.md` / `verification.md` as required.
