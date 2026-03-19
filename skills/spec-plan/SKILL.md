---
name: spec-plan
description: Create or update specs/{feature}/plan.md by turning an approved spec into one execution-ready document with key technical decisions, phased tasks, IDs (T001...), parallel candidates (P), story linkage, and Definition of Done per phase. Use this skill whenever someone wants to translate a spec into concrete implementation work without maintaining a separate execution-design file, create a structured task checklist for a feature, add DoD to task phases, or create/update plan.md. This follows spec-specify and precedes spec-implement in the spec-driven workflow. Don't use for general to-do lists or project management outside the spec workflow.
license: MIT
metadata:
  author: h3y6e
  version: "0.3.0"
---

# Plan Skill

## Purpose

Create or update `specs/{feature}/plan.md` as the execution source of truth, including technical context, key decisions, phased tasks, and completion conditions.

## Input

- Existing `specs/constitution.md` when present
- `specs/{feature}/spec.md`
- `specs/{feature}/research/*.md` when present

## Output

- `specs/{feature}/plan.md`
- `specs/{feature}/spec.md` when backflow is required
- `specs/{feature}/research/{topic}.md` for additional discovery notes

## Steps

1. Resolve `language` and shared rules from `specs/constitution.md` when present; otherwise infer from the available workflow documents and the user's own message. Ask only if still unclear, then conduct all subsequent interaction in this language.
2. Read `spec.md`, extract user stories and constraints, and confirm spec approval state.
   - Require `spec.md` to be `approved` before generating the execution plan
3. Create the plan from `references/plan-template.md`.
   - Summary
   - Execution Context
   - Key Decisions
   - Phases: Setup, Foundational, User Story (P1, P2, ...), Polish
   - Add spike or research tasks before implementation when uncertainty could change the spec or plan structure
4. Capture only execution-facing detail that must stay aligned during implementation.
   - Record technical context, constraints, validation strategy, and key decisions here instead of splitting them into another document
   - Reference the spec for user-facing intent rather than repeating full story prose
5. Standardize the task format.
   - `- [ ] Txxx ...`
   - Use `(P)` for parallel candidates
   - Use `[USn]` for story linkage
6. Add `DoD` under each phase.
   - Include checks for testing, observability, and rollback readiness
   - Write DoD as proof that the phase itself is complete
7. Express dependencies through phase order and task descriptions.
   - Place high-uncertainty discovery work before irreversible implementation tasks
8. Run backflow if requirement gaps or contradictions are discovered.
    - Update `spec.md`
    - Reset `spec.md` status to `draft`
9. Update frontmatter.
    - Required keys: `status`, `summary`
    - Initial `status`: `draft`
    - Set `status: approved` when the plan is ready for implementation
10. Perform final review and keep the file within 150 lines.
    - Remove repetition
    - Simplify wording
    - Resolve contradictions
11. In the completion message, suggest the next step.
     - After approval: `spec-implement`
     - If requirement changes are needed: `spec-specify`

## Success Criteria

- The plan combines execution design and delivery sequencing without requiring another execution document.
- The plan supports independent delivery by story.
- Each phase has a clear DoD.
- `(P)` marks valid parallel work.
- High-uncertainty work is front-loaded as spike or research tasks when needed.
- Backflow handling is explicit.

## Completion Guidance

- Next recommended step: `spec-implement`
- Include the target feature and generated `plan.md` path in the response
