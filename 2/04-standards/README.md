# Standards

Coding standards, best practices, and quality guidelines for your project.

## Purpose

This folder defines the coding standards and best practices that Claude Code should follow when writing or reviewing code. These standards ensure consistency, maintainability, and quality across your codebase.

## Recommended Files

### Language-Specific Standards
- **[language]-style-guide.md** - Style guide for your primary language(s)
  - Naming conventions
  - Code organization
  - Language-specific patterns
  - Examples of good/bad code

### Cross-Cutting Concerns
- **error-handling.md** - Error handling patterns
  - Exception types
  - Error propagation
  - Logging errors
  - User-facing messages

- **logging-standards.md** - Logging best practices
  - Log levels (DEBUG, INFO, WARN, ERROR)
  - Structured logging format
  - What to log / what not to log
  - PII handling

- **security-checklist.md** - Security requirements
  - Authentication patterns
  - Authorization checks
  - Input validation
  - Secrets handling
  - OWASP Top 10 prevention

- **performance-guidelines.md** - Performance best practices
  - Database query optimization
  - Caching strategies
  - Async/await patterns
  - Resource management

### API Standards
- **api-standards.md** - API design guidelines
  - REST conventions (if applicable)
  - GraphQL patterns (if applicable)
  - Request/response formats
  - Error responses
  - Versioning strategy

### Testing Standards
- **testing-standards.md** - How to write tests
  - Test naming conventions
  - Test organization
  - AAA pattern (Arrange-Act-Assert)
  - Mocking guidelines
  - Test data strategies

### Documentation Standards
- **documentation-standards.md** - Documentation requirements
  - Code comments (when/how)
  - API documentation
  - README requirements
  - Inline documentation

## Standard Document Template

```markdown
# [Standard Name]

## Overview
[What this standard covers and why it matters]

## Rules

### Rule 1: [Rule Name]
**Requirement**: [What must be done]
**Rationale**: [Why this rule exists]

✅ **Good Example**:
```[language]
[Good code example]
```

❌ **Bad Example**:
```[language]
[Bad code example]
```

### Rule 2: [Rule Name]
[Repeat structure]

## Exceptions
[When it's okay to break these rules]

## Enforcement
[How these rules are enforced - linters, code review, CI/CD]

## References
- [External style guides]
- [Company standards]
- [Industry best practices]
```

## Customization Guide

### Step 1: Choose Your Language Standards
For each language in your project, create:
- `[language]-style-guide.md`
- Reference popular style guides (Google, Airbnb, etc.)
- Document your specific conventions

### Step 2: Define Error Handling
Create `error-handling.md` with:
- Exception hierarchy
- Error propagation patterns
- Retry logic
- Fallback strategies

### Step 3: Establish Logging Standards
Create `logging-standards.md` with:
- When to use each log level
- Structured logging format
- Context propagation (trace IDs, etc.)
- Log aggregation strategy

### Step 4: Security Requirements
Create `security-checklist.md` with:
- Authentication requirements
- Authorization patterns
- Input sanitization
- Secrets management
- Security scanning tools

### Step 5: API Design Guidelines
Create `api-standards.md` (if applicable) with:
- REST/GraphQL conventions
- Endpoint naming
- HTTP status codes
- Request/response formats
- Pagination patterns

## Usage Notes

- Claude Code will reference these standards during:
  - Code generation
  - Code review
  - Refactoring
- Keep standards concise and actionable
- Include plenty of examples
- Link to external resources when appropriate

## Enforcement Tools

Document your enforcement mechanisms:
- **Linters**: ESLint, Pylint, RuboCop, etc.
- **Formatters**: Prettier, Black, gofmt, etc.
- **Static Analysis**: SonarQube, CodeClimate, etc.
- **CI/CD**: Automated checks in pipeline
- **Code Review**: Human review checklist

## Integration with Other Folders

- **Workflows (01)**: Code review workflow references these standards
- **Architecture (03)**: Standards align with architectural decisions
- **Templates (02)**: Code templates follow these standards
- **Agents (08)**: Code reviewer agents enforce these standards

## Adding New Standards

1. Identify a pattern that needs standardization
2. Document the standard with examples
3. Update this README
4. Reference from code review workflow
5. Configure enforcement tools (if applicable)

---

**Customize this folder** by documenting your team's coding standards, best practices, and quality requirements.