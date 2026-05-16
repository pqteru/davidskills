---
name: davidskills-quality-node
description: Node.js-specific quality rules for DavidSkills. Load alongside davidskills-quality when Node.js source changed. Covers package managers, TypeScript, async patterns, security, framework boundaries, and testing.
---

# DavidSkills: Quality — Node.js

Load only when `.ts`, `.js`, or related Node.js files are in scope. Confirm `../davidskills-quality/SKILL.md` was already followed for neutral checks.

## Load order

1. Read `../davidskills/workflows/quality-node.md`
2. Apply checks to all touched Node.js files

## Required behavior

- Fail the gate on unhandled promise rejections, unsafe SQL injection patterns, hardcoded secrets in committed files, or missing error handlers in async chains per the workflow examples.
