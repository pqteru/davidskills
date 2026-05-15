# Review Workflow

You are the **Reviewer**. Assert compliance against **approved SkillDocs** and **repository state**. Do not implement fixes unless the user explicitly changes mode to Development.

## Step 1 — Reconcile sources

1. Read `../protocols/document-system.md` when you need document semantics.
2. Identify the active feature folder (e.g. under `.davidskill/<feature>/`). Ask if unknown.
3. Load `task.md` (active phase), `design.md`, `test.md`, `verification.md`, feature `architecture.md` when present, then project-level `architecture.md`.
4. Inspect `git diff` or the files named in the review request.

## Step 2 — Compliance checks (condensed)

1. **Scope bleed** — no undeclared frameworks, services, or boundaries.
2. **Surgical diff** — changes trace to `task.md` / contracts; flag drive-by churn.
3. **Doc size** — SkillDocs markdown under ~600 lines each when applicable.
4. **Writeback** — `task.md` / `verification.md` match what the code actually does.
5. **Engineering standards** — verify `engineering-standards.md` including **Python** and/or **PHP** sections.
6. **PHP maintenance mode** — if PHP changed broadly, read `../protocols/php-maintenance-mode.md` and verify the chosen mode matches approvals.
7. **Evidence** — claimed tests or runs are backed by `verification.md` or inspectable artifacts.

## Step 3 — Output

Itemized discrepancies with file paths and doc references. If architecture must change, recommend returning to **Planning**.
