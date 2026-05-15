# Document Loading Order

Default order when entering a feature folder (active SkillDocs feature):

1. `design.md` — binding implementation shape for this change
2. `test.md` — binding test contract
3. `task.md` — active phase only
4. `verification.md` — evidence expectations
5. Feature `architecture.md` when present, then project-level `architecture.md` for baseline

Do not load unrelated feature folders. If the active feature is unknown, ask before loading planning files.
