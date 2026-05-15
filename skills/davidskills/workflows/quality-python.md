# Quality Workflow — Python

Apply after `quality-neutral.md`. Fix failures before writing back to `task.md`.

## 1. Packaging (`uv`)

| Bad | Good |
|-----|------|
| `pip install` as primary workflow | `uv add`, `uv run`, committed `uv.lock` |
| ad-hoc venv instructions without `uv` | `uv run python …` / `uv run pytest` |

## 2. Types

Public callables should have annotations; avoid `Any` except at third-party boundaries.

## 3. Resources & concurrency

Prefer `with` for files/connections. In async code, do not block the event loop on socket/file IO without `asyncio.to_thread` or approved async drivers.

## 4. Exceptions

Catch narrow types; no bare `except:`. Domain errors should be typed, not message-parsed.

## 5. Logging

Use `logging.getLogger(__name__)`; structured fields for request/job IDs where applicable.

## 6. Mutable defaults

Never use mutable default arguments; use `None` and initialize inside the body.

## 7. Tests

Tests must be runnable via `uv run` per project convention; failing tests are a hard stop before phase completion.
