# Development Workflows

This section contains all development and collaboration workflows for the intapi-assistant project. These workflows define **how the team works on the project**, not the technical workflows within the application itself.

## Purpose

- Standardize development processes across the team
- Provide clear procedures for common development tasks
- Ensure consistency in code quality, testing, and deployment
- Define collaboration patterns and communication standards
- Support efficient onboarding of new team members

## Contents

- **[01-development-workflow.md](01-development-workflow.md)**
  Day-to-day development process, local setup, and coding standards

- **[02-code-review-workflow.md](02-code-review-workflow.md)**
  Pull request creation, review process, and approval procedures

- **[03-testing-workflow.md](03-testing-workflow.md)**
  Testing strategy, test execution, and quality assurance

- **[04-deployment-workflow.md](04-deployment-workflow.md)**
  Build, release, and deployment procedures

- **[05-documentation-workflow.md](05-documentation-workflow.md)**
  How to maintain memory bank and project documentation

- **[06-collaboration-workflow.md](06-collaboration-workflow.md)**
  Team communication, sync patterns, and decision-making

## How to Use This Section

### For Developers
1. Start with **01-development-workflow.md** for daily coding practices
2. Reference **02-code-review-workflow.md** when creating or reviewing PRs
3. Consult **03-testing-workflow.md** before running tests
4. Check **05-documentation-workflow.md** when updating docs

### For AI Assistants
1. **ALWAYS** Load this section along with the memory bank
2. Follow workflows exactly as documented
3. Reference appropriate workflow when performing tasks
4. **ALWAYS** Update workflows if new patterns emerge

### For Team Leads
1. Keep workflows updated as processes evolve
2. Ensure all team members follow documented procedures
3. Use workflows as onboarding materials
4. Review and refine workflows based on team feedback

## Workflow Principles

1. **Ticket-Driven**: All work must be associated with a valid JIRA ticket
2. **Mise-First**: All commands executed via `mise run <task>` for reproducibility
3. **Memory Bank**: Single source of truth for all project knowledge
4. **Documentation**: Update docs alongside code changes
5. **Testing**: Tests required for all new features and bug fixes
6. **Code Review**: All changes require peer review before merge
7. **Automation**: Leverage CI/CD and mise tasks for consistency

## Related Documentation

- [Ticket Administration](../ticket-administration/README.md) - JIRA ticket workflows and templates
- [Team Agents](../agents/README.md) - Role definitions and responsibilities
- [Foundation](../foundation/README.md) - Project structure and technical context
- [Ticket Administration-Best Practices](../ticket-administration/01-best-practices.md) - Coding and commit standards

---

_Last updated: 2025-10-09_