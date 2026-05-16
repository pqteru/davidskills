# Quality Workflow — Node.js

Apply after `quality-neutral.md`. Fix failures before writing back to `task.md`.

## 1. Package Management

| Bad | Good |
|-----|------|
| Mixing npm, yarn, pnpm without lockfile strategy | Single package manager with committed lockfile (`package-lock.json`, `yarn.lock`, or `pnpm-lock.yaml`) |
| Outdated or missing peer dependencies | Declared peer deps with compatible ranges; validated during CI |
| `npm install -g` in production workflows | Dev dependencies in devDependencies; CLI tools via `npx` or local scripts |

## 2. TypeScript & Types

- Use `strict: true` in `tsconfig.json` for new projects (or match project baseline)
- Public APIs should have explicit type annotations; avoid `any` except at integration boundaries
- Never use `@ts-ignore` without a comment explaining the reason
- Export types alongside implementations where consumed externally

## 3. Async & Promises

| Bad | Good |
|-----|------|
| Fire-and-forget promises without error handler | `try/catch` in async functions or `.catch()` on every promise chain |
| `void` promises without explicit handling | Return promises from async code; consume with `await` or `.catch()` |
| Blocking operations in async context (sync file IO, CPU-heavy loops) | Use `fs/promises`, `asyncio`-like patterns, or worker threads for heavy compute |

## 4. Security

| Bad | Good |
|-----|------|
| Template literals in SQL: `` `SELECT * FROM users WHERE id = ${id}` `` | Parameterized queries: prepared statements or ORM with bound parameters |
| Secrets in `.env` files committed to repo | `.env` in `.gitignore`; use environment variables or secret manager in CI/CD |
| Direct `eval()` or `Function()` constructor on user input | Avoid dynamic code execution; use safe alternatives (JSON.parse, template engines) |

## 5. Framework Boundaries (Express, Fastify, etc.)

- Route handlers should be middleware-aware; respect declared authentication/authorization chains
- Do not bypass router-based CSRF/CORS checks with manual headers
- Error handlers should consolidate logging and response formatting
- Controllers/handlers should delegate to service layer; avoid direct data access in routes

## 6. Resource Management

- Always close database connections, file handles, or stream pipes in error paths
- Use try/finally or context managers (e.g., resource cleanup utilities) for critical resources
- For event emitters, remove listeners when no longer needed to prevent memory leaks

## 7. Logging

- Use structured logging libraries (`winston`, `pino`, `bunyan`) with log levels
- Include request IDs or correlation IDs for traceability in async flows
- Avoid logging sensitive data (passwords, tokens); sanitize before output

## 8. Tests

Tests must be runnable via the project's test script (`npm run test`, `yarn test`, etc.); failing tests are a hard stop before phase completion. Include:
- Unit tests for business logic
- Integration tests for API routes and database queries
- Error case coverage (async rejection handling, malformed input)

## 9. Dependencies

- Regularly audit for security vulnerabilities: `npm audit`, `yarn audit`, `pnpm audit`
- Minimize transitive dependencies; prefer smaller libraries where applicable
- Pin critical infrastructure dependencies; allow patch updates for libraries unless pinning is project policy
