# Component Architecture

Documentation of your project's structure, design decisions, and architectural patterns.

## Purpose

This folder contains architectural knowledge that helps Claude Code understand:
- How your codebase is organized
- Key design decisions and their rationale
- Module dependencies and interactions
- Technology stack and frameworks
- External service integrations

## Recommended Files

### Core Architecture
- **project-structure.md** - Overall codebase organization (REQUIRED)
  - Directory structure
  - Module breakdown
  - Entry points
  - Build system

- **design-decisions.md** - Architectural Decision Records (ADRs)
  - Why certain technologies were chosen
  - Trade-offs considered
  - Alternatives evaluated

- **module-dependencies.md** - How modules interact
  - Dependency graph
  - Module responsibilities
  - Communication patterns

### Technology Stack
- **tech-stack.md** - Technologies used
  - Languages and versions
  - Frameworks
  - Libraries
  - Tools

- **external-dependencies.md** - Third-party integrations
  - APIs consumed
  - External services
  - Authentication methods
  - Rate limits and quotas

### Configuration
- **configuration-guide.md** - Configuration system
  - Environment variables
  - Config files
  - Feature flags
  - Secrets management

### Testing
- **testing-policy.md** - Testing strategy
  - Test types (unit/integration/e2e)
  - Coverage requirements
  - Mocking strategy
  - Test data management

## Document Template

```markdown
# [Component/Module Name]

## Overview
[Brief description of what this component does]

## Responsibilities
- Responsibility 1
- Responsibility 2

## Dependencies
- Dependency 1: [Why needed]
- Dependency 2: [Why needed]

## Key Files
- `path/to/file.ext` - [Purpose]
- `path/to/other.ext` - [Purpose]

## Design Patterns
[Patterns used in this component]

## Configuration
[How to configure this component]

## Common Operations
[Typical tasks involving this component]

## Troubleshooting
[Common issues and solutions]
```

## Customization Guide

### Step 1: Document Your Structure
Create `project-structure.md` with:
- Root directory layout
- Module organization
- File naming conventions
- Package structure (if applicable)

### Step 2: Explain Key Decisions
Create `design-decisions.md` with:
- Major architectural choices
- Technology selections
- Pattern adoptions
- Trade-offs made

### Step 3: Map Dependencies
Create `module-dependencies.md` with:
- Internal module dependencies
- External service dependencies
- Database schemas
- API contracts

### Step 4: Document Configuration
Create `configuration-guide.md` with:
- Environment setup
- Configuration files
- Secrets management
- Feature toggles

### Step 5: Define Testing Strategy
Create `testing-policy.md` with:
- Test pyramid
- Coverage targets
- Testing tools
- CI/CD integration

## Usage Notes

- Keep architecture docs up-to-date as design evolves
- Include diagrams (use Mermaid markdown syntax)
- Link to code examples
- Explain the "why" not just the "what"

## Integration with Other Folders

- **Standards (04)**: Architecture decisions inform coding standards
- **Workflows (01)**: Setup workflows reference architecture docs
- **Templates (02)**: Component templates follow architecture patterns

## Adding New Files

1. Identify an architectural concept that needs documentation
2. Create a file with clear, descriptive name
3. Use the document template above
4. Update this README
5. Link from `CLAUDE.md` if frequently referenced

---

**Customize this folder** by documenting your project's unique architecture, design decisions, and technical stack.