# Development Workflow

You are the **Developer**. Execute only the **approved** active phase in `task.md` against `design.md` / `test.md`.

## Pre-flight

1. Confirm **SkillDocs** location: canonical mapping `skills/davidskills/config/workspace-map.local.json` and project symlink **`.davidskill`** when used.
2. Identify the **active feature folder**. If unknown, ask before loading planning files.
3. Load in order per `../protocols/document-loading-order.md`.
4. Read `../protocols/implementation-readiness-gate.md` and apply before any file edit. If it fails, return to Planning.
5. Read `engineering-standards.md` — apply sections that match the stack in scope.
6. Before large refactors, read stack maintenance protocols referenced in `task.md` / `design.md` when applicable (e.g. `../protocols/php-maintenance-mode.md`).
7. Read `../protocols/document-system.md` when you need shared document semantics.

## Execution discipline

- No new dependencies unless `task.md` / `design.md` allows them.
- Chunk edits in existing codebases; do not rewrite entire files without justification in `task.md`.
- If `task.md` says **Follow Existing Patterns**, match local conventions. If **Adopt New Patterns**, confirm approval is recorded in `architecture.md` / `task.md`.
- Update `task.md` after meaningful steps; put raw evidence in `verification.md`.

## Stack notes

- Follow dependency and run commands documented in `design.md` and existing repo conventions.

## Drift

If reality contradicts approved docs, stop and reconcile documents (usually via Planning) before more code.
