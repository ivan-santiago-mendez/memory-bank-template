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
│   └── 04-build-configuration.md
└── context/            # Dynamic work tracking
    ├── activeContext.md
    ├── progress.md
    └── systemPatterns.md
```

## Key Files and Their Purpose

- **`CLAUDE_TEMPLATE.md`**: Master template for Claude Code guidance across projects
- **`.clinerules`**: Detailed rules for Cline AI assistant workflows
- **`memory-bank-template/README.md`**: Template usage guide and index
- **`.aiignore`**: AI tool ignore patterns for clean analysis

## AI Assistant Integration

### Required Workflow
1. **Memory Bank First**: Always read memory bank documentation before starting work
2. **Ticket Association**: All work must reference valid ticket numbers
3. **Documentation Updates**: Update relevant template files for significant changes
4. **Template Consistency**: Follow established patterns across foundation and context layers

### Planning and Acting Modes
- **Planning Mode**: Use when understanding requirements and creating implementation strategies
- **Acting Mode**: Use when executing specific development tasks
- **Memory Updates**: Trigger when project structure or core patterns change

## Development Commands

Commands are expected to follow mise patterns:
```bash
mise run <task>          # Execute specific development tasks
```

Note: This template repository doesn't have traditional build/test commands as it focuses on documentation structure rather than source code compilation.