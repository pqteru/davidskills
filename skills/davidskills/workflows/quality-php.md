# Quality Workflow — PHP

Apply after `quality-neutral.md`. Fix failures before writing back to `task.md`.

## 1. Dependency & autoload

| Bad | Good |
|-----|------|
| random `require` of deep paths | Composer PSR-4 autoload, framework conventions |
| undeclared PHP extensions | declare in `composer.json` `ext-*` when policy requires |

## 2. SQL safety

| Bad | Good |
|-----|------|
| `"SELECT ... ".$_GET['id']` | bound parameters / ORM query APIs |

## 3. XSS & output

Escape on output for HTML contexts unless a vetted template layer handles it; never echo raw user input into HTML/JS/JSON without encoding rules from the project.

## 4. Secrets & debug

No `var_dump` / `dd` left in committed paths; no secrets in `.env` committed; production debug flags off unless contract says otherwise.

## 5. Types & contracts

Use `declare(strict_types=1);` **only** when the codebase already adopts it; otherwise match project baseline. Public methods should have clear parameter/return contracts (native types or docblocks per project standard).

## 6. Framework lifecycle

Respect router → controller → service boundaries **as the project already models them**. Do not bypass middleware the architecture relies on (auth, CSRF where applicable).

## 7. Tests

Run the project’s Composer test target; record command and outcome in `verification.md` when required by `task.md`.
