# DavidSkills Codex bootstrap

Before **Planning, Development, Review, Performance debugging, or Update** on substantive project work, load and follow:

`{{DAVIDSKILLS_ROOT}}/skills/davidskills/SKILL.md`

Treat that file as the **routing source of truth**.

Execution rules:

- Read **only** the entry router first.
- After reading it, choose **exactly one** primary mode and read **only** that mode’s `SKILL.md` next.
- Do **not** preload `protocols/`, `workflows/`, `templates/`, or quality skills unless the active phase or router bootstrap requires it.
- For **Development**, do not edit code without a passing **implementation readiness gate** and explicit user approval as defined in that router and phase skill.
- Stack-specific dependency and quality rules load **just-in-time** per the active phase skill and touched paths.
- User instructions still take precedence when they explicitly override DavidSkills.

If the path is missing, stop and tell the user to set `{{DAVIDSKILLS_ROOT}}` to the absolute path of the `davidskills` directory (the folder containing `skills/davidskills/SKILL.md`).
