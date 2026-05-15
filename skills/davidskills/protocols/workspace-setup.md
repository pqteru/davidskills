# Workspace Setup & Directory Rules (DavidSkills)

Use when resolving where SkillDocs live and how the workspace points at the active project.

## Canonical mapping

- **Canonical file:** `skills/davidskills/config/workspace-map.local.json` (machine-local; gitignored).
- If missing, derive `skilldocs_base_path` as `<workspace_path>/docs` and persist it into that file.

## Active project pointer

- **Symlink:** project root `.davidskill` → `<skilldocs_base_path>/<project>` (the active SkillDocs project folder).
- Do not treat an ancestor’s `.davidskill` as authoritative for a nested repo without explicit user intent.

## Feature folders

- Active work lives under the project folder, typically a named feature subdirectory (e.g. `.davidskill/my-feature/`).
- If the user has not named the active feature, ask before loading planning files.

## Repair

- If mapping and `.davidskill` disagree, treat as repair work: reconcile mapping and symlink, then return to the routed phase.
