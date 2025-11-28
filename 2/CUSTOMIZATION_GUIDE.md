# Memory Bank Customization Guide

Step-by-step guide to customize this template for your project.

## Overview

This guide will help you transform this generic template into a project-specific knowledge repository for Claude Code.

**Estimated Time**: 2-4 hours
**Prerequisites**: Project understanding, team processes documented

## Step 1: Project Setup (15 minutes)

### 1.1 Copy Template
```bash
# Copy this template to your project
cp -r memory-bank-template/ your-project/memory-bank/

cd your-project/memory-bank/
```

### 1.2 Update Main README
Edit `README.md`:
- Replace "Memory Bank Template" with your project name
- Update "Last Updated" date
- Update "Maintained By" with your team name
- Add project-specific quick start examples

### 1.3 Configure Gitignore
```bash
# Copy gitignore template to project root
cat memory-bank/.gitignore-template >> ../.gitignore

# Or integrate with existing .gitignore
```

## Step 2: Document Architecture (30-45 minutes)

### 2.1 Project Structure
Create `03-component-architecture/project-structure.md`:

```markdown
# Project Structure

## Root Directory
- `src/` - Source code
- `tests/` - Test files
- `docs/` - Documentation
- `scripts/` - Automation scripts

## Module Organization
[Describe your modules/packages]

## Key Files
[List important files and their purpose]
```

### 2.2 Technology Stack
Create `03-component-architecture/tech-stack.md`:

```markdown
# Technology Stack

## Languages
- [Language]: [Version]

## Frameworks
- [Framework]: [Version]

## Databases
- [Database]: [Version]

## External Services
- [Service]: [Purpose]
```

### 2.3 External Dependencies
Create `03-component-architecture/external-dependencies.md`:

```markdown
# External Dependencies

## Services
| Service | Purpose | Authentication | Rate Limits |
|---------|---------|----------------|-------------|
| [Service] | [Why] | [How] | [Limits] |
```

### 2.4 Configuration
Create `03-component-architecture/configuration-guide.md`:

```markdown
# Configuration Guide

## Environment Variables
- `VAR_NAME`: [Purpose]

## Config Files
- `path/to/config`: [Purpose]

## Setup Instructions
1. Step 1
2. Step 2
```

## Step 3: Define Standards (45-60 minutes)

### 3.1 Language Style Guide
Create `04-standards/[language]-style-guide.md`:

```markdown
# [Language] Style Guide

## Naming Conventions
- Variables: [Convention]
- Functions: [Convention]
- Classes: [Convention]

## Code Organization
[Your patterns]

## Good/Bad Examples
✅ Good:
```[language]
[example]
```

❌ Bad:
```[language]
[example]
```
```

### 3.2 Error Handling
Create `04-standards/error-handling.md`:

```markdown
# Error Handling Standards

## Exception Types
[Your exception hierarchy]

## Error Propagation
[How errors should be handled]

## Logging Errors
[When and how to log]
```

### 3.3 Logging Standards
Create `04-standards/logging-standards.md`:

```markdown
# Logging Standards

## Log Levels
- DEBUG: [When to use]
- INFO: [When to use]
- WARN: [When to use]
- ERROR: [When to use]

## Log Format
[Your structured logging format]
```

### 3.4 Security Checklist
Create `04-standards/security-checklist.md`:

```markdown
# Security Checklist

## Authentication
- [ ] Check 1
- [ ] Check 2

## Authorization
- [ ] Check 1
- [ ] Check 2

## Input Validation
- [ ] Check 1
- [ ] Check 2
```

## Step 4: Create Workflows (30-45 minutes)

### 4.1 Ticket Creation
Create `01-workflows/ticket-creation-workflow.md`:

```markdown
# Ticket Creation Workflow

## Trigger
User requests ticket creation with complete requirements

## Prerequisites
- [ ] Requirements validated
- [ ] Template sections complete

## Steps

### Step 1: Validate Requirements
[Your validation process]

### Step 2: Create Ticket
[Your ticket system specifics]

## Success Criteria
- [ ] Ticket created
- [ ] Ticket ID returned
```

