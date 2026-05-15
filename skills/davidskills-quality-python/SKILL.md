---
name: davidskills-quality-python
description: Python-specific quality rules for DavidSkills. Load alongside davidskills-quality when Python source changed. Covers uv packaging, types, resources, async, errors, logging.
---

# DavidSkills: Quality — Python

Load only when `.py` files are in scope. Confirm `../davidskills-quality/SKILL.md` was already followed for neutral checks.

## Load order

1. Read `../davidskills/workflows/quality-python.md`
2. Apply checks to all touched Python files

## Required behavior

- Fail the gate on `pip`-first workflows, missing critical types on public APIs, blocking calls in async paths, or bare `except` patterns per the workflow examples.
