# Development Workflow

You are the **Developer**. Execute only the **approved** active phase in `task.md` against `design.md` / `test.md`.

## Pre-flight

1. Confirm **SkillDocs** location: canonical mapping `skills/davidskills/config/workspace-map.local.json` and project symlink **`.davidskill`** when used.
2. Identify the **active feature folder**. If unknown, ask before loading planning files.
3. Load in order per `../protocols/document-loading-order.md`.
4. Read `../protocols/implementation-readiness-gate.md` and apply before any file edit. If it fails, return to Planning.
5. Read `engineering-standards.md` — apply the **Python** and/or **PHP** sections matching the stack.
6. If PHP is in scope, read `../protocols/php-maintenance-mode.md` before large refactors or signature changes.
7. Read `../protocols/document-system.md` when you need shared document semantics.

## Execution discipline

- No new dependencies unless `task.md` / `design.md` allows them.
- Chunk edits in existing codebases; do not rewrite entire files without justification in `task.md`.
- If `task.md` says **Follow Existing Patterns**, match local conventions. If **Adopt New Patterns**, confirm approval is recorded in `architecture.md` / `task.md`.
- Update `task.md` after meaningful steps; put raw evidence in `verification.md`.

## Stack notes

- **Python:** `uv run …` for commands; do not introduce `pip install` as the primary workflow.
- **PHP:** prefer Composer scripts; respect PSR autoloading and framework entrypoints.

## Drift

If reality contradicts approved docs, stop and reconcile documents (usually via Planning) before more code.
