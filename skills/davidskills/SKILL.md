---
name: DavidSkills
description: Document-driven development router for Python and PHP. Use when the user needs planning, implementation, review, performance debugging, or lightweight inquiry with minimal context loading. Stacks covered: PHP and Python only.
---

# DavidSkills: Bootstrap-first router

Entry point for **DavidSkills**. Register routes, pick **exactly one** current mode, reroute when the immediate next action changes.

Do not preload workflows, protocols, templates, or quality modules before routing.

## 0. Primary modes

- **Planning** → `../davidskills-planning/SKILL.md`  
  Scope, architecture, SkillDocs shape, `task.md` / `design.md` / `test.md`.

- **Development** → `../davidskills-development/SKILL.md`  
  Approved implementation work against `task.md`.

- **Review** → `../davidskills-review/SKILL.md`  
  Validate code against approved SkillDocs.

- **Debug / Performance** → `../davidskills-performance/SKILL.md`  
  Measured regressions, latency, profiling-backed work.

- **Exception / Inquiry** → `../davidskills-exception/SKILL.md`  
  Lightweight lookup, questions, research—**not** a substitute for Planning or Development.

- **Update** → `../davidskills-update/SKILL.md`  
  Capture reusable rules into `skills/davidskills/protocols/custom-*.md` per `skill-evolution.md`.

**Reroute** when the mode no longer matches the immediate next action. After entering a mode, read **only** that mode’s `SKILL.md` next.

## 0.1 Bootstrap (workspace)

Before other files:

1. If `skills/davidskills/config/workspace-map.local.json` exists and the task is **not** workspace repair, treat mapping as established—do **not** load workspace setup “just to confirm.”
2. If mapping is missing **or** the user is fixing SkillDocs / `.davidskill` / paths, load `../davidskills-workspace-setup/SKILL.md`.

## 1. Constraints

- **Canonical mapping path:** `skills/davidskills/config/workspace-map.local.json` only.
- **No preload:** until the mode is chosen, do not read workflows, quality, or templates except bootstrap repair above.
- **Stacks:** language-specific quality and standards cover **Python** and **PHP** only.

## 2. Support modules

Load support skills **only** when the active phase file says so (e.g. `davidskills-grill` from Planning, `davidskills-quality` after Development).

## 3. Language

Skill bodies are **English** unless the user explicitly requests another language for a deliverable document.
