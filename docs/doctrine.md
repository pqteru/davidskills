# DavidSkills Doctrine

Rules for extending **DavidSkills** so it stays coherent and small—**Python and PHP only** unless you deliberately widen scope.

## 1. Purpose

DavidSkills makes agent execution more reliable for **Python / PHP** work by:

- routing early into the correct **phase**,
- keeping context small via **JIT** file loads,
- persisting durable state in **SkillDocs** (`architecture.md`, `design.md`, `test.md`, `task.md`, `verification.md`),
- running an explicit **quality gate** before phase completion.

## 2. Prompt-weight awareness

- The **router** (`skills/davidskills/SKILL.md`) stays short: modes + bootstrap only.
- **Workflows** and **protocols** load **only** when the active phase skill points to them.
- Quality rules load **per category / language**, not all at once.

## 3. Bounded stacks

- **Do not** add Go, Node, Ruby, Lua, etc. to this repo’s quality tree without an explicit decision to widen scope.
- New language-specific rules belong in **`workflows/quality-<lang>.md`** + **`davidskills-quality-<lang>/SKILL.md`**, wired from **`davidskills-quality/SKILL.md`**.

## 4. Workspace pointer

- DavidSkills uses project root **`.davidskill`** → active SkillDocs project folder. Use a **distinct** symlink name if this repo already uses another doc-router symlink.
- The **only** canonical mapping file for this pack is **`skills/davidskills/config/workspace-map.local.json`**.

## 5. Shared contracts over duplication

If a rule applies in more than one phase, put it in **`protocols/`** or a single **`workflows/*.md`** and link—do not copy long blocks into multiple phase skills.

## 6. SkillDocs limits

Keep each SkillDocs markdown artifact **under ~600 lines** so sessions can reload cleanly (implementation source is exempt).
