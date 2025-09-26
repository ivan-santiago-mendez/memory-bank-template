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
- Load every file listed in the "Contents" section below.  
- Use the folder structure and file descriptions to guide your exploration.
- If you ever feel lost, just come back here for a refresher!

**For Developers:**  
- Begin with this README.md for a high-level overview.
- Open each file in the "Contents" list to get the full project picture.
- Unsure where to start? Try the "project overview" or "active context" files first.

---

This memory bank contains essential context and documentation for the [PROJECT_NAME] project.

> **Ticket-Driven Documentation Policy with Story Point Estimation:**
> For every task or change, a valid ticket number AND story point estimate must be provided. All work must be documented and tracked under the corresponding ticket in the `ticket-administration/` section, following the story point estimation methodology defined in the project brief and ticket administration strategy for traceability and compliance.

## Contents

### Foundation

- **[foundation/01-project-overview.md](foundation/01-project-overview.md)**  
  High-level project purpose, structure, and module organization
- **[foundation/02-technology-stack.md](foundation/02-technology-stack.md)**  
  Complete technology stack including frameworks, libraries, and versions
- **[foundation/03-module-architecture.md](foundation/03-module-architecture.md)**  
  Detailed module architecture, naming conventions, and dependencies
- **[foundation/04-build-configuration.md](foundation/04-build-configuration.md)**  
  Build configuration, versioning strategy, and project settings
- **[foundation/projectbrief.md](foundation/projectbrief.md)**  
  Project requirements and goals (source of truth for project scope)
- **[foundation/productContext.md](foundation/productContext.md)**  
  Product purpose, user experience, and problem context
- **[foundation/techContext.md](foundation/techContext.md)**  
  Technologies, setup, constraints, and dependencies

### Context

- **[context/activeContext.md](context/activeContext.md)**  
  Current work focus, recent changes, next steps, and active decisions
- **[context/progress.md](context/progress.md)**  
  What works, what's left, current status, and known issues
- **[context/systemPatterns.md](context/systemPatterns.md)**  
  System architecture, design patterns, and key technical decisions

### Ticket Administration

- **[ticket-administration/README.md](ticket-administration/README.md)**
  Overview of ticket management and story point estimation methodology
- **[ticket-administration/ticket-templates.md](ticket-administration/ticket-templates.md)**
  Standardized templates for user stories, bugs, and technical tasks with story point estimation
- **[ticket-administration/best-practices.md](ticket-administration/best-practices.md)**
  Comprehensive guide to story point estimation, Planning Poker, and velocity tracking
- **[ticket-administration/workflows.md](ticket-administration/workflows.md)**
  Complete ticket lifecycle from backlog to completion with estimation processes
- **[ticket-administration/roles-and-permissions.md](ticket-administration/roles-and-permissions.md)**
  Team roles, responsibilities, and permissions in story point estimation

*All files are grouped by purpose for easier search and maintenance. Update this index when adding or moving documentation.*

## Managing the Memory Bank Folder Structure

- **Folder Purpose:**
  - `foundation/`: Project-wide and foundational documentation (overview, tech stack, architecture, requirements, product context, tech context).
  - `context/`: Living project context, active work, progress, and system patterns.
  - `memory-bank/ticket-administration/`: All knowledge, workflows, templates, and best practices for ticket management and administration.

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
- Always require a ticket number AND story point estimate for every new task or change, and prompt the user if not provided.
- All work must be documented and tracked under the corresponding ticket in `ticket-administration/`, following the ticket administration strategy with proper story point estimation.
- Reference the story point estimation methodology in `foundation/projectbrief.md` and `ticket-administration/` for all task planning.
- Always reference relevant memory bank documents when providing project-specific guidance
- Use the foundational docs (01-04) to understand project context before addressing specific issues
- Keep documentation updated as the project evolves

### For Developers
- Always provide a ticket number AND story point estimate for every new task or change, and ensure all work is documented and tracked under the corresponding ticket in `ticket-administration/`, following the story point estimation methodology.
- Reference the estimation guidelines in `foundation/projectbrief.md` for all task planning
- Start with project overview (01) for high-level understanding
- Reference technology stack (02) for dependency questions
- Use module architecture (03) for understanding project structure
- Consult migration documentation (if present) for upgrade tasks

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
