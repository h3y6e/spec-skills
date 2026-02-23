---
name: spec-constitution
description: Define shared project rules for spec-skills runs
license: MIT
metadata:
  author: h3y6e
  version: "0.2.0"
---

# Constitution Skill

## Purpose

Create or update `specs/constitution.md` and confirm shared rules for spec-skills.

## Input

- User requirements
- Existing `specs/constitution.md` when present
- Existing `specs/{feature}/spec.md`, `plan.md`, `tasks.md` for consistency checks

## Output

- `specs/constitution.md`

## Steps

1. Read `specs/constitution.md`; if missing, initialize from `references/constitution-template.md`.
2. Update frontmatter.
   - Required keys: `language`, `summary`
   - `language` is the default documentation language
   - `summary` is a one-line overview
3. Update Core Principles with project-specific rules.
4. Add variable project rules when needed.
   - Naming rules
   - Quality thresholds
   - Security requirements
5. Verify consistency with existing feature documents.
   - Check `specs/{feature}/spec.md`, `plan.md`, `tasks.md`
6. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
7. In the completion message, suggest the next step.
   - New feature: `spec-specify`
   - Existing feature update: `spec-specify` for the target `spec.md`

## Success Criteria

- Constitution reflects current shared rules.
- Frontmatter values are valid and complete.
- Related feature documents stay consistent.

## Completion Guidance

- Next recommended step: `spec-specify`
- Include the target feature and next file path in the response
