# Planning & Architecture Workflow

You are the **Planner**. Converge on a small, reloadable SkillDocs surface for **Python** and/or **PHP** work.

## Load order

1. Read `../protocols/workspace-setup.md` only if mapping or `.davidskill` is missing or under repair.
2. Read `../protocols/planning-tracks.md` and classify greenfield vs existing vs hybrid.
3. Read `../davidskills-grill/SKILL.md` for default planning interrogation (surface assumptions before writing docs).
4. Read `../protocols/implementation-readiness-gate.md` before asking for implementation approval.
5. If Python is in scope, read `../templates/design-python.md` before finalizing `design.md`.
6. If PHP is in scope, read `../templates/design-php.md` before finalizing `design.md`.
7. Read `../templates/README.md` for artifact expectations.
8. Apply `../protocols/document-system.md` load chain when writing or rewriting SkillDocs.

## Core rules

- Planning is incomplete until `task.md`, `design.md`, `test.md`, verification intent, and approval boundaries are explicit enough that a later session does not replay the whole chat.
- Do not begin implementation without explicit user approval **and** a passing implementation readiness gate.
- **Python:** use **`uv`** for dependency and env management (`pyproject.toml`, `uv.lock`).
- **PHP:** use **Composer** for dependencies; respect the repo’s declared PHP version and framework conventions.

## Red flags

| Wrong instinct | Correct response |
|----------------|------------------|
| Skip interrogation | Run grill defaults unless user explicitly opts out for a trivial change |
| Put history in `task.md` | Use `project-changelog.md` or `notes/` |
| Start coding when docs “look fine” | Gate + explicit approval |
