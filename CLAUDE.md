# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a documentation template repository for AI assistant (Claude Code) knowledge management and project guidance. It provides structured templates and patterns for maintaining consistent, AI-friendly project documentation across projects.

## Development Environment

- **Tool Manager**: mise is used for managing development tools
- **Node.js**: Managed via mise shims (`/Users/ivan.santiago/.local/share/mise/shims/node`)
- **IDE Support**: VSCode and IntelliJ IDEA configurations included

## Core Architecture

### Memory Bank Strategy
This repository implements a "memory-first" approach where AI assistants must:
1. Always start by reading `memory-bank/README.md`
2. Follow ticket-driven documentation workflows
3. Maintain consistent template-based structure

### Template Structure
```
memory-bank-template/
├── foundation/          # Core project documentation
│   ├── 01-project-overview.md
│   ├── 02-technology-stack.md
│   ├── 03-module-architecture.md
│   ├── 04-build-configuration.md
│   ├── 05-product-context.md
│   ├── 06-project-brief.md
│   └── 07-tech-context.md
├── context/            # Dynamic work tracking
│   ├── 01-active-context.md
│   ├── 02-progress.md
│   └── 03-system-patterns.md
├── ticket-administration/  # Ticket management and workflows
│   ├── 01-best-practices.md
│   ├── 02-ticket-templates.md
│   ├── 03-roles-and-permissions.md
│   ├── 04-workflows.md
│   └── README.md
├── agents/             # Team role definitions and responsibilities
│   ├── 01-developer-agent.md
│   ├── 02-reviewer-agent.md
│   ├── 03-qa-agent.md
│   ├── 04-ai-assistant-agent.md
│   ├── 05-documentation-agent.md
│   ├── 06-automation-agent.md
│   ├── 07-claude-code-agents.md
│   └── README.md
└── workflows/          # Development process workflows
    ├── 01-development-workflow.md
    ├── 02-code-review-workflow.md
    ├── 03-testing-workflow.md
    ├── 04-deployment-workflow.md
    ├── 05-documentation-workflow.md
    ├── 06-collaboration-workflow.md
    └── README.md
```

## Key Files and Their Purpose

- **`CLAUDE_TEMPLATE.md`**: Master template for Claude Code guidance across projects
- **`.clinerules`**: Detailed rules for Cline AI assistant workflows
- **`memory-bank-template/README.md`**: Template usage guide and index
- **`.aiignore`**: AI tool ignore patterns for clean analysis

## AI Assistant Integration

### Required Workflow
1. **Memory Bank First**: Always read memory bank documentation before starting work
   - Start with `memory-bank/README.md` (the index)
   - Then read `memory-bank/foundation/README.md` (foundation guide)
   - Load all foundation documents in the recommended order
   - Then read `memory-bank/context/README.md` (context guide)
   - Load all context documents to understand current state
2. **Ticket Association**: All work must reference valid ticket numbers
3. **Documentation Updates**: Update relevant template files for significant changes
4. **Template Consistency**: Follow established patterns across foundation and context layers
5. **Agent & Workflow Awareness**: Understand team roles and development workflows before executing tasks

### Planning and Acting Modes
- **Planning Mode**: Use when understanding requirements and creating implementation strategies
- **Acting Mode**: Use when executing specific development tasks
- **Memory Updates**: Trigger when project structure or core patterns change

### Agent System
The template includes comprehensive agent definitions for different team roles:
- **Developer Agent**: Implementation, coding standards, testing practices
- **Reviewer Agent**: Code review guidelines and quality checks
- **QA Agent**: Testing strategies and quality assurance procedures
- **AI Assistant Agent**: Guidelines for AI tools working with the codebase
- **Documentation Agent**: Memory bank maintenance and documentation updates
- **Automation Agent**: CI/CD, build automation, and infrastructure
- **Claude Code Agents**: Integration with Claude Code Task tool and custom agents

### Workflow System
The template provides structured workflows for all development activities:
- **Development Workflow**: Daily coding practices and local development setup
- **Code Review Workflow**: PR creation, review standards, and approval processes
- **Testing Workflow**: Test strategies, execution, and quality gates
- **Deployment Workflow**: Build, release, and deployment procedures
- **Documentation Workflow**: How to maintain the memory bank and project docs
- **Collaboration Workflow**: Team communication patterns and decision-making

## Development Commands

Commands are expected to follow mise patterns:
```bash
mise run <task>          # Execute specific development tasks
```

Note: This template repository doesn't have traditional build/test commands as it focuses on documentation structure rather than source code compilation.