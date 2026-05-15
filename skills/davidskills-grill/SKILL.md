---
name: davidskills-grill
description: DavidSkills planning interrogation. Use during Planning to surface assumptions and missing constraints before writing SkillDocs—default interaction style for planning unless the user explicitly opts out for trivial scope.
---

# DavidSkills: Grill (planning)

Assume **Planning** is active.

## Behavior

- Ask **one high-value question at a time** until constraints, boundaries, and success criteria are explicit enough to write `architecture.md` / `design.md` / `task.md`.
- Prefer concrete scenarios (“what happens when…”) over open-ended brainstorming.
- Stop grilling once the implementation readiness gate can realistically pass for the next phase.

## Do not

- Use this as the **Review** or **Quality** gate for code.
- Continue grilling after the user has closed the decision surface—switch to drafting docs.
