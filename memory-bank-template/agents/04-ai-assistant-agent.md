# AI Assistant Agent

Guidelines for working effectively with Claude Code and other AI assistants on the intapi-assistant project.

## Core Principles

### 1. Memory Bank First, Always
**NEVER start work without loading the memory bank**

```markdown
# Required reading before any task:
1. memory-bank/README.md
2. All foundation documents (01-04)
3. Relevant ticket documentation
4. Applicable workflow documents
5. Related agent role definitions
```

### 2. Ticket-Driven Development
**ALL work must be associated with a valid JIRA ticket**

```markdown
# Before starting:
- Verify ticket number (e.g., AIT-XXX)
- Check if ticket folder exists in ticket-administration/
- Check if there is a version folder exists in ticket-administration/AIT-XXX
- Read ticket context and requirements in ticket-administration/AIT-XXX/README.md
- Document your work in ticket folder
```

### 3. Executive Summaries
**Create non-technical summaries for stakeholders**

```markdown
# NOT this (too technical):
"Implemented MessageChatMemoryAdvisor integration with Spring AI ChatClient
using ConversationId parameter for thread-safe conversation history retrieval"

# THIS (executive summary):
"Summary: Enhanced conversation memory system for better context retention
Complexity: Medium
The assistant now maintains conversation history more reliably across interactions"
```

### 4. Use Mise Tasks
**Always use `mise run <task>` instead of direct commands**

```bash
# ✅ Correct
mise run build
mise run test
mise run bootRun

# ❌ Wrong
gradle build
./gradlew test
java -jar app.jar
```

## AI Assistant Workflow

### Phase 1: Load Context
```markdown
1. 🔴 CRITICAL: Load ALL Claude Code agents from .claude/agents/ FIRST:
   - .claude/agents/README.md
   - .claude/agents/developer.json
   - .claude/agents/reviewer.json
   - .claude/agents/qa.json
   - .claude/agents/ai-assistant.json
   - .claude/agents/documentation.json
   - .claude/agents/automation.json
2. Load memory-bank/README.md
3. Load foundation documents (project overview, tech stack, architecture)
4. Load applicable workflows (development, testing, etc.)
5. Load relevant agent roles from memory-bank/agents/ (developer, reviewer, etc.)
6. Load ticket documentation for current task
7. Confirm context loaded: "I've loaded Claude agents, memory bank, and ticket AIT-XXX context"
```

### Phase 2: Understand Task
```markdown
1. Read ticket description and acceptance criteria
2. Ask clarifying questions if anything is unclear
3. Identify which files/modules will be affected
4. Consider architectural implications
5. Propose approach: "Here's my plan: [explain approach]"
6. Get user confirmation before proceeding
```

### Phase 3: Plan Execution
```markdown
1. Break down task into small steps
2. Use TodoWrite tool to track progress
3. Document plan in ticket README
4. Start with reading relevant code
5. Make incremental changes with frequent commits
```

### Phase 4: Implement
```markdown
1. Follow coding standards from CLAUDE.md
2. Write tests alongside code
3. Use mise tasks for all operations
4. Document decisions in ticket README
5. Update memory bank if architectural changes
6. Create executive summaries for ticket comments
```

### Phase 5: Verify and Document
```markdown
1. Run tests: mise run test
2. Build project: mise run build
3. Manual testing: mise run bootRun
4. Complete ticket documentation
5. Create executive summary
6. Prepare PR description
```

## Working with Users

### When User Says "Implement X"
```markdown
# Your response should be:
1. "Let me load the memory bank and ticket context first"
   [Load all required documentation]

2. "I understand you want to [restate requirement].
    Here's my approach: [explain plan]"
   [Present clear, structured plan]

3. "Does this approach look good?"
   [Get confirmation before coding]

4. [Only after approval] "Starting implementation..."
   [Use TodoWrite to track progress]
```

### When You Need Clarification
```markdown
# Be specific about what you need:
"I need clarification on [specific point]:

Context: [what you understand so far]

Options:
1. [Option 1]
2. [Option 2]

Which approach would you prefer, or is there another way?"
```

### When You Encounter Issues
```markdown
# Communicate clearly:
"I've encountered [specific issue]:

What I tried:
1. [Approach 1] - [Result]
2. [Approach 2] - [Result]

Error message: [if applicable]

I recommend [proposed solution]. Shall I proceed?"
```

## Documentation Guidelines

### Ticket README Updates
```markdown
# Update frequently as you work:

## Progress
- [x] Completed task 1
- [x] Completed task 2
- [ ] In progress: Task 3
- [ ] Pending: Task 4

## Decisions Made
### Decision: [Title]
- **Context**: [Why needed]
- **Choice**: [What was chosen]
- **Rationale**: [Why this choice]
- **Date**: 2025-10-09

## Notes
- [Observation or learning]
- [Challenge encountered and how solved]
```

### Executive Summaries
```markdown
# Format for ticket comments:

Summary: [One sentence describing what was done]
Complexity: [Low/Medium/High]

[2-3 sentences explaining impact in business terms]

Technical details documented in: memory-bank/ticket-administration/JIRA/AIT-XXX/

# Example:
Summary: Integrated MCP client for data analytics capabilities
Complexity: Medium

The assistant can now access real-time company data and analytics tools,
enabling more accurate and data-driven responses to user questions.
This improves response quality and reduces manual data lookup needs.

Technical details documented in: memory-bank/ticket-administration/JIRA/AIT-654/
```

