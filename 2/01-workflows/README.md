# Workflows Catalog

Step-by-step procedures for common development tasks. Each workflow is deterministic and repeatable.

## Purpose

Workflows provide Claude Code with explicit, step-by-step instructions for performing common development tasks. Each workflow ensures consistency across team members and automation.

## Available Workflows (Template)

### Ticket Operations
- **ticket-drafting-workflow.md** - Draft ticket requirements in context folder
- **ticket-creation-workflow.md** - Create ticket in your tracking system
- **ticket-transition-workflow.md** - Transition ticket status
- **ticket-closure-workflow.md** - Close tickets

### Git Operations
- **git-commit-workflow.md** - How to create commits
- **git-pr-workflow.md** - How to create pull requests
- **git-branch-strategy.md** - Branch naming conventions

### Code Quality
- **code-review-workflow.md** - PR review process
- **testing-workflow.md** - Test execution strategy

### Project Setup
- **project-setup-workflow.md** - First-time project setup

### Daily Operations
- **end-of-day-workflow.md** - EOD checklist

## Workflow File Structure

Each workflow file should contain:

### 1. Trigger
When to use this workflow (conditions that activate it)

### 2. Prerequisites
What must be ready before starting

### 3. Steps
Numbered, sequential steps with clear actions

### 4. Success Criteria
How to verify the workflow completed successfully

### 5. Error Handling
What to do if something fails

### 6. Related Workflows
Links to workflows that may run before or after

## Example Workflow Template

```markdown
# [Workflow Name]

## Trigger
[When should this workflow be used?]

## Prerequisites
- [ ] Prerequisite 1
- [ ] Prerequisite 2

## Steps

### Step 1: [Action Name]
**Action**: [What to do]
**Tools**: [Which tools to use]
**Output**: [Expected result]

### Step 2: [Action Name]
**Action**: [What to do]
**Tools**: [Which tools to use]
**Output**: [Expected result]

## Success Criteria
- [ ] Success criterion 1
- [ ] Success criterion 2

## Error Handling
| Error | Cause | Solution |
|-------|-------|----------|
| Error 1 | Reason | How to fix |

## Related Workflows
- Before: [Workflow name]
- After: [Workflow name]
```

## Customization Guide

1. **Identify Common Tasks**: List repetitive development tasks in your workflow
2. **Document Current Process**: Write down how tasks are currently performed
3. **Create Workflow File**: Use the template above
4. **Test with Claude**: Verify Claude can follow the workflow
5. **Iterate**: Refine based on feedback

## Usage Notes

- Reference workflows from `CLAUDE.md` for quick lookup
- Keep workflows focused on ONE task
- Use templates from `02-templates/` within workflows
- Link to standards from `04-standards/` when relevant

## Adding New Workflows

1. Create file with descriptive name: `{task}-workflow.md`
2. Follow the standard structure (trigger, prerequisites, steps, etc.)
3. Update this README with a link
4. Reference from `CLAUDE.md` if it's a common task

---

**Customize this folder** by creating workflow files specific to your team's development process.