---
name: davidskills-performance
description: DavidSkills performance and debugging module. Use for measured failures, regressions, or profiling-backed optimization in Python and/or PHP services.
---

# DavidSkills: Performance

Use when the immediate next action is **Debug / Performance** with measurable symptoms.

Assume the router classified this mode. If the user actually needs Planning, Development, or Review, **reroute**.

## Load order

1. If mapping is missing or broken, read `../davidskills-workspace-setup/SKILL.md`; otherwise skip.
2. Read `../davidskills/workflows/04-performance-debugging.md`
3. Load only the architecture sections and `task.md` phases needed for the bottleneck
4. If PHP lifecycle or caching behavior is in scope, read `../davidskills/protocols/php-maintenance-mode.md`
5. Read shared `../davidskills/protocols/custom-*.md` only when relevant

## Required behavior

- Baseline before optimization; persist durable findings back to SkillDocs when contracts require.
- If boundaries change, return to **Planning** before broad implementation continues.
