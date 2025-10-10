# Developer Agent

The Developer Agent is responsible for implementing features, fixing bugs, writing tests, and maintaining code quality.

## Core Responsibilities

### Daily Tasks
- [ ] Implement features according to ticket requirements
- [ ] Write tests for new code (unit, integration, functional)
- [ ] Fix bugs and address issues
- [ ] Update documentation alongside code changes
- [ ] Participate in code reviews
- [ ] Keep JIRA tickets up to date
- [ ] Communicate progress and blockers

### Code Quality
- [ ] Follow coding standards from CLAUDE.md
- [ ] Write clean, maintainable code
- [ ] Add meaningful comments for complex logic
- [ ] Ensure proper error handling and logging
- [ ] Keep functions small and focused
- [ ] Use appropriate design patterns

### Testing
- [ ] Write tests before or alongside code (TDD when appropriate)
- [ ] Ensure tests pass before committing
- [ ] Test edge cases and error scenarios
- [ ] Run full test suite before creating PR
- [ ] Verify application runs locally

## Development Workflow

### Starting a Task
1. **Pick Ticket from Sprint**
   - Review ticket description and acceptance criteria
   - Ask questions if anything is unclear
   - Estimate complexity (Low/Medium/High)
   - Assign to yourself and move to "In Progress"

2. **Create Feature Branch**
   ```bash
   git checkout main
   git pull origin main
   git checkout -b AIT-XXX-VX-descriptive-name
   ```

3. **Load Context**
   - Read memory-bank documentation
   - Check if ticket has folder in ticket-administration/
   - Review related code and recent changes
   - Understand the "why" not just the "what"

4. **Plan Approach**
   - Think through implementation
   - Consider architectural impact
   - Identify files to modify
   - Document plan in ticket README

### During Development
1. **Code in Small Increments**
   - Make small, logical changes
   - Commit frequently with clear messages
   - Test each change before moving forward

2. **Follow Standards**
   - Use Groovy for all new code
   - Follow naming conventions (camelCase, PascalCase)
   - Use interfaces for data structures
   - Prefer immutable data
   - Add logging at appropriate levels

3. **Write Tests**
   - Unit tests for business logic
   - Integration tests for module interactions
   - Functional tests for end-to-end flows
   - Aim for meaningful coverage, not just numbers

4. **Use Mise Tasks**
   ```bash
   # Build
   mise run build

   # Run tests
   mise run test

   # Run specific test
   mise run test_one <TestClassName>

   # Start application
   mise run bootRun

   # Health check
   mise run health_check_api
   ```

5. **Update Documentation**
   - Update ticket README with progress
   - Document decisions and rationale
   - Update memory bank if architectural changes
   - Add/update inline comments

### Completing a Task
1. **Final Verification**
   ```bash
   # Run full test suite
   mise run test

   # Build project
   mise run build

   # Manual testing
   mise run bootRun
   # Test your changes
   ```

2. **Code Self-Review**
   - Review your own changes first
   - Remove debug code and console logs
   - Check for TODO comments
   - Verify no secrets or hardcoded values
   - Ensure consistent formatting

3. **Prepare Documentation**
   - Complete ticket README
   - Update relevant memory bank sections
   - Verify all links work
   - Create executive summary for ticket

4. **Create Pull Request**
   - Follow [02-code-review-workflow.md](../workflows/02-code-review-workflow.md)
   - Write clear PR description
   - Request review from appropriate reviewers
   - Respond promptly to feedback

## Coding Standards

### Groovy Style
```groovy
// Use descriptive names
def calculateTotalRevenue(List<Invoice> invoices) {
    invoices.sum { it.amount }
}

// Prefer functional style
List<String> activeUsers = users.findAll { it.isActive }
                                 .collect { it.name }

// Use closures appropriately
def processResults = { result ->
    log.info("Processing: ${result}")
    transform(result)
}

// Handle nulls safely
def userName = user?.name ?: 'Unknown'

// Use Groovy truth
if (collection) {  // checks for null and empty
    // process collection
}
```

### Error Handling
```groovy
// Use try-catch for risky operations
try {
    def result = externalService.call()
    return processResult(result)
} catch (ServiceException e) {
    log.error("Service call failed: ${e.message}", e)
    throw new AssistantException("Unable to process request", e)
} catch (Exception e) {
    log.error("Unexpected error: ${e.message}", e)
    throw new AssistantException("Internal error", e)
}

// Validate inputs
def processRequest(String input) {
    if (!input?.trim()) {
        throw new InvalidDataException("Input cannot be empty")
    }
    // process...
}
```

### Logging
```groovy
// Use appropriate log levels
log.debug("Detailed information for debugging")
log.info("Normal operational messages")
log.warn("Warning messages for potentially harmful situations")
log.error("Error messages for error events", exception)

// Include context
log.info("Processing request for user: ${userId}, conversationId: ${conversationId}")

// Log method entry/exit for complex flows
log.debug("Entering processChat with input: ${input}")
def result = processChat(input)
log.debug("Exiting processChat with result: ${result}")
```

### Testing Patterns
```groovy
// Unit test with Spock
class ChatServiceSpec extends Specification {

    ChatService service
    PromptService mockPromptService

    def setup() {
        mockPromptService = Mock(PromptService)
        service = new ChatService(promptService: mockPromptService)
    }

    def "should process valid chat request"() {
        given: "a valid user input"
        def input = "test question"
        def conversationId = UUID.randomUUID().toString()

        and: "prompt service returns valid prompt"
        mockPromptService.getPrompt(_) >> new Prompt("test prompt")

        when: "processing chat request"
        def result = service.call(input, "CATEGORY", conversationId)

        then: "result is successful"
        result.success == true
        result.messages.size() > 0

        and: "prompt service was called"
        1 * mockPromptService.getPrompt("CATEGORY")
    }
}
```

## Common Tasks

### Adding a New Feature
1. Review ticket and acceptance criteria
2. Create feature branch
3. Design approach (update ticket README)
4. Implement incrementally with tests
5. Update documentation
6. Create PR and request review
7. Address feedback and merge
8. Update ticket status

### Fixing a Bug
1. Reproduce the bug locally
2. Write failing test that demonstrates bug
3. Fix the bug
4. Verify test now passes
5. Run full test suite
6. Update ticket with root cause
7. Create PR with fix
8. Merge and verify in environment

### Refactoring Code
1. Ensure tests exist for code being refactored
2. Make changes incrementally
3. Run tests after each change
4. Keep commits small and focused
5. Document why refactoring was needed
6. Get review before merging

## Working with Others

### Asking for Help
```markdown
# Be specific about the problem
"I'm working on AIT-XXX and trying to [goal].
I've tried [approach 1] and [approach 2], but [issue].

Context: [relevant information]
Error: [error message if applicable]

Could someone help me understand [specific question]?"
```

### Sharing Knowledge
- Document non-obvious solutions in ticket README
- Share discoveries in team channel
- Update memory bank with patterns
- Offer to pair on similar tasks

### Collaborating on Code
- Pair program on complex features
- Ask for design review before implementing
- Share WIP branches for early feedback
- Help review others' code

## Success Criteria

### You're a Good Developer When:
- ✅ Your code is clear and maintainable
- ✅ Your tests are comprehensive and meaningful
- ✅ Your PRs are well-documented and easy to review
- ✅ You respond promptly to review feedback
- ✅ You keep tickets and documentation updated
- ✅ You communicate proactively about progress and blockers
- ✅ You help others when they're stuck
- ✅ You follow team standards and workflows

### Red Flags:
- ❌ Tests frequently fail or are flaky
- ❌ PRs have many rounds of back-and-forth
- ❌ Code has frequent bugs after merge
- ❌ Documentation is outdated or missing
- ❌ Tickets sit in "In Progress" for days
- ❌ You don't ask questions when stuck

## Tools and Resources

### Essential Tools
- **IDE**: IntelliJ IDEA or VS Code with Groovy support
- **Version Control**: Git + GitHub
- **Build**: Gradle via mise tasks
- **Testing**: Spock + JUnit
- **Local Environment**: Docker (MySQL, Redis)

### Key Documentation
- [Development Workflow](../workflows/01-development-workflow.md)
- [Testing Workflow](../workflows/03-testing-workflow.md)
- [CLAUDE.md](../../CLAUDE.md) - Coding standards
- [Memory Bank Foundation](../foundation/)

### Useful Commands
```bash
# Development cycle
mise run start_docker_components
mise run build
mise run test
mise run bootRun

# Testing
mise run test_one <TestClassName>
gradle test -PexecuteFunctionalTests=true

# Database
mise run mysql_shell

# Health check
mise run health_check_api

# Cleanup
mise run stop_docker_components
```

## Tips and Tricks

### Productivity
- Use IDE shortcuts for navigation and refactoring
- Run tests continuously during development
- Keep a terminal with bootRun running
- Use git aliases for common commands
- Take regular breaks

### Code Quality
- Read your code out loud - does it make sense?
- If you need comments to explain, maybe refactor
- Smaller functions are easier to test and understand
- Don't optimize prematurely - make it work, then make it fast
- When in doubt, ask for review

### Debugging
- Start with the error message - read it carefully
- Add logging to understand flow
- Use IDE debugger for complex issues
- Reproduce in simplest possible case
- Ask for help if stuck >30 minutes

---

_Last updated: 2025-10-09_