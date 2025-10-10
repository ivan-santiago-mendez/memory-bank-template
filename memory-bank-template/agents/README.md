# Team Agents (Roles and Responsibilities)

This section defines team roles, responsibilities, and guidelines for the intapi-assistant project. Think of these as "agents" - defined roles with specific responsibilities and ways of working.

## What Are Team Agents?

Team agents are defined roles that team members take on during development. Each agent has:
- **Clear responsibilities**: What this role is accountable for
- **Guidelines**: How to perform the role effectively
- **Tools and resources**: What the role needs to succeed
- **Success criteria**: How to know you're doing it well

## Purpose

- Define clear roles and responsibilities
- Set expectations for each role
- Provide guidelines for effective work
- Support collaboration and accountability
- Enable smooth team operation

## Contents

- **[01-developer-agent.md](01-developer-agent.md)**
  Developer role, daily responsibilities, and coding practices

- **[02-reviewer-agent.md](02-reviewer-agent.md)**
  Code reviewer guidelines, standards, and review practices

- **[03-qa-agent.md](03-qa-agent.md)**
  QA and testing responsibilities, procedures, and quality standards

- **[04-ai-assistant-agent.md](04-ai-assistant-agent.md)**
  How to work effectively with Claude Code and AI assistants

- **[05-documentation-agent.md](05-documentation-agent.md)**
  Documentation maintenance responsibilities and practices

- **[06-automation-agent.md](06-automation-agent.md)**
  CI/CD, automation tooling, and infrastructure responsibilities

- **[07-claude-code-agents.md](07-claude-code-agents.md)**
  How to use Claude Code custom agents (`.claude/agents/` directory integration)

## How to Use This Section

### For Team Members
1. Review the agent(s) relevant to your current work
2. Follow guidelines and best practices
3. Use checklists to ensure completeness
4. Refer back when unsure about responsibilities

### For Team Leads
1. Assign roles to team members
2. Use as basis for onboarding
3. Review and update as processes evolve
4. Reference in performance discussions

### For AI Assistants
1. **ALWAYS** load relevant agent documentation
2. Follow agent guidelines when performing tasks
3. Especially important: 04-ai-assistant-agent.md
4. Update agent docs if new patterns emerge

## Role Assignment

### Single-Person Roles (Can Rotate)
- **On-call Engineer**: Responds to production incidents
- **Sprint Facilitator**: Runs sprint ceremonies
- **Documentation Champion**: Ensures docs stay current

### Multi-Person Roles (Everyone Participates)
- **Developer**: Everyone writes code
- **Reviewer**: Everyone reviews code
- **QA**: Everyone tests their work
- **AI Assistant User**: Everyone uses AI tools effectively

### Shared Responsibilities
- All team members maintain documentation
- All team members contribute to automation
- All team members support team health

## Agent Principles

### 1. Clear Ownership
- Each role has defined responsibilities
- Overlaps are intentional and documented
- Gaps are identified and assigned

### 2. Accountability
- Role holders are accountable for their area
- Success criteria are measurable
- Regular review of effectiveness

### 3. Collaboration
- Roles work together, not in silos
- Communication is key
- Support each other's success

### 4. Continuous Improvement
- Roles evolve with the project
- Feedback is encouraged
- Process refinement is ongoing

## Quick Reference

### I'm Starting Development
→ See [01-developer-agent.md](01-developer-agent.md)
→ See [04-ai-assistant-agent.md](04-ai-assistant-agent.md) if using AI

### I'm Reviewing a PR
→ See [02-reviewer-agent.md](02-reviewer-agent.md)

### I'm Testing a Feature
→ See [03-qa-agent.md](03-qa-agent.md)

### I'm Updating Documentation
→ See [05-documentation-agent.md](05-documentation-agent.md)

### I'm Working on CI/CD
→ See [06-automation-agent.md](06-automation-agent.md)

### I'm Using Claude Code Agents
→ See [07-claude-code-agents.md](07-claude-code-agents.md)
→ See [.claude/agents/README.md](../../.claude/agents/README.md)

## Related Documentation

- [Development Workflow](../workflows/01-development-workflow.md) - Day-to-day development process
- [Code Review Workflow](../workflows/02-code-review-workflow.md) - PR creation and review
- [Testing Workflow](../workflows/03-testing-workflow.md) - Testing strategy and execution
- [Documentation Workflow](../workflows/05-documentation-workflow.md) - Documentation maintenance
- [Best Practices](../ticket-administration/01-best-practices.md) - Coding and commit standards

---

_Last updated: 2025-10-09_