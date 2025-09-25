# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## AI Assistant Memory Management

**Important**: Claude's memory resets completely between sessions. This requires reliance on the Memory Bank for project continuity. Always begin every task by reading the Memory Bank index (`memory-bank/README.md`) to understand the current project state and required documentation.

## Project Overview

[PROJECT_NAME] is a [FRAMEWORK/TECHNOLOGY]-based service that [PRIMARY_PURPOSE]. It serves as [ROLE_IN_ECOSYSTEM] for [TARGET_USERS], managing [KEY_RESPONSIBILITIES] while integrating with [EXTERNAL_SERVICES].

## Development Workflow

### Required Tools
- **All commands must be executed via `mise run <task>`** for reproducibility
- [LANGUAGE_VERSION] ([SPECIFIC_VERSION]) managed by mise
- [BUILD_TOOL] [VERSION] managed by mise
- Docker with [REQUIRED_SERVICES_AND_VERSIONS]

### Essential Commands
```bash
# Build the project
mise run build

# Run tests (excludes integration and functional tests by default)
mise run test

# Run a specific test class
mise run test_one <TestClassName>

# Start the application (runs on port [PORT])
mise run [START_COMMAND]

# Health check the running application
mise run health_check_api

# Docker services management
mise run start_docker_components
mise run stop_docker_components
mise run restart_docker_components

# Database access
mise run [DATABASE_SHELL_COMMAND]

# [ADD_PROJECT_SPECIFIC_COMMANDS]
```

### Test Execution
- Default `test` excludes integration tests (`[INTEGRATION_TEST_PATTERN]`)
- Functional tests (`[FUNCTIONAL_TEST_PATTERN]`) only run when `[FUNCTIONAL_TEST_FLAG]`
- Integration and functional tests require [EXTERNAL_DEPENDENCIES_FOR_TESTS]

## Architecture

### Module Structure
- **[MODULE_1]/**: [MODULE_1_PURPOSE]
- **[MODULE_2]/**: [MODULE_2_PURPOSE]
- **[MAIN_MODULE]/**: [MAIN_MODULE_PURPOSE] (`[MAIN_APPLICATION_CLASS]`)
- **[SERVICE_MODULE]/**: [SERVICE_MODULE_PURPOSE]
- **[DATA_MODULE]/**: [DATA_MODULE_PURPOSE]
- **memory-bank/**: Knowledge base with documentation, prompts, and ticket definitions

### Key Dependencies
- [PRIMARY_FRAMEWORK] [VERSION] for [PRIMARY_PURPOSE]
- [WEB_FRAMEWORK] for [WEB_PURPOSE]
- [COMPANY_SPECIFIC_LIBRARIES] for consistent configuration
- Integration with [EXTERNAL_SERVICE_1], [EXTERNAL_SERVICE_2], and [EXTERNAL_SERVICE_3]

### Technology Stack
- **Language**: [PRIMARY_LANGUAGE] (primary), with some [SECONDARY_LANGUAGE] generated code
- **Framework**: [MAIN_FRAMEWORK]
- **Build**: [BUILD_SYSTEM] with [COMPANY_PLUGINS]
- **Database**: [DATABASE] with [MIGRATION_TOOL] migrations
- **Cache**: [CACHE_SOLUTION]
- **Messaging**: [MESSAGE_BROKER]
- **Testing**: [TEST_FRAMEWORKS] with [CONTAINER_TESTING_TOOL]

## Configuration

### Required Environment Variables
Configure in `[CONFIG_FILE_PATH]` for local development:
```properties
[ENV_VAR_1]=[DESCRIPTION]
[ENV_VAR_2]=[DESCRIPTION]
[ENV_VAR_3]=[DESCRIPTION]
[AUTH_CONFIG]=[AUTH_DESCRIPTION]
[API_ENDPOINTS]=[ENDPOINT_DESCRIPTION]
[TIMEOUT_SETTINGS]=[TIMEOUT_DESCRIPTION]
```

### Database Setup
```sql
CREATE DATABASE `[DATABASE_NAME]` /*!40100 DEFAULT CHARACTER SET [CHARSET] COLLATE [COLLATION] */ /*!80016 DEFAULT ENCRYPTION='N' */;
```

## Memory Bank Strategy

**The memory bank (`./memory-bank/`) is the source of truth and main entry point for all project knowledge.** All AI assistants and developers must always load and reference the memory bank as the canonical context for all tasks.

### Core Workflow Requirements
- **Always start by reading `memory-bank/README.md`** - This is the canonical index and usage guide for all memory bank files
- **Memory resets between sessions**: Claude relies ENTIRELY on the Memory Bank to understand project state and continue work effectively
- **Required reading**: Load ALL files listed in the memory bank README Contents section for full project context

### Usage Guidelines
- **For AI Assistants**: Always load the memory bank first - start with `./memory-bank/README.md` as your map to all required context
- **Ticket-Driven Documentation**: Every task/change requires a valid [TICKET_SYSTEM] ticket number. All work must be documented and tracked under the corresponding ticket in `memory-bank/ticket-administration/`
- **Documentation Updates**: Memory Bank updates occur when:
  - Discovering new project patterns
  - After implementing significant changes
  - When user requests with **update memory bank** (MUST review ALL files)
  - When context needs clarification

### Memory Bank Structure (Core Files)
- **README.md**: Canonical index and usage guide for the memory bank
- **foundation/**: Project-wide documentation
  - `projectbrief.md`: Foundation document that shapes all other files
  - `productContext.md`: Why this project exists and user experience goals
  - `techContext.md`: Technologies, setup, constraints, dependencies
- **context/**: Living project context
  - `activeContext.md`: Current work focus, recent changes, next steps
  - `systemPatterns.md`: System architecture and design patterns
  - `progress.md`: What works, what's left to build, current status
- **ticket-administration/**: All ticket workflows, templates, and best practices
- **prompts/**: [DOMAIN_SPECIFIC] prompts, glossaries, and [TICKET_SYSTEM] ticket definitions

### Essential Memory Bank Files
- `memory-bank/README.md` - **ALWAYS READ FIRST** - Index and usage guide
- `foundation/projectbrief.md` - Foundation document and project scope
- `foundation/productContext.md` - Project purpose and user experience
- `foundation/techContext.md` - Technologies and development setup
- `context/activeContext.md` - Current work focus and decisions
- `context/systemPatterns.md` - Architecture and design patterns
- `context/progress.md` - Current status and evolution
- `ticket-administration/README.md` - Ticket administration strategy

## Development Guidelines

### Core Workflows for AI Assistants

#### Planning Mode
1. Read Memory Bank index (`memory-bank/README.md`)
2. Check if required files are complete
3. For ticket-driven work, reference relevant documentation in `memory-bank/ticket-administration/`
4. Develop strategy and present approach

#### Acting Mode
1. Check Memory Bank for current context
2. Update documentation as needed
3. Execute task
4. Document changes and patterns discovered

### Development Rules
- **All work must be associated with a valid [TICKET_SYSTEM] ticket** - document in `memory-bank/ticket-administration/`
- **Always use the Memory Bank as source of truth** for project context, requirements, and workflows
- **Document all changes and decisions** in appropriate Memory Bank files
- Use existing [COMPANY_NAME] patterns and libraries (check neighboring files and [BUILD_FILE])
- Follow the modular architecture - [DEPENDENCY_HIERARCHY_RULES]
- Server runs on port [PORT] (configured in `[CONFIG_FILE_LOCATION]`)
- API endpoints require [COMPANY_NAME] headers ([REQUIRED_HEADERS])

## Key Integration Points

- **[PRIMARY_EXTERNAL_SERVICE]**: [INTEGRATION_DESCRIPTION]
- **[PROTOCOL/STANDARD]**: [PROTOCOL_DESCRIPTION] via `[ENDPOINT_PATTERN]` endpoints
- **External Services**: [SERVICE_1] ([PURPOSE]), [SERVICE_2] ([PURPOSE]), [SERVICE_3] ([PURPOSE])
- **Authentication**: [AUTH_SYSTEM] integration for security

# important-instruction-reminders
Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.