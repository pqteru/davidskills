# Codex: DavidSkills install

Codex does not read Cursor `.mdc` rules. Use **`AGENTS.md`** in the workspace root to bootstrap the router.

## 1. Bootstrap

```bash
cp davidskills/.codex/AGENTS.bootstrap.md /path/to/workspace/AGENTS.md
```

Replace `{{DAVIDSKILLS_ROOT}}` with the **absolute path** to the **`davidskills` directory** — the folder that **contains** `skills/davidskills/SKILL.md`.

Example: `/home/me/david/david/davidskills`

## 2. Workspace symlink

Create **`.davidskill`** per `skills/davidskills/protocols/workspace-setup.md` when using SkillDocs.

## 3. Optional symlink for discovery

```bash
mkdir -p ~/.agents/skills
ln -s /absolute/path/to/davidskills/skills/davidskills ~/.agents/skills/davidskills
```

## Manual fallback

```text
Load and follow {{DAVIDSKILLS_ROOT}}/skills/davidskills/SKILL.md before doing anything else.
```

Substitute the real absolute path for `{{DAVIDSKILLS_ROOT}}`.
