# Quality — Language-neutral core

Apply during `davidskills-quality`. Fix failures before declaring a phase complete.

## 1. Resource & input safety

- Validate external input at boundaries; reject or normalize early.
- Avoid leaking secrets in logs, errors, or client-visible payloads.

## 2. Config & environment

- No silent fallback to insecure defaults for auth, TLS, or credentials.
- Configuration is explicit (env or config files as per project norms).

## 3. Resilience

- Timeouts on external calls where applicable; retry with backoff only when idempotent or guarded.
- Graceful degradation paths documented when required by `design.md`.

## 4. Operational hygiene

- No committed secrets; `.gitignore` covers build artifacts and local env files per project policy.
- Evidence of checks lives in `verification.md` when the contract requires it.

## 5. Identity & authz (when applicable)

- Authorization checks live next to sensitive operations, not only at the edge.
- Stable identifiers; do not mix internal IDs with externally exposed tokens without explicit design.
