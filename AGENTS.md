# AGENTS.md

## Project Overview

spec-skills is a **Markdown-only repository** containing [Agent Skills](https://agentskills.io) for Spec-Driven Development.
There is no source code, no build system, no package manager, and no test framework.
All content is declarative Markdown defining AI agent skill definitions and their reference templates.

## Commands

There are **no build, lint, or test commands**.

The only CI pipeline is automated release,
triggered on push to `main`. It bumps the `metadata.version` field in all five `SKILL.md` files and creates a GitHub release.

## Repository Structure

```
spec-skills/
├── README.md
├── skills/                             # Skill definitions (core content)
│   ├── spec-constitution/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── constitution-template.md
│   ├── spec-specify/
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── spec-template.md
│   │       └── research-template.md
│   ├── spec-plan/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── plan-template.md
│   ├── spec-tasks/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── tasks-template.md
│   └── spec-implement/
│       └── SKILL.md
└── specs/                              # example specs
    ├── constitution.md
    └── sample-feature/
        ├── spec.md
        ├── plan.md
        ├── tasks.md
        └── research/
            └── implementation-note.md
```

## The Five Skills (Workflow Order)

1. **spec-constitution** - Define shared project rules in `specs/constitution.md`
2. **spec-specify** - Create `specs/{feature}/spec.md` from requirements
3. **spec-plan** - Create `specs/{feature}/plan.md` with technical design
4. **spec-tasks** - Break plan into `specs/{feature}/tasks.md` with phased tasks
5. **spec-implement** - Execute tasks with implement/self-validate/fix loops

## Content Style Guidelines

### SKILL.md Structure

Every skill file follows this exact structure:

1. **YAML frontmatter**: `name`, `description`, `license`, `metadata.author`, `metadata.version`
2. **H1 title**: `# {Skill Name} Skill`
3. **Sections in order**: Purpose, Input, Output, Steps, Success Criteria, Completion Guidance

### Markdown Formatting

- Use numbered lists for sequential steps
- Use `- [ ]` / `- [x]` checkboxes for DoD items and acceptance criteria
- Task IDs follow the pattern `T001`, `T002`, etc.
- Use backticks for file paths, identifiers, and skill names
- Requirements use prefixed IDs: `FR-001`, `SC-001`
- Keep all documents **within 150 lines** when possible

### Templates

- Templates live in `skills/{skill-name}/references/`
- Placeholders use `[UPPER_SNAKE_CASE]` format (e.g., `[FEATURE_NAME]`, `[DESCRIPTION]`)
- Templates include placement instructions (e.g., `Place this file at specs/{feature}/spec.md.`)
- HTML comments (`<!-- ... -->`) are used for inline guidance in templates

### Naming Conventions

- Skill directories: `spec-{name}` (kebab-case with `spec-` prefix)
- Feature directories: `specs/{feature-slug}/` (kebab-case)
- Research files: `specs/{feature}/research/{topic}.md` (kebab-case)
- Fixed filenames: `SKILL.md`, `constitution.md`, `spec.md`, `plan.md`, `tasks.md`

### Writing Style

- Concise, imperative tone in skill steps ("Read", "Create", "Update", "Perform")
- Keep descriptions to 1-3 sentences
- Avoid redundancy; deduplicate during final review
- Every skill ends with Completion Guidance recommending the next skill

## Git Conventions

### Commit Messages

Follow conventional commits with lowercase type prefixes:

- `feat:` for new features or skills
- `fix:` for corrections
- `docs:` for documentation changes
- `chore:` for maintenance (config, CI)
- `ci:` for CI/workflow changes
