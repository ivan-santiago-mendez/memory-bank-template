# GitHub Copilot Agent Instructions for lib-test-tools

## Memory Bank: Project Knowledge Base

- The canonical entry point is [`memory-bank/README.md`](../memory-bank/README.md). Always read this file first—it indexes all required documentation and governs project knowledge.
- All documentation, including migration plans and ticket-driven work, is located under [`memory-bank/`](../memory-bank/).

## Core Workflows

### Planning
- Begin every task by reading the Memory Bank index (`memory-bank/README.md`).
- For ticket-driven work, reference the relevant ticket documentation in `memory-bank/ticket-administration/`.

### Acting
- Update documentation in the Memory Bank after significant changes or when new patterns are discovered.

## Documentation Update Triggers
- When discovering new project patterns
- After implementing significant changes
- When requested with **update memory bank** (review ALL files)
- When context needs clarification

## Key Files and Structure
- `memory-bank/README.md`: Documentation index and usage guide
- `memory-bank/foundation/`: Project overview, technology stack, architecture, build configuration
- `memory-bank/context/`: Current work focus, system patterns, progress tracking
- `memory-bank/ticket-administration/`: Ticket-driven documentation and migration knowledge

## Best Practices for Copilot Agents
- Always use the Memory Bank as the source of truth for project context, requirements, and workflows.
- Document all changes and decisions in the appropriate Memory Bank files.

**Start every session by reading `memory-bank/README.md`. This file defines the required documentation set, usage guidelines, and maintenance rules for the entire Memory Bank.**