### 4.2 Git PR Workflow
Create `01-workflows/git-pr-workflow.md`:

```markdown
# Pull Request Creation Workflow

## Trigger
User requests PR creation

## Prerequisites
- [ ] Changes committed
- [ ] Tests passing
- [ ] Code reviewed

## Steps

### Step 1: Generate Description
[Your PR description format]

### Step 2: Create PR
[Your PR process]

### Step 3: Request Reviews
[Your review process]
```

### 4.3 Code Review Workflow
Create `01-workflows/code-review-workflow.md`:

```markdown
# Code Review Workflow

## Trigger
PR created or review requested

## Steps

### Step 1: Automated Checks
[Your CI/CD checks]

### Step 2: Code Review
[Your review checklist]

### Step 3: Approval
[Your approval process]
```

### 4.4 Testing Workflow
Create `01-workflows/testing-workflow.md`:

```markdown
# Testing Workflow

## Test Types
- Unit: [How to run]
- Integration: [How to run]
- E2E: [How to run]

## Coverage Requirements
[Your coverage targets]

## Running Tests
```bash
[Your test commands]
```
```

## Step 5: Create Templates (30 minutes)

### 5.1 Ticket Template
Create `02-templates/ticket-template.md`:

```markdown
# Ticket Template

## Format
```
Title: [Brief description]

Description: [Detailed description]

Acceptance Criteria:
- [ ] Criterion 1
- [ ] Criterion 2

Testing:
- [ ] Test 1
- [ ] Test 2
```

## Example
[Filled-out example]
```

### 5.2 PR Template
Create `02-templates/pr-template.md`:

```markdown
# PR Template

## Format
```
## Summary
[What changed]

## Changes
- Change 1
- Change 2

## Testing
- [ ] Test 1
- [ ] Test 2
```

## Example
[Filled-out example]
```

### 5.3 Commit Message Template
Create `02-templates/commit-message-template.md`:

```markdown
# Commit Message Template

## Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

## Types
- feat: New feature
- fix: Bug fix
- docs: Documentation
- refactor: Code refactoring
- test: Tests
- chore: Maintenance
```

## Step 6: Document Scripts (20-30 minutes)

### 6.1 Scripts Overview
Create `07-scripts-documentation/scripts-overview.md`:

```markdown
# Scripts Overview

## Task Runner
[Your task runner: Makefile, run.sh, npm scripts]

## Available Commands
| Command | Description |
|---------|-------------|
| [command] | [what it does] |
```

### 6.2 Setup Scripts
Create `07-scripts-documentation/setup-scripts.md`:

```markdown
# Setup Scripts

## First Time Setup
```bash
[Your setup commands]
```

## Dependencies
- Dependency 1
- Dependency 2
```

## Step 7: Create Sub-Agents (30-45 minutes)

### 7.1 Create Agent Directory
```bash
# Create agents directory in project root
mkdir -p .claude/agents
```

### 7.2 Code Reviewer Agent
Create `.claude/agents/code-reviewer.yaml`:

```yaml
---
name: code-reviewer
description: Expert code reviewer for [PROJECT_NAME]
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

Report: ✅ passed / ⚠️ warnings / ❌ critical issues
```

### 7.3 Document Agents
Create `08-agents/auto-invocation-rules.md`:

```markdown
# Auto-Invocation Rules

## Before PR Creation
**Trigger**: User requests PR creation
**Agent**: code-reviewer
**Action**: Review all changed files
```

## Step 8: Document Team Processes (20-30 minutes)

### 8.1 Story Point Estimation
Create `09-team-processes/story-point-estimation.md`:

```markdown
# Story Point Estimation

## Scale
[Your scale: Fibonacci, T-shirt, etc.]

## Reference Stories
### [Size] - [Complexity]
- Example 1
- Example 2
```

### 8.2 Ticket Lifecycle
Create `09-team-processes/ticket-lifecycle.md`:

```markdown
# Ticket Lifecycle

## States
1. To Do → In Progress
2. In Progress → Review
3. Review → Done

## Transition Criteria
[Your criteria for each transition]
```

## Step 9: Setup Ticket Administration (10 minutes)

### 9.1 Create Structure
```bash
# Create ticket system folder (replace JIRA with your system)
mkdir -p memory-bank/ticket-administration/JIRA
```

### 9.2 Archive Process
Create `ticket-administration/archive-process.md`:

```markdown
# Archive Process

## When to Archive
[Your criteria]

## How to Archive
1. Step 1
2. Step 2
```

## Step 10: Update CLAUDE.md (20-30 minutes)

Create `CLAUDE.md` in project root:

```markdown
# CLAUDE.md

Instructions for Claude Code on how to work in [PROJECT_NAME].

## Purpose
[Brief description]

## Quick Reference

### Development Operations
| Task | Command |
|------|---------|
| Build | [command] |
| Test | [command] |
| Run | [command] |

### Workflow Operations
| Task | Workflow File |
|------|---------------|
| Create ticket | `memory-bank/01-workflows/ticket-creation-workflow.md` |
| Create PR | `memory-bank/01-workflows/git-pr-workflow.md` |

## Configuration
**Ticket System**: [Jira/Linear/GitHub/etc.]
**Project Key**: [YOUR_PROJECT_KEY]

## Memory Bank
**All knowledge lives in `memory-bank/`**

Read `memory-bank/README.md` first for complete structure.

## Rules
1. Read workflows first
2. Use templates
3. Auto-invoke sub-agents (check `memory-bank/08-agents/auto-invocation-rules.md`)
4. No confirmations (execute after disambiguation)
5. Reference memory bank (don't duplicate knowledge)
```

## Step 11: Test with Claude (15-30 minutes)

### 11.1 Test Basic Commands
Ask Claude:
- "What is the project structure?"
- "How do I create a ticket?"
- "What are the coding standards?"
- "How do I run tests?"

### 11.2 Test Workflows
Ask Claude to:
- Create a draft ticket
- Review some code
- Generate commit message

### 11.3 Verify Sub-Agents
Ask Claude to:
- Review code with code-reviewer agent
- Explain when agents are auto-invoked

## Step 12: Team Rollout (Ongoing)

### 12.1 Share with Team
- Present memory bank structure
- Explain how to update
- Demonstrate with Claude Code

### 12.2 Iterate
- Gather feedback
- Update based on usage
- Refine processes
- Add missing documentation

### 12.3 Maintain
- Update as project evolves
- Keep workflows current
- Review quarterly
- Prune outdated content

## Checklist: Customization Complete

- [ ] Main README updated with project name
- [ ] .gitignore configured for memory-bank
- [ ] Architecture documented (03-component-architecture)
- [ ] Standards defined (04-standards)
- [ ] Workflows created (01-workflows)
- [ ] Templates created (02-templates)
- [ ] Scripts documented (07-scripts-documentation)
- [ ] Sub-agents created (.claude/agents)
- [ ] Team processes documented (09-team-processes)
- [ ] Ticket administration setup (ticket-administration)
- [ ] CLAUDE.md created in project root
- [ ] Tested with Claude Code
- [ ] Team onboarded

## Maintenance Schedule

### Weekly
- Update active workflows if process changes
- Add new scripts documentation as needed

### Monthly
- Review and update standards
- Check for outdated information
- Update architecture docs if changed

### Quarterly
- Full review of all documentation
- Team feedback session
- Major updates and improvements
- Archive old/unused content

## Getting Help

If you need help customizing:
1. Review example in intapi-assistant repository
2. Check individual folder READMEs for guidance
3. Start small - document what's most important first
4. Iterate based on actual usage

## Next Steps

After customization:
1. **Use it**: Start using Claude Code with your memory bank
2. **Learn**: See what works and what doesn't
3. **Improve**: Update based on real usage
4. **Share**: Help other projects adopt this pattern

---

**Remember**: This is a living repository. It grows and improves with your project.