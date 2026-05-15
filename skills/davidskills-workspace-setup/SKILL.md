---
name: davidskills-workspace-setup
description: DavidSkills workspace setup. Use when creating or repairing skilldocs path mapping, .davidskill symlink, or workspace-map.local.json.
---

# DavidSkills: Workspace setup

Use only when mapping is missing or the task is explicitly workspace / SkillDocs path repair. Otherwise return to the active routed mode.

## Load order

1. Read `../davidskills/config/workspace-map.example.json`
2. Read `../davidskills/protocols/workspace-setup.md`

## Required behavior

- Persist canonical mapping to `skills/davidskills/config/workspace-map.local.json`.
- Resolve `skilldocs_base_path` (default `<workspace>/docs` when creating fresh mapping).
- Ensure project root `.davidskill` points at `<skilldocs_base_path>/<project>` when this install uses that convention.
- Do not duplicate mapping state outside the canonical file.
