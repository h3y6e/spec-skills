---
name: tasks
description: Break spec and plan into executable phase-based tasks
---

# Tasks Skill

## Purpose

Create or update `specs/{feature}/tasks.md` and define execution order plus completion conditions.

## Input

- `specs/constitution.md`
- `specs/{feature}/spec.md`
- `specs/{feature}/plan.md`
- `specs/{feature}/research/*.md` when present

## Output

- `specs/{feature}/tasks.md`
- `specs/{feature}/spec.md` when backflow is required

## Steps

1. Read `constitution`, then apply `language` and shared rules.
2. Read spec and plan, extract user stories and constraints, and confirm plan/tasks approval state.
3. Create tasks from `references/tasks-template.md`.
   - Setup
   - Foundational
   - User Story (P1, P2, ...)
   - Polish
4. Standardize the task format.
   - `- [ ] Txxx ...`
   - Use `(P)` for parallel candidates
   - Use `[USn]` for story linkage
5. Add `DoD` under each phase.
   - Include checks for testing, observability, and rollback readiness
6. Express dependencies through phase order and task descriptions.
7. Run backflow if requirement gaps or contradictions are discovered.
   - Update `spec.md`
   - Reset `spec.md` status to `draft`
8. Update frontmatter.
   - Required keys: `status`, `summary`
   - File type and ownership are identified by path
9. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
10. In the completion message, suggest the next step.
    - After approval: `implement`
    - If requirement changes are needed: `plan` or `specify`

## Success Criteria

- Tasks support independent delivery by story.
- Each phase has a clear DoD.
- `(P)` marks valid parallel work.
- Backflow handling is explicit.

## Completion Guidance

- Next recommended step: `implement`
- Include the target feature and generated `tasks.md` path in the response
