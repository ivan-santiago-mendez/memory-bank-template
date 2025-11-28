# CLAUDE.md Template

Copy this template to your project root as `CLAUDE.md` and customize with your project details.

---

# CLAUDE.md

Instructions for Claude Code on how to work in the [PROJECT_NAME] repository.

## Purpose
[Brief 1-2 sentence description of what this project does]

**Available Commands**:
- `[command]` - [Description]
- `[command]` - [Description]
- `[command]` - [Description]

## Application Overview

**What this service does**: [Detailed description]

**Prerequisites for Running**:
- ✅ **Required**: [Prerequisite 1] → `[command to start]`
- ✅ **Required**: [Prerequisite 2] → `[setup instructions]`
- ⚠️ **Optional**: [Optional services for full functionality]

**First Time Setup**: See `memory-bank/01-workflows/project-setup-workflow.md`

**Key Technologies**:
- **[Technology 1]** - [Purpose]
- **[Technology 2]** - [Purpose]
- **[Technology 3]** - [Purpose]

**Module Structure**: [Describe your module organization]

**External Dependencies**: [List key external services]

## Quick Reference

### Development Operations

| Task | Command/Workflow |
|------|------------------|
| **Setup & Initialization** | |
| First-time project setup | `memory-bank/01-workflows/project-setup-workflow.md` |
| Initialize dependencies | `[command]` |
| **Build & Test** | |
| Build project | `[command]` |
| Run tests | `[command]` |
| Run single test | `[command]` |
| **Run Application** | |
| Start application | `[command]` |
| Check health | `[command]` |

### Workflow Operations

| Task | Workflow File |
|------|---------------|
| **Ticket Operations** | |
| Draft ticket in context | `memory-bank/06-context/workflows.md#workflow-1` |
| Create ticket | `memory-bank/01-workflows/ticket-creation-workflow.md` |
| Transition ticket | `memory-bank/01-workflows/ticket-transition-workflow.md` |
| **Git Operations** | |
| Create commit | `memory-bank/01-workflows/git-commit-workflow.md` |
| Create PR | `memory-bank/01-workflows/git-pr-workflow.md` |
| **Code Quality** | |
| Review code | `memory-bank/01-workflows/code-review-workflow.md` |
| Run tests | `memory-bank/01-workflows/testing-workflow.md` |

## Configuration

**Ticket System**: [Jira/Linear/GitHub Issues/etc.]
**Cloud ID** (if Jira): [your-cloud-id]
**Default Project**: [PROJECT_KEY]
**Default Issue Type**: [Task/Story/Bug]

## Memory Bank

**All knowledge lives in `memory-bank/`**

Read `memory-bank/README.md` first for complete structure.

**Quick access by folder**:
- `memory-bank/01-workflows/` - Step-by-step procedures for all tasks
- `memory-bank/02-templates/` - Templates for tickets, PRs, commits
- `memory-bank/03-component-architecture/` - Codebase structure and design
- `memory-bank/04-standards/` - Coding standards
- `memory-bank/05-cache/` - Cached API data
- `memory-bank/06-context/` - Session-specific work tracking
- `memory-bank/07-scripts-documentation/` - Shell script documentation
- `memory-bank/08-agents/` - Sub-agent definitions
- `memory-bank/09-team-processes/` - Team collaboration processes
- `memory-bank/ticket-administration/` - Archived completed tickets

## Request Disambiguation

**Ambiguous user requests require clarification before proceeding:**

| User Says | Could Mean | Ask User |
|-----------|------------|----------|
| "Create a ticket" | Draft locally OR create in ticket system | "Do you want to draft requirements locally first, or create the ticket directly?" |
| "Update the ticket" | Add comment OR transition OR edit fields | "How would you like to update it: add a comment, change status, or edit fields?" |
| "Create a PR" | With draft description OR user-provided body | "Should I generate a PR description, or do you have one ready?" |

## Sub-Agent Auto-Invocation

**IMPORTANT**: Before executing certain operations, Claude Code MUST check `memory-bank/08-agents/auto-invocation-rules.md` and invoke the appropriate sub-agent as a quality gate.

**Mandatory Auto-Invocation Triggers**:
1. **Before creating PR** → Invoke `code-reviewer` to check code against standards
2. **After writing new service/class** → Invoke `test-generator` to create tests
3. **Before creating ticket** → Invoke `ticket-creator` to validate template
4. **When touching auth/security code** → Invoke `security-auditor` to check vulnerabilities

**Full Documentation**: `memory-bank/08-agents/auto-invocation-rules.md`

## General Rules

### Execution Rules
1. **Read workflows first** - Before any operation, read the corresponding workflow file
2. **Use templates** - When creating artifacts, use templates from `memory-bank/02-templates/`
3. **Auto-invoke sub-agents** - Check `memory-bank/08-agents/auto-invocation-rules.md` before critical operations

### User Interaction Rules
4. **No confirmations** - Execute operations without confirmation AFTER disambiguation
5. **Minimal output** - Return concise results (e.g., "Created PROJ-123")
6. **Ask for commit messages** - Do NOT auto-generate, always ask user

### Prerequisites & Setup Rules
7. **Before suggesting "run application"** - Check prerequisites:
   - [List your prerequisites and how to check them]

### Quality Rules
8. **Reference memory bank** - Don't duplicate knowledge, always reference existing documentation
9. **Validate against standards** - Check `memory-bank/04-standards/` before claiming code is correct

## More Information

- **Setup**: `README.md`
- **Configuration**: `[configuration file or doc]`
- **Memory Bank**: `memory-bank/README.md`

---

**Customization Instructions**:
1. Replace all `[placeholders]` with your project-specific information
2. Update commands with your actual task runner commands
3. Add/remove sections based on your project needs
4. Keep this file in sync with your memory-bank documentation
5. Delete this instruction section when done customizing