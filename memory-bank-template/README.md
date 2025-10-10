# Memory Bank for [PROJECT_NAME]

> **👋 Welcome to the Memory Bank Template!**
>  
> **This memory bank is the source of truth and main entry point of knowledge for all AI assistants and developers.**  
>  
> Loading the Memory Bank instantly restores all project knowledge and context—so you (and your AI assistant) can work with confidence, clarity, and zero guesswork.  
>  
> **It's easy:** Just load all the files listed below, and you'll have everything you need to understand, contribute, and make great decisions.  
>  
> _Whether you're new or returning, the Memory Bank is your friendly guide to the project!_

---

## Quickstart: Loading the Memory Bank

**For AI Assistants:**
- Start by reading this README.md—it's your map to all required context.
- **Next, read [foundation/README.md](foundation/README.md)** for guidance on foundation documents, then load all foundation files (01-07) to understand project fundamentals.
- **Then, read [context/README.md](context/README.md)** for guidance on context documents, then load all context files (01-03) to understand current project state.
- Load additional files from workflows, agents, and ticket-administration as needed for your task.
- **Always update context documents as you work** to keep project state current.
- If you ever feel lost, just come back here for a refresher!

**For Developers:**
- Begin with this README.md for a high-level overview.
- **New to the project?** Read [foundation/README.md](foundation/README.md) first, then read foundation documents (01-07) in the recommended order.
- **Ready to start work?** Read [context/README.md](context/README.md), then check context documents (01-03) for current state.
- Reference workflows and agents for development processes and role responsibilities.
- Keep context documents updated as you work!

---

This memory bank contains essential context and documentation for the [PROJECT_NAME] project.

> **Ticket-Driven Documentation Policy with Story Point Estimation:**
> For every task or change, a valid ticket number AND story point estimate must be provided. All work must be documented and tracked under the corresponding ticket in the `ticket-administration/` section, following the story point estimation methodology defined in the project brief and ticket administration strategy for traceability and compliance.

## Contents

### Foundation

**Start here for project fundamentals! Read [foundation/README.md](foundation/README.md) first for guidance on how to use these documents.**

- **[foundation/README.md](foundation/README.md)** ⭐ **START HERE**
  Guide to foundation documents, what they contain, and how to use them
- **[foundation/01-project-overview.md](foundation/01-project-overview.md)**
  High-level project purpose, structure, and module organization
- **[foundation/02-technology-stack.md](foundation/02-technology-stack.md)**
  Complete technology stack including frameworks, libraries, and versions
- **[foundation/03-module-architecture.md](foundation/03-module-architecture.md)**
  Detailed module architecture, naming conventions, and dependencies
- **[foundation/04-build-configuration.md](foundation/04-build-configuration.md)**
  Build configuration, versioning strategy, and project settings
- **[foundation/05-product-context.md](foundation/05-product-context.md)**
  Product purpose, user experience, and problem context
- **[foundation/06-project-brief.md](foundation/06-project-brief.md)**
  Project requirements and goals (source of truth for project scope)
- **[foundation/07-tech-context.md](foundation/07-tech-context.md)**
  Technologies, setup, constraints, and dependencies

### Context

**Dynamic project state—updated frequently! Read [context/README.md](context/README.md) first to understand how to use these living documents.**

- **[context/README.md](context/README.md)** ⭐ **START HERE**
  Guide to context documents, what they contain, and how to keep them current
- **[context/01-active-context.md](context/01-active-context.md)**
  Current work focus, recent changes, next steps, and active decisions (update daily)
- **[context/02-progress.md](context/02-progress.md)**
  What works, what's left, current status, and known issues (update weekly)
- **[context/03-system-patterns.md](context/03-system-patterns.md)**
  System architecture, design patterns, and key technical decisions (update as needed)

### Ticket Administration

- **[ticket-administration/README.md](ticket-administration/README.md)**
  Overview of ticket management and story point estimation methodology
- **[ticket-administration/ticket-templates.md](ticket-administration/02-ticket-templates.md)**
  Standardized templates for user stories, bugs, and technical tasks with story point estimation
- **[ticket-administration/best-practices.md](ticket-administration/01-best-practices.md)**
  Comprehensive guide to story point estimation, Planning Poker, and velocity tracking
- **[ticket-administration/workflows.md](ticket-administration/04-workflows.md)**
  Complete ticket lifecycle from backlog to completion with estimation processes
- **[ticket-administration/roles-and-permissions.md](ticket-administration/03-roles-and-permissions.md)**
  Team roles, responsibilities, and permissions in story point estimation

### Agents

- **[agents/README.md](agents/README.md)**
  Overview of team roles, responsibilities, and agent principles
- **[agents/01-developer-agent.md](agents/01-developer-agent.md)**
  Developer role, daily responsibilities, coding practices, and testing patterns
- **[agents/02-reviewer-agent.md](agents/02-reviewer-agent.md)**
  Code reviewer guidelines, standards, and review practices
- **[agents/03-qa-agent.md](agents/03-qa-agent.md)**
  QA and testing responsibilities, procedures, and quality standards
- **[agents/04-ai-assistant-agent.md](agents/04-ai-assistant-agent.md)**
  How to work effectively with Claude Code and AI assistants
- **[agents/05-documentation-agent.md](agents/05-documentation-agent.md)**
  Documentation maintenance responsibilities and practices
- **[agents/06-automation-agent.md](agents/06-automation-agent.md)**
  CI/CD, automation tooling, and infrastructure responsibilities
- **[agents/07-claude-code-agents.md](agents/07-claude-code-agents.md)**
  How to use Claude Code custom agents and Task tool integration

### Workflows

- **[workflows/README.md](workflows/README.md)**
  Overview of development workflows and workflow principles
- **[workflows/01-development-workflow.md](workflows/01-development-workflow.md)**
  Day-to-day development process, local setup, and coding standards
- **[workflows/02-code-review-workflow.md](workflows/02-code-review-workflow.md)**
  Pull request creation, review process, and approval procedures
- **[workflows/03-testing-workflow.md](workflows/03-testing-workflow.md)**
  Testing strategy, test execution, and quality assurance
- **[workflows/04-deployment-workflow.md](workflows/04-deployment-workflow.md)**
  Build, release, and deployment procedures
- **[workflows/05-documentation-workflow.md](workflows/05-documentation-workflow.md)**
  How to maintain memory bank and project documentation
- **[workflows/06-collaboration-workflow.md](workflows/06-collaboration-workflow.md)**
  Team communication, sync patterns, and decision-making

*All files are grouped by purpose for easier search and maintenance. Update this index when adding or moving documentation.*

## Managing the Memory Bank Folder Structure

- **Folder Purpose:**
  - `foundation/`: Project-wide and foundational documentation (overview, tech stack, architecture, requirements, product context, tech context).
  - `context/`: Living project context, active work, progress, and system patterns.
  - `ticket-administration/`: All knowledge, workflows, templates, and best practices for ticket management and administration.
  - `agents/`: Team role definitions, agent responsibilities, and guidelines for each role (developer, reviewer, QA, etc.).
  - `workflows/`: Development process workflows (development, code review, testing, deployment, documentation, collaboration).

- **Adding Files:**  
  Place new documentation in the appropriate folder based on its purpose. Update the "Contents" section above to include the new file and path.

- **Ticket-Driven Documentation:**  
  Every new task, change, or documentation update must be associated with a ticket number. Create or update a subfolder in `ticket-administration/` for the ticket, and document all related work, context, and decisions there.

- **Moving/Renaming Files or Folders:**  
  When reorganizing, always update:
    - The "Contents" section in this README.md
    - Any diagrams or references in `.clinerules` or other documentation
    - Internal links in all affected files

- **Canonical Index:**  
  This README.md is the authoritative index for the memory bank. All changes to the folder structure must be reflected here.

- **Consistency:**  
  Keep folder and file names descriptive and consistent. Group by purpose for clarity and ease of search.

## Usage Guidelines

### For AI Assistants
- **The memory bank is your source of truth and main entry point for all project knowledge. All AI assistants must always load and reference the memory bank as the canonical context for all tasks.**
- **Loading sequence (CRITICAL - follow this order)**:
  1. This README.md (the index - you are here)
  2. **[foundation/README.md](foundation/README.md)** (your guide to foundation) + all foundation docs 01-07 (stable fundamentals)
  3. **[context/README.md](context/README.md)** (your guide to context) + all context docs 01-03 (current state) ← **THIS IS YOUR STARTING POINT FOR CURRENT WORK**
  4. Relevant workflows, agents, and ticket documentation as needed for your specific task
- **Context is your starting point**: After loading foundation, always check context documents to understand what's happening right now
- Always require a ticket number AND story point estimate for every new task or change, and prompt the user if not provided
- All work must be documented and tracked under the corresponding ticket in `ticket-administration/`, following the ticket administration strategy with proper story point estimation
- **Update context documents as you work (CRITICAL)**:
  - Update `context/01-active-context.md` when starting/completing work (daily)
  - Update `context/02-progress.md` weekly or when status changes
  - Update `context/03-system-patterns.md` when making architectural decisions
- Keep all documentation updated as the project evolves

### For Developers
- **New to the project?**
  1. Start with [foundation/README.md](foundation/README.md) for guidance, then read foundation documents (01-07) in order
  2. Next, read [context/README.md](context/README.md) for guidance, then read context documents (01-03) to understand current state
- **Starting work?** Check [context/01-active-context.md](context/01-active-context.md) first to see what's happening right now
- Always provide a ticket number AND story point estimate for every new task or change, and ensure all work is documented and tracked under the corresponding ticket in `ticket-administration/`, following the story point estimation methodology
- Reference the estimation guidelines in `foundation/06-project-brief.md` for all task planning
- **Update context as you work**: Keep active context, progress, and system patterns current (see [context/README.md](context/README.md) for guidelines)
- Reference [workflows/01-development-workflow.md](workflows/01-development-workflow.md) for day-to-day development practices

## Document Maintenance

This memory bank should be updated when:
- New major modules are added to the project
- Technology stack changes significantly
- Build configuration is modified
- Migration plans are adjusted or completed
- New architectural decisions are made

Last Updated: [YYYY-MM-DD]

## Project Context

**[PROJECT_NAME]** is a [brief description of your project, its purpose, and main features].

---
