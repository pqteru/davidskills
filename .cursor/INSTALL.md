# Cursor: DavidSkills install

## 1. Package location

This repo includes `davidskills/` at the workspace root with **`skills/davidskills/`** as the bundled router pack (`protocols/`, `workflows/`, `templates/`, entry `SKILL.md`).

## 2. Install the rule

```bash
mkdir -p .cursor/rules
cp davidskills/.cursor/rules/davidskills.mdc .cursor/rules/
```

## 3. Workspace symlink (SkillDocs)

DavidSkills uses **`.davidskill`** at the project root to point at the active SkillDocs project folder (under your `docs/` tree or equivalent). See `skills/davidskills/protocols/workspace-setup.md`.

## 4. `alwaysApply`

Default is **`false`** (description-triggered). Set **`true`** in your copy if you want the router considered on every chat.

## Manual fallback

```text
Read and follow davidskills/skills/davidskills/SKILL.md from the workspace root before proceeding.
```
