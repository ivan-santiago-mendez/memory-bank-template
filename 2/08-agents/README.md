# Sub-Agents

Documentation for Claude Code sub-agents - specialized AI assistants for specific tasks.

## Purpose

Sub-agents are specialized versions of Claude Code that:
- Operate in separate context windows
- Have focused expertise for specific tasks
- Use custom system prompts aligned with project standards
- Have controlled tool access for security
- Serve as quality gates for critical operations

## What are Sub-Agents?

Sub-agents are defined in YAML files at `.claude/agents/` (project root). Each sub-agent:
- Has a specific responsibility (code review, testing, security, etc.)
- References memory-bank standards in its prompt
- Is invoked automatically or explicitly by main Claude
- Returns findings to main conversation

## Recommended Sub-Agents

### Code Quality
- **code-reviewer** - Reviews code against project standards
  - Purpose: PR reviews, code quality checks
  - Tools: Read, Grep, Glob
  - Reads: `04-standards/`

- **test-generator** - Generates tests for new code
  - Purpose: Create unit/integration tests
  - Tools: Read, Write, Edit
  - Reads: `04-standards/testing-standards.md`

### Security
- **security-auditor** - Scans for security vulnerabilities
  - Purpose: Authentication, authorization, input validation checks
  - Tools: Read, Grep, Glob
  - Reads: `04-standards/security-checklist.md`

### Ticket Management
- **ticket-creator** - Creates well-formed tickets
  - Purpose: Validate ticket structure before creation
  - Tools: Read, MCP tools for ticket system
  - Reads: `02-templates/ticket-template.md`

- **ticket-implementer** - Implements tickets end-to-end
  - Purpose: Fetch ticket, analyze, implement, test
  - Tools: Read, Write, Edit, Grep, Glob, Bash, TodoWrite, MCP tools
  - Reads: All memory-bank folders

### Documentation
- **documentation-writer** - Updates documentation
  - Purpose: Ensure consistent documentation
  - Tools: Read, Write, Edit, Glob
  - Reads: All memory-bank folders

## Sub-Agent Definition Template

Create in `.claude/agents/[agent-name].yaml`:

```yaml
---
name: [agent-name]
description: [One-line description for auto-invocation matching]
tools: [Comma-separated list: Read, Write, Edit, Grep, Glob, Bash, etc.]
model: inherit
---
You are a [role description] for [PROJECT_NAME].

BEFORE [task], read these standards:
- memory-bank/04-standards/[relevant-standard].md
- memory-bank/03-component-architecture/[relevant-doc].md

Your responsibilities:
1. [Responsibility 1]
2. [Responsibility 2]
3. [Responsibility 3]

Review checklist:
- [ ] Check 1
- [ ] Check 2
- [ ] Check 3

Report format: ✅ passed / ⚠️ warnings / ❌ critical issues

If critical issues found:
- List each issue with file:line reference
- Explain why it's an issue
- Suggest fix

If warnings found:
- List each warning
- Explain context
- Let user decide

If all passed:
- Confirm checks completed
- Summary of what was reviewed
```

## Auto-Invocation Rules

Document when sub-agents should be automatically invoked. Create `auto-invocation-rules.md`:

```markdown
# Auto-Invocation Rules

## Before PR Creation
**Trigger**: User requests PR creation
**Agent**: code-reviewer
**Action**: Review all changed files against standards

## After New Service Created
**Trigger**: New service class created
**Agent**: test-generator
**Action**: Generate test suite

## Security Changes
**Trigger**: Changes to auth/security code
**Agent**: security-auditor
**Action**: Security vulnerability scan

## Ticket Creation
**Trigger**: User requests ticket creation with complete requirements
**Agent**: ticket-creator
**Action**: Validate ticket structure

## Documentation Updates
**Trigger**: Changes to memory-bank docs
**Agent**: documentation-writer
**Action**: Check consistency and formatting
```

## How Sub-Agents Work

```
User: "Create a PR for my changes"
    ↓
Main Claude reads: 08-agents/auto-invocation-rules.md
    ↓
Match found: "Before PR Creation"
    ↓
Invoke: code-reviewer sub-agent
    ↓
Sub-agent runs in separate context:
  - Reads standards
  - Reviews code
  - Checks for issues
    ↓
Returns to main Claude: ✅/⚠️/❌ + details
    ↓
If ❌: Fix issues before continuing
If ⚠️: Report warnings, user decides
If ✅: Continue with PR creation
```

## Invocation Methods

### Method 1: Automatic (Recommended)
Claude automatically invokes based on auto-invocation-rules.md

### Method 2: Explicit
User requests: "Use the [agent-name] sub-agent to [task]"

### Method 3: CLI
```bash
claude --agent [agent-name] "[task description]"
```

## Creating Sub-Agents

### Step 1: Identify Need
What tasks need specialized expertise?
- Repetitive quality checks
- Domain-specific validation
- Security auditing
- Complex code generation

### Step 2: Define Scope
For each sub-agent:
- **Name**: Descriptive, kebab-case
- **Responsibility**: Single, clear purpose
- **Tools**: Minimum necessary tools
- **Standards**: Which memory-bank docs to reference

### Step 3: Write Definition
Create `.claude/agents/[agent-name].yaml`:
- Write clear description (for auto-matching)
- Define system prompt
- List tools
- Reference standards

### Step 4: Document
Create entry in this README and auto-invocation-rules.md

### Step 5: Test
Test sub-agent:
```bash
claude --agent [agent-name] "[test task]"
```

## Best Practices

- **Single Responsibility**: One clear purpose per agent
- **Tool Minimalism**: Only grant necessary tools
- **Standards Integration**: Reference memory-bank standards
- **Clear Description**: Help main Claude know when to invoke
- **Version Control**: Commit agents to git

## Usage Notes

- Sub-agents start fresh each invocation (no persistent context)
- Use for focused tasks, not entire workflows
- Sub-agents can be chained, but consider overhead
- Don't use for simple tasks (1-2 file edits)

## Integration with Workflows

Sub-agents integrate into workflows as quality gates:

- **01-workflows/git-pr-workflow.md** → Invokes code-reviewer
- **01-workflows/testing-workflow.md** → Invokes test-generator
- **01-workflows/ticket-creation-workflow.md** → Invokes ticket-creator

## Troubleshooting

### Agent not found
**Check**:
- `.claude/agents/[agent-name].yaml` exists
- YAML syntax is valid
- Name matches exactly

### Agent not auto-invoked
**Check**:
- `auto-invocation-rules.md` has rule defined
- Task matches trigger condition
- Description is clear enough for matching

### Agent fails with permission error
**Check**:
- Required tools listed in YAML frontmatter
- File paths are accessible
- Memory-bank files exist

## Security Considerations

- **Tool Access**: Only grant tools sub-agent needs
- **File Access**: Sub-agents can't access files outside project
- **API Access**: MCP tools require user authorization
- **Code Execution**: Bash tool should be used carefully

## Customization Guide

1. **Identify specialized tasks** in your workflow
2. **Create agent definitions** in `.claude/agents/`
3. **Document agents** in this folder
4. **Define auto-invocation rules** in `auto-invocation-rules.md`
5. **Test agents** before relying on them
6. **Update workflows** to reference agents
7. **Train team** on when to explicitly invoke agents

## Example: Code Reviewer Agent

`.claude/agents/code-reviewer.yaml`:
```yaml
---
name: code-reviewer
description: Expert code reviewer for project standards
tools: Read, Grep, Glob
model: inherit
---
You are an expert code reviewer for [PROJECT_NAME].

BEFORE reviewing, read these standards:
- memory-bank/04-standards/[language]-style-guide.md
- memory-bank/04-standards/error-handling.md
- memory-bank/04-standards/security-checklist.md

Review checklist:
1. Code follows style guide
2. Error handling is proper
3. Tests are included
4. Security checks pass
5. Documentation is updated

Report: ✅ passed / ⚠️ warnings / ❌ critical issues
```

---

**Customize this folder** by creating sub-agents for specialized tasks in your development workflow.