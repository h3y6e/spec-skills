---
status: draft
summary: Technical plan for [FEATURE_NAME]
---

Place this file at `specs/{feature}/plan.md`.

## Summary

- [PLAN_SUMMARY]

## Technical Context

- Language/Runtime: [LANGUAGE_RUNTIME]
- Primary Dependencies: [DEPENDENCIES]
- Storage: [STORAGE]
- Testing: [TESTING]
- Target Platform: [PLATFORM]
- Constraints: [CONSTRAINTS]
- Scale/Scope: [SCALE]

## Constitution Check (Pre-Design)

- [ ] Aligns with constitution shared rules
- [ ] Output paths are under `specs/`

## Project Structure

### Documentation

```text
specs/{feature}/
├── spec.md
├── plan.md
├── tasks.md
└── research/*.md
```

### Source Structure

```text
[REPOSITORY_STRUCTURE]
```

## Design Approach

### Architecture

- [ARCHITECTURE_DECISION]

### Data and Interfaces

- [DATA_OR_INTERFACE_DECISION]

### Risks and Tradeoffs

- [RISK_OR_TRADEOFF]

## Planning Phases

### Phase [N]: [PHASE_NAME]

- [PHASE_TASK]

[Add as many phases as needed]

## Backflow Policy

- Update `spec.md` when findings change requirements
- Reset `spec.md` status to `draft` after such updates

## Annotation Cycle

1. Create initial draft
2. Apply annotation feedback
3. Repeat until approval

## Validation Strategy

- [VALIDATION_PLAN]

## Constitution Check (Post-Design)

- [ ] spec/plan/tasks are consistent
- [ ] Final review completed (deduplicate, simplify, resolve contradictions)
