# Document Authority

Each SkillDocs artifact owns one primary contract:

| Artifact | Owns |
|------------|------|
| `architecture.md` | Effective boundaries, approved target shape, stable flows |
| `design.md` | Implementation-facing contract (modules, responsibilities, file tree intent) |
| `test.md` | Testing contract derived from `design.md` |
| `task.md` | **Active executable phase only** — linear tasks, handoffs, approval state |
| `verification.md` | Durable evidence: commands run, outputs, negative paths, cleanup notes |
| `notes/` | Rejected ideas, scratch material not needed in default load |
| `project-changelog.md` (project root) | Timestamped rationale rows; not default execution context |

If these disagree, reconcile in the documents before claiming a phase complete.
