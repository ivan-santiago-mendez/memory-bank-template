# Claude Code Custom Agents Integration

How to use custom agents with Claude Code in the intapi-assistant project.

## Overview

Custom agents are specialized AI assistants configured to perform specific roles following project guidelines. They are defined in `.claude/agents/` and integrate with the memory bank for consistent, role-appropriate behavior.

## Available Agents

### 1. Developer Agent
- **Type**: `developer`
- **Purpose**: Feature implementation, bug fixes, testing
- **Knowledge**: Developer guidelines, coding standards, technology stack
- **Use when**: Implementing features, fixing bugs, writing tests

### 2. Reviewer Agent
- **Type**: `reviewer`
- **Purpose**: Code review, quality assurance
- **Knowledge**: Review guidelines, coding standards, architecture
- **Use when**: Reviewing PRs, checking code quality

### 3. QA Agent
- **Type**: `qa`
- **Purpose**: Testing, quality verification
- **Knowledge**: QA guidelines, testing workflows, test strategies
- **Use when**: Testing features, verifying fixes, executing test plans

### 4. AI Assistant Agent
- **Type**: `ai-assistant`
- **Purpose**: General project work following all guidelines
- **Knowledge**: All memory bank guidelines, workflows, standards
- **Use when**: General tasks, ticket-driven development, executive summaries

### 5. Documentation Agent
- **Type**: `documentation`
- **Purpose**: Memory bank and documentation maintenance
- **Knowledge**: Documentation standards, memory bank structure
- **Use when**: Updating docs, maintaining memory bank, fixing broken links

### 6. Automation Agent
- **Type**: `automation`
- **Purpose**: CI/CD, mise tasks, Docker configuration
- **Knowledge**: Build configuration, Docker, mise tasks, CI/CD
- **Use when**: Maintaining automation, updating mise tasks, Docker issues

## How to Use Agents

### Via Task Tool

Agents are invoked using the Task tool with the `subagent_type` parameter:

```
Task tool parameters:
- description: "Brief description of task"
- prompt: "Detailed task description with context"
- subagent_type: "agent-name"
```

### Example Invocations

**Developer Agent**:
```
description: "Implement feature AIT-XXX"
prompt: "Implement the MCP client integration feature defined in ticket AIT-654. Follow the architecture defined in the ticket README and use Taulia starters framework."
subagent_type: "developer"
```

**Reviewer Agent**:
```
description: "Review PR for AIT-XXX"
prompt: "Review the pull request for AIT-654 MCP client integration. Check code quality, test coverage, documentation, and architectural alignment."
subagent_type: "reviewer"
```

**QA Agent**:
```
description: "Test AIT-XXX feature"
prompt: "Test the MCP client integration feature from AIT-654. Execute automated tests, perform manual testing, and verify acceptance criteria."
subagent_type: "qa"
```

**Documentation Agent**:
```
description: "Update memory bank for AIT-XXX"
prompt: "Update the memory bank to reflect the new MCP client integration architecture. Update foundation/03-module-architecture.md and context/01-active-context.md."
subagent_type: "documentation"
```

**Automation Agent**:
```
description: "Add mise task for MCP testing"
prompt: "Add a mise task to test the MCP server and client integration. Include startup, health check, and shutdown."
subagent_type: "automation"
```

## Agent Configuration

### Configuration Location
`.claude/agents/[agent-name].json`

### Configuration Structure
```json
{
  "name": "agent-name",
  "description": "Brief description",
  "instructions": "Detailed guidelines from memory bank",
  "knowledgeBase": [
    "memory-bank/agents/XX-agent.md",
    "other/relevant/files.md"
  ],
  "allowedTools": ["Read", "Write", "Edit", "Bash", "Task"]
}
```

### Configuration Best Practices
- Keep instructions focused on role-specific guidelines
- Reference memory bank docs as source of truth
- Include only necessary tools for the role
- Maintain consistency with memory bank agent definitions

## Agent Behavior

### Memory Bank Integration
All agents:
- Load memory bank as source of truth
- Follow guidelines from memory-bank/agents/
- Reference foundation docs for context
- Follow workflows defined in memory-bank/workflows/
- Maintain consistency with project standards

### Ticket-Driven Development
All agents:
- Require valid JIRA ticket number
- Check ticket documentation in ticket-administration/
- Document work in ticket folders
- Create executive summaries (not overly technical)

### Tool Usage
All agents:
- Use mise tasks exclusively (never direct gradle/git)
- Prefer specialized tools (Read/Write/Edit) over Bash
- Use TodoWrite for progress tracking
- Follow tool usage guidelines from memory bank

## Multi-Agent Workflows

Agents can be used together for complex workflows:

### Feature Implementation Workflow
1. **Developer** implements feature
2. **Reviewer** reviews code
3. **QA** tests implementation
4. **Documentation** updates memory bank

### Bug Fix Workflow
1. **Developer** fixes bug
2. **Developer** writes test
3. **QA** verifies fix
4. **Reviewer** approves

### Documentation Update Workflow
1. **Documentation** identifies gaps
2. **Documentation** updates docs
3. **Reviewer** checks accuracy
4. **Documentation** verifies links

## Best Practices

### Choosing the Right Agent
- Use **Developer** for implementation tasks
- Use **Reviewer** for code review and quality checks
- Use **QA** for testing and verification
- Use **AI Assistant** for general work or when unsure
- Use **Documentation** for memory bank maintenance
- Use **Automation** for CI/CD, mise, Docker

### Clear Task Descriptions
Provide:
- Ticket number (if applicable)
- Clear objective
- Relevant context
- Expected outcome
- Any constraints or requirements

### Agent Limitations
- Agents follow their role-specific guidelines
- Agents have limited tool access
- Agents reference memory bank as source of truth
- Agents cannot override project standards

## Maintenance

### Updating Agent Configurations
When updating agents:
1. Update `.claude/agents/[agent-name].json`
2. Update memory-bank/agents/XX-agent.md if needed
3. Test agent behavior
4. Document changes in this file
5. Update "Last updated" date

### Adding New Agents
To add a new agent:
1. Create `.claude/agents/[agent-name].json`
2. Define name, description, instructions
3. Specify knowledge base files
4. List allowed tools
5. Test thoroughly
6. Document in this file and .claude/agents/README.md

### Removing Agents
To remove an agent:
1. Delete `.claude/agents/[agent-name].json`
2. Update this file
3. Update .claude/agents/README.md
4. Document reason for removal

## Troubleshooting

### Agent Not Found
- Verify `.claude/agents/[agent-name].json` exists
- Check file name matches `subagent_type` parameter
- Ensure JSON is valid

### Agent Not Behaving as Expected
- Review agent instructions in JSON file
- Check knowledge base files are up to date
- Verify memory bank guidelines are current
- Test with simpler task first

### Agent Has Wrong Context
- Check knowledge base files in agent config
- Ensure memory bank is up to date
- Verify agent is loading correct docs

## Related Documentation

- [.claude/agents/README.md](../../.claude/agents/README.md) - Agent directory overview
- [memory-bank/agents/](./README.md) - Agent role definitions
- [CLAUDE.md](../../CLAUDE.md) - Project instructions
- [memory-bank/README.md](../README.md) - Memory bank index

## Success Criteria

### Agents are Working Well When:
- ✅ Agents follow role-specific guidelines
- ✅ Agents reference memory bank correctly
- ✅ Agents use appropriate tools
- ✅ Agents produce consistent results
- ✅ Agents integrate with ticket workflow
- ✅ Team finds agents helpful

### Red Flags:
- ❌ Agents ignore project standards
- ❌ Agents don't reference memory bank
- ❌ Agents use wrong tools
- ❌ Agents produce inconsistent results
- ❌ Agents skip ticket documentation
- ❌ Team bypasses agents

---

_Last updated: 2025-10-09_
_Created as part of AIT-654 MCP client integration work_