### Memory Bank Updates
```markdown
# Update when:
- Adding new architecture patterns
- Introducing new dependencies
- Changing build configuration
- Discovering important patterns
- Making significant decisions

# What to update:
- foundation/03-module-architecture.md (architectural changes)
- foundation/02-technology-stack.md (dependency changes)
- context/01-active-context.md (current work focus)
- context/02-progress.md (status updates)
```

## Common Scenarios

### Scenario: New Feature Implementation
```markdown
1. Load memory bank and ticket AIT-XXX
2. Present approach: "I'll implement [feature] by [approach]"
3. Get approval
4. Create TodoWrite list with steps
5. Implement incrementally:
   - Read existing related code
   - Make small changes
   - Write tests
   - Update documentation
6. Create executive summary
7. Prepare PR
```

### Scenario: Bug Fix
```markdown
1. Load memory bank and ticket AIT-XXX
2. Reproduce bug locally
3. Explain root cause to user
4. Propose fix approach
5. Implement fix with test
6. Verify fix works
7. Document in ticket README
8. Create executive summary
```

### Scenario: Code Review
```markdown
1. Load memory bank
2. Read PR description and changes
3. Check against coding standards
4. Verify tests exist and pass
5. Look for potential issues
6. Provide constructive feedback:
   - Be specific
   - Explain reasoning
   - Suggest alternatives
   - Acknowledge good work
```

### Scenario: Documentation Update
```markdown
1. Load memory bank
2. Identify what needs updating
3. Present plan: "I'll update [files] to reflect [changes]"
4. Make updates
5. Verify cross-references
6. Check formatting and links
7. Update "Last updated" date
```

## Best Practices

### DO:
- ✅ Always load memory bank first
- ✅ Use mise tasks for all commands
- ✅ Create TodoWrite lists for tracking
- ✅ Update documentation as you code
- ✅ Create executive summaries
- ✅ Ask for clarification when unsure
- ✅ Present plan before implementing
- ✅ Make incremental changes
- ✅ Run tests frequently
- ✅ Follow coding standards from CLAUDE.md

### DON'T:
- ❌ Start coding without loading memory bank
- ❌ Use direct gradle/git commands instead of mise
- ❌ Create overly technical ticket comments
- ❌ Skip documentation updates
- ❌ Make large changes without plan
- ❌ Ignore test failures
- ❌ Assume context without asking
- ❌ Skip executive summaries
- ❌ Forget to update ticket README
- ❌ Leave TODOs without tickets

## Communication Patterns

### Starting Work
```markdown
"I'm starting work on AIT-XXX. Let me load Claude agents and memory bank first.

[Load all Claude agents from .claude/agents/]
[Load all required memory bank docs]

I've loaded the Claude agents and memory bank context. I understand the task is to [restate requirement].

My approach:
1. [Step 1]
2. [Step 2]
3. [Step 3]

Does this plan look good?"
```

### During Work
```markdown
"I've completed [task 1] and am now working on [task 2].

Progress:
- ✅ Task 1 complete
- 🚧 Task 2 in progress
- ⏳ Task 3 pending

Everything on track, no blockers."
```

### Completing Work
```markdown
"I've completed the implementation for AIT-XXX.

Summary:
- [What was done]
- Tests passing
- Documentation updated

Executive Summary:
[Non-technical summary for ticket]

Ready to create PR?"
```

## Success Criteria

### You're an Effective AI Assistant When:
- ✅ 🔴 You always load Claude agents FIRST at session start
- ✅ You always load memory bank after Claude agents
- ✅ You follow project workflows and standards
- ✅ You provide clear communication
- ✅ You document decisions and rationale
- ✅ You create helpful executive summaries
- ✅ You ask for clarification when needed
- ✅ You make incremental, testable changes
- ✅ You keep users informed of progress
- ✅ You update documentation proactively

### Red Flags:
- ❌ 🔴 Starting ANY work without loading Claude agents first
- ❌ Starting work without loading memory bank
- ❌ Using direct commands instead of mise tasks
- ❌ Creating overly technical summaries
- ❌ Making assumptions without asking
- ❌ Skipping documentation updates
- ❌ Ignoring workflow guidelines
- ❌ Not using TodoWrite for tracking

## Tools for AI Assistants

### Essential Tools
- **Read**: Load memory bank and code files
- **Write/Edit**: Create/update files
- **Bash** (via mise): Execute mise tasks only
- **Glob/Grep**: Search for files and content
- **TodoWrite**: Track progress
- **Task**: Delegate complex multi-step tasks

### Tool Usage Guidelines
```markdown
# Always prefer:
Read → For loading files
Edit → For modifying existing files
Write → For creating new files
Glob → For finding files by pattern
Grep → For searching content
TodoWrite → For tracking progress

# Use mise via Bash for:
mise run build
mise run test
mise run bootRun
(etc. - all mise tasks)

# Don't use Bash for:
- File operations (use Read/Write/Edit)
- Direct gradle/git commands
- Searching (use Grep/Glob)
```

---

_Last updated: 2025-10-09_