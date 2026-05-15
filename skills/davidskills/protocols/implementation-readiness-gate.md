# Implementation Readiness Gate

Apply immediately before:

- declaring planning complete or asking whether implementation should begin, or
- editing implementation files during Development preflight.

## Core rule

`architecture.md`, `design.md`, `test.md`, `task.md`, and verification intent must tell the Developer **what to do**. They must not ask the Developer to **choose** the active implementation direction for the current phase.

## Hard blockers

Do not begin implementation when the active planning surface has:

- active-phase branches such as “choose A or B” without a selected path
- `TODO` / `TBD` / placeholder values in required active-phase sections
- open questions that change behavior, ownership, tests, verification, or rollout for this phase
- unresolved handoffs or blockers that must clear before coding
- disagreement between `architecture.md`, `design.md`, `test.md`, `task.md`, or required contracts

User approval does not override a failed gate; fix the documents first.

## Fast heuristics

Scan for: `TODO`, `TBD`, `[`, `choose`, `either`, `open question`, `blocker`. Classify each hit as selected, deferred, out-of-scope, or stop-condition before development begins.
