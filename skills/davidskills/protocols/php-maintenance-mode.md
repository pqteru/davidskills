# PHP Maintenance Mode

Before large PHP refactors, classify the touched area:

## Conservative PHP maintenance (default)

- Match existing framework and folder conventions (e.g. Laravel vs plain PHP).
- Preserve public method signatures and request/response shapes unless `task.md` explicitly approves a breaking change.
- Prefer small, test-backed diffs; avoid drive-by reformatting unrelated files.

## Explicit modernization

- Allowed only when `architecture.md` or `task.md` records user approval and compensating verification (tests, rollout notes).
- Permits newer PHP features (e.g. `readonly`, enums, constructor promotion) **only** where the project baseline and CI support them.

If the mode is unclear, ask once and record the choice in `task.md` before proceeding.
