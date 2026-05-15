# Engineering Standards

Apply during **Development** and **Review**. Distinct from runtime checks in `quality-neutral.md`.

Default service shape when the codebase already uses layers: **Router / Controller → Service → Repository** (or framework-native equivalents). Controllers stay thin; domain logic does not depend on HTTP globals.

## 1. Naming & clarity

Names express action and subject. Avoid vague exported names (`data`, `handle`, `process`) unless locally scoped and obvious.

## 2. Errors & logging

- Errors carry **context** (what step failed). No string-matching on raw messages for control flow.
- Use the project’s structured logger in server paths; avoid `print` / `var_dump` in production paths.

## 3. Magic values

Ports, timeouts, retries, and domain literals are named constants or config — not bare literals scattered in logic.

## 4. API / boundary shape

External boundaries return consistent shapes; server errors do not leak stack traces or secrets to clients.

## 5. File discipline

Target **under ~400 lines** per application source file where reasonable; soft ceiling **~600** with an explicit documented exception in `design.md` / `task.md` when splitting would hurt clarity.

---

## Python (DavidSkills)

- **Package manager:** **`uv` only** for deps and runs (`uv add`, `uv run`, `uv lock`). Do not introduce `pip install` / `requirements.txt`-only flows as the primary contract.
- **Types:** type hints on public functions; avoid untyped `Any` except at true FFI boundaries.
- **Resources:** prefer context managers (`with`) for files, connections, locks.
- **Async:** no blocking I/O inside `async def` without `asyncio.to_thread` or an approved executor pattern.
- **Tests:** `uv run pytest` (or project-standard via `uv run`).

---

## PHP (DavidSkills)

- **Dependencies:** Composer only; respect `composer.json` platform PHP version.
- **SQL:** prepared statements / query builder bindings — no string-concat SQL with user input.
- **Types:** declare property and parameter types where the project baseline allows; avoid silent mixed return shapes on public APIs.
- **Framework:** follow existing Laravel / Symfony / plain-PHP layout; do not invent a parallel architecture without `task.md` approval.
- **Errors:** log with context; user-visible messages stay safe and non-leaky.
- **Tests:** `composer test` or the project’s documented script — record commands in `verification.md`.
