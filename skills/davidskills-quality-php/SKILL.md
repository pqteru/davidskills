---
name: davidskills-quality-php
description: PHP-specific quality rules for DavidSkills. Load alongside davidskills-quality when PHP source changed. Covers Composer, SQL safety, XSS, secrets, framework boundaries, tests.
---

# DavidSkills: Quality — PHP

Load only when `.php` files are in scope. Confirm `../davidskills-quality/SKILL.md` was already followed for neutral checks.

## Load order

1. Read `../davidskills/workflows/quality-php.md`
2. Apply checks to all touched PHP files

## Required behavior

- Fail the gate on string-built SQL with user input, debug dumps in committed paths, leaked secrets, or bypassing declared auth/middleware contracts.
