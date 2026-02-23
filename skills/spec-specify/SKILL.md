---
name: spec-specify
description: Create a feature specification and resolve ambiguity in one flow
license: MIT
metadata:
  author: h3y6e
  version: "0.1.0"
---

# Specify Skill

## Purpose

Create or update `specs/{feature}/spec.md` from user requirements.
Resolve ambiguity within this skill.

## Input

- User requirements
- `specs/constitution.md`
- Existing `specs/{feature}/spec.md` when present
- Existing `specs/{feature}/research/*.md` when present

## Output

- `specs/{feature}/spec.md`
- `specs/{feature}/research/{topic}.md` when needed

## Steps

1. Read `specs/constitution.md` and apply `language` plus shared rules.
2. Decide the feature slug and target `specs/{feature}/`.
3. Create the spec from `references/spec-template.md`.
4. Run a specification self-review.
   - Scope
   - Data
   - UX
   - Non-Functional
   - Integration
   - Edge
   - Terminology
   - Completion
5. Ask only high-impact clarification questions.
   - Ask one question at a time
   - Maximum 3 questions per session
   - Record low-impact open points in `research/{topic}.md`
6. Integrate answers directly into the spec.
7. Update frontmatter.
   - Required keys: `status`, `summary`
   - Initial `status`: `draft`
8. Perform final review and keep the file within 150 lines.
   - Remove repetition
   - Simplify wording
   - Resolve contradictions
9. In the completion message, suggest the next step.
   - If review-ready: `plan`
   - If more refinement is needed: continue `specify`

## Success Criteria

- Prioritized user stories include at least one P1 story.
- Acceptance scenarios are testable.
- Functional requirements align with success criteria.
- No unresolved high-impact ambiguity remains.

## Completion Guidance

- Next recommended step: `plan`
- Include the target feature and generated `spec.md` path in the response
