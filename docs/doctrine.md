# DavidSkills Doctrine

Rules for extending **DavidSkills** so it stays coherent and small—add stacks deliberately, not ad hoc in shared workflows.

## 1. Purpose

DavidSkills makes agent execution more reliable for document-driven work by:

- routing early into the correct **phase**,
- keeping context small via **JIT** file loads,
- persisting durable state in **SkillDocs** (`architecture.md`, `design.md`, `test.md`, `task.md`, `verification.md`),
- running an explicit **quality gate** before phase completion.

## 2. Prompt-weight awareness

- The **router** (`skills/davidskills/SKILL.md`) stays short: modes + bootstrap only.
- **Workflows** and **protocols** load **only** when the active phase skill points to them.
- Quality rules load **per category / stack**, not all at once.

## 3. Bounded stacks

- **Do not** add new stacks to shared phase workflows; widen via **`workflows/quality-<stack>.md`** + **`davidskills-quality-<stack>/SKILL.md`**, wired from **`davidskills-quality/SKILL.md`**, with an explicit scope decision.

## 4. Workspace pointer

- DavidSkills uses project root **`.davidskill`** → active SkillDocs project folder. Use a **distinct** symlink name if this repo already uses another doc-router symlink.
- The **only** canonical mapping file for this pack is **`skills/davidskills/config/workspace-map.local.json`**.

## 5. Shared contracts over duplication

If a rule applies in more than one phase, put it in **`protocols/`** or a single **`workflows/*.md`** and link—do not copy long blocks into multiple phase skills.

## 6. SkillDocs limits

Keep each SkillDocs markdown artifact **under ~600 lines** so sessions can reload cleanly (implementation source is exempt).
