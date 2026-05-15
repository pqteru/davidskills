# Planning Tracks

Read **exactly one** track that matches the change, then follow `workflows/01-planning.md` for artifact steps.

## Greenfield

New module or service with little existing coupling. Emphasize boundaries, ownership, and minimal viable contracts.

## Existing system

Change inside a mature codebase. Emphasize surgical diff, regression risk, and conformance to existing patterns unless modernization is explicitly approved.

## Hybrid

Touches both new surfaces and legacy constraints. Split responsibilities explicitly in `architecture.md` and keep `task.md` phased.
