# DavidSkills

DavidSkills is a **document-driven development** prompt pack: bootstrap-first router, `protocols/`, `workflows/`, `templates/`, phase skills, and a quality gate. It is **narrow by design**:

- **Stacks:** stack-specific quality and design stubs load **just-in-time**; shared phase workflows stay stack-neutral.
- **Tooling:** follow repo-native package managers and scripts recorded in SkillDocs (`design.md`, `test.md`).
- **Workspace pointer:** project root **`.davidskill`** → active SkillDocs project (pick another name only if this repo already reserves that symlink).
- **Canonical mapping:** `skills/davidskills/config/workspace-map.local.json` (gitignored—see `config/.gitignore`).

Skill bodies are **English**.

## Layout

| Path | Role |
|------|------|
| `skills/davidskills/SKILL.md` | Entry router |
| `skills/davidskills/protocols/` | Shared contracts (documents, workspace, readiness gate, stack maintenance, skill evolution) |
| `skills/davidskills/workflows/` | Phase workflows + engineering standards + quality (neutral + stack-specific) |
| `skills/davidskills/templates/` | SkillDocs stubs |
| `skills/davidskills/config/` | `workspace-map.example.json`; local `workspace-map.local.json` |
| `skills/davidskills-planning/` | Planning |
| `skills/davidskills-development/` | Development |
| `skills/davidskills-review/` | Review |
| `skills/davidskills-performance/` | Debug / performance |
| `skills/davidskills-exception/` | Lightweight inquiry |
| `skills/davidskills-update/` | Persist rules to `protocols/custom-*.md` |
| `skills/davidskills-workspace-setup/` | Mapping + `.davidskill` repair |
| `skills/davidskills-grill/` | Planning interrogation (default in Planning) |
| `skills/davidskills-quality/` | Quality gate router |
| `skills/davidskills-quality-*/` | Stack-specific quality gates (see each skill) |
| `docs/doctrine.md` | Extension rules for this pack |

## Install

- **Cursor:** [`.cursor/INSTALL.md`](.cursor/INSTALL.md)
- **Codex:** [`.codex/INSTALL.md`](.codex/INSTALL.md)

## Manual one-liner

```text
Read and follow davidskills/skills/davidskills/SKILL.md from this workspace root before proceeding.
```
