# Example Workflow Template

Use this as a template for creating new workflow files.

---

# [Workflow Name]

Brief one-sentence description of what this workflow accomplishes.

## Trigger

**When to use this workflow:**
- Condition 1
- Condition 2
- Example: "User says 'do X'"

## Prerequisites

Things that must be in place before starting:
- [ ] Prerequisite 1 (how to check: `command`)
- [ ] Prerequisite 2 (how to verify)
- [ ] Prerequisite 3

## Steps

### Step 1: [Action Name]

**Action**: What Claude Code should do

**Tools**: Which tools to use (Read, Write, Edit, Bash, etc.)

**Details**:
- Sub-action 1
- Sub-action 2

**Example**:
```bash
command to run
```

**Output**: What to expect as result

### Step 2: [Action Name]

**Action**: Next thing to do

**Tools**: Tools required

**Details**:
- Sub-action 1
- Sub-action 2

**Output**: Expected result

### Step 3: [Action Name]

**Action**: What to do

**Tools**: Tools needed

**Details**:
- Sub-action 1
- Sub-action 2

**Output**: What comes out

## Success Criteria

How to verify the workflow completed successfully:
- [ ] Success criterion 1
- [ ] Success criterion 2
- [ ] Success criterion 3

## Error Handling

What to do when things go wrong:

| Error | Cause | Solution |
|-------|-------|----------|
| Error message 1 | Why it happens | How to fix |
| Error message 2 | Why it happens | How to fix |
| Error message 3 | Why it happens | How to fix |

## Related Workflows

- **Before this workflow**: [workflow-name.md] - [Why/when]
- **After this workflow**: [workflow-name.md] - [Why/when]
- **Alternative**: [workflow-name.md] - [When to use instead]

## Templates Used

- `memory-bank/02-templates/[template-name].md` - [When used in workflow]

## Standards Referenced

- `memory-bank/04-standards/[standard-name].md` - [How it applies]

## Notes

Additional context or special considerations:
- Note 1
- Note 2
- Note 3

---

**Example Usage**:

```
User: "[Example request that triggers this workflow]"

Claude:
1. [Does step 1]
2. [Does step 2]
3. [Does step 3]

Result: [What user sees]
```