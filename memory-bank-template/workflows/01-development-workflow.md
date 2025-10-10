# Development Workflow

This document defines the day-to-day development workflow for the intapi-assistant project.

## Daily Development Cycle

### 1. Environment Setup (First Time / After Reset)

```bash
# Start Docker Desktop
mise run start_docker_service

# Start MySQL and Redis containers
mise run start_docker_components

# Verify Docker services are running
docker ps

# If needed, grant MySQL privileges (first time only)
mise run mysql_shell
# Then in MySQL shell:
# CREATE USER IF NOT EXISTS 'root'@'%' IDENTIFIED BY 'password';
# GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
# FLUSH PRIVILEGES;
# exit
```

### 2. Start Your Development Session

```bash
# Pull latest changes from upstream/main
git checkout main
git pull upstream main

# Create or switch to your feature branch
git checkout -b AIT-XXX-VX-feature-description

# Load memory bank context (for AI assistants)
# Read: memory-bank/README.md and all referenced documents
# Read: memory-bank/ticket-administration/JIRA/AIT-XXX/

# Build the project
mise run build

# Start the application
mise run bootRun
# Application runs on port 8171

# In another terminal, verify health
mise run health_check_api
```

### 3. Active Development

```bash
# Make code changes in your IDE
# Follow coding standards from CLAUDE.md

# Run tests frequently
mise run test

# Run specific test class
mise run test_one <TestClassName>

# Check application logs for errors
# Logs appear in terminal running bootRun
```

### 4. Update Documentation

As you code, update:
- Memory bank ticket folder: `memory-bank/ticket-administration/JIRA/AIT-XXX/VX/`
- Code comments and inline documentation
- Update `memory-bank/context/01-active-context.md` if making architectural changes
- Update `memory-bank/context/02-progress.md` with what works and what's left

### 5. Commit Changes

```bash
# Stage changes
git add .

# Commit with ticket reference
git commit -m "feat(AIT-XXX): Brief description of change

Detailed explanation if needed.

🤖"

# Push to remote
git push origin AIT-XXX-VX-feature-description
```

### 6. End of Day / Session Cleanup

```bash
# Stop the Spring Boot application (Ctrl+C in bootRun terminal)

# Stop Docker services
mise run stop_docker_components

# Commit any work-in-progress
git add .
git commit -m "wip: AIT-XXX: Work in progress - <what you're working on>"
git push origin AIT-XXX-VX-feature-description
```

## Feature Development Workflow

### Step 1: Pick a Ticket
1. Choose ticket from backlog or sprint
2. Assign ticket to yourself in JIRA
3. Move ticket to "In Progress"
4. Note ticket number (e.g., AIT-XXX)

### Step 2: Prepare Development Environment
```bash
# Create feature branch from upstream main
git checkout main
git pull upstream main
git checkout -b AIT-XXX-V1-descriptive-name

# Create ticket documentation folder
mkdir -p memory-bank/ticket-administration/JIRA/AIT-XXX/V1
```

### Step 3: Document Ticket Context
Create `memory-bank/ticket-administration/JIRA/AIT-XXX/README.md`:
```markdown
# AIT-XXX: Ticket Title
## Version: X
## Context
[Brief description of the task]

## Approach
[Your implementation strategy]

## Progress
- [ ] Task 1
- [ ] Task 2

## Notes
[Any decisions, challenges, or learnings]
```

### Step 4: Implement Changes
1. Write code following Groovy guidelines from CLAUDE.md
2. Add/update tests
3. Use `mise run` commands for all operations
4. Commit frequently with meaningful messages
5. Update ticket documentation as you progress

### Step 5: Verify Implementation
```bash
# Run all tests
mise run test

# Build the project
mise run build

# Start application and verify manually
mise run bootRun
# Test your changes via API calls or UI

# Stop application
# Ctrl+C

# Clean up
mise run stop_docker_components
```

### Step 6: Prepare for Code Review
1. Update ticket status in JIRA
2. Create executive summary in ticket comments
3. Ensure all tests pass
4. Update relevant memory bank documentation
5. Create pull request (see [02-code-review-workflow.md](02-code-review-workflow.md))

## Bug Fix Workflow

### Quick Bug Fix Process
```bash
# 1. Reproduce the bug locally
mise run bootRun
# Test the failing scenario

# 2. Create bug fix branch
git checkout main
git pull origin main
git checkout -b AIT-XXX-fix-bug-description

# 3. Write failing test first (TDD approach)
# Add test that demonstrates the bug

# 4. Fix the bug
# Make minimal changes to fix the issue

# 5. Verify fix
mise run test_one <BugTestClass>
mise run test

# 6. Document in ticket
# Update memory-bank/ticket-administration/JIRA/AIT-XXX/V1/README.md

# 7. Commit and push
git add .
git commit -m "fix(AIT-XXX): Fixed [bug description]

- Added test to reproduce bug
- Fixed [specific issue]
- Verified with manual and automated tests

🤖"
git push origin AIT-XXX-fix-bug-description
```

## Working with AI Assistants (Claude Code)

### AI Assistant Development Loop
```markdown
# 1. ALWAYS load memory bank first
Read: memory-bank/README.md
Read: All foundation documents
Read: Relevant ticket documentation

# 2. Start with context
"I'm working on AIT-XXX. Let me load the ticket context first."
[Load memory-bank/ticket-administration/JIRA/AIT-XXX/]

# 3. Plan before executing
"Here's my plan to approach this task: [explain plan]"
[Get user confirmation if needed]

# 4. Use mise tasks
"I'll use mise run build instead of gradle build directly"

# 5. Document as you go
"I'll update the ticket README with this decision"
[Update memory-bank docs]

# 6. Create executive summaries
"Let me create an executive summary for the ticket comment"
[Create concise, non-technical summary, not so much formatting]
```

## Common Development Scenarios

### Scenario: Database Schema Change
```bash
# 1. Create Liquibase migration
# Add new changeset to appropriate changelog file

# 2. Restart Docker to apply migration
mise run restart_docker_components

# 3. Update TDO entities if needed
# Modify Groovy entity classes in tdo/src/main/groovy/

# 4. Test the migration
mise run bootRun
# Verify schema changes in MySQL

# 5. Document in ticket
```

### Scenario: Adding New REST Endpoint
```bash
# 1. Add endpoint in server module
# server/src/main/groovy/com/taulia/assistant/server/resources/

# 2. Add service logic in services module
# services/src/main/groovy/com/taulia/assistant/services/

# 3. Write integration test
# server/src/test/groovy/.../ResourceIntegrationTest.groovy

# 4. Test locally
mise run bootRun
curl -X POST http://localhost:8171/api/endpoint -H "Content-Type: application/json" -d '{...}'

# 5. Update API documentation
```

### Scenario: Adding New Dependency
```bash
# 1. Add dependency to build.gradle
# In appropriate module's build.gradle

# 2. Rebuild project
mise run build

# 3. Document in foundation/02-technology-stack.md
# Add new library and version

# 4. Update CLAUDE.md if it affects development workflow
```

## Best Practices

### Code Quality
- Follow Groovy guidelines from CLAUDE.md
- Use interfaces for data structures
- Prefer immutable data
- Write descriptive variable and method names
- Add comments for complex logic

### Testing
- Write tests alongside code
- Aim for meaningful test coverage
- Test edge cases and error scenarios
- Use meaningful test names

### Commits
- Commit frequently with small, logical changes
- Use conventional commit format (feat:, fix:, docs:, etc.)
- Always reference ticket number
- Include Claude Code attribution when applicable

### Documentation
- Update memory bank as you code
- Keep ticket documentation current
- Document decisions and trade-offs
- Update progress regularly

## Troubleshooting

### Application Won't Start
```bash
# Check Docker services
docker ps

# Restart Docker components
mise run restart_docker_components

# Check MySQL connection
mise run mysql_shell

# Review application logs for specific errors
```

### Tests Failing
```bash
# Run specific test for debugging
mise run test_one <TestClassName>

# Check test logs for details
# Review build/test-results/

# Verify Docker services are running
docker ps
```

### Port Already in Use
```bash
# Find process using port 8171
lsof -i :8171

# Kill the process if needed
kill -9 <PID>

# Or use a different port in application-dev.gconf
```

---

_Last updated: 2025-10-09_