# Quality Workflow

Entry skill: `../../davidskills-quality/SKILL.md`.

## Just-in-time categories

Read each category file **immediately before** applying it (doctrine: keep the rule at the bottom of attention):

1. `quality-neutral.md` — language-neutral checks (always when running quality)

## Language-specific

After neutral checks, load **every** language skill matching files touched in this change:

- `.py` → `../../davidskills-quality-python/SKILL.md`
- `.php` → `../../davidskills-quality-php/SKILL.md`

If no matching extension, apply neutral checks only.
