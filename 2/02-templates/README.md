# Templates Catalog

Reusable templates for creating structured artifacts. Use these to ensure consistency.

## Purpose

Templates provide standardized formats for common artifacts (tickets, PRs, commits, etc.). They ensure consistency across the team and help Claude Code generate properly formatted content.

## Available Templates (Template)

### Ticket Templates
- **ticket-template.md** - Comprehensive template for creating tickets
  - User Story/Task format
  - Bug Report format
  - Technical Task format
  - Epic format

### Context Folder Templates
- **local-draft-template.md** - Draft ticket requirements before creating in ticket system
- **ticket-context-readme-template.md** - Document fetched tickets
- **version-readme-template.md** - Version-specific documentation for V0/V1/V2 implementations

### Git Templates
- **pr-template.md** - PR description format
- **commit-message-template.md** - Commit message format

### Code Review Templates
- **code-review-checklist.md** - Review criteria checklist

### Communication Templates
- **notification-template.md** - Team notification formats (Slack/Teams/etc.)

## Template Structure

Each template file should contain:

### 1. Format
The actual template with placeholders in `[BRACKETS]`

### 2. Guidelines
Rules for filling out the template

### 3. Example
A filled-out example showing proper usage

### 4. Usage
Which workflow references this template

## Example Template Format

```markdown
# [Template Name]

## Format

```
[Template structure with placeholders]
```

## Guidelines
1. Guideline for filling out
2. Another guideline
3. When to use optional sections

## Example

```
[Filled-out example]
```

## Usage
- Used by: [workflow-name.md]
- Created by: [Role/Person]
- Reviewed by: [Role/Person]
```

## Customization Guide

1. **Identify Artifacts**: List all recurring artifacts your team creates
2. **Document Current Format**: Capture existing templates or formats
3. **Standardize**: Create consistent template structure
4. **Add Examples**: Provide real examples (anonymized)
5. **Link from Workflows**: Reference templates in workflow files

## Template Variables

Common placeholders to use:
- `[PROJECT_NAME]` - Your project name
- `[TICKET_ID]` - Ticket identifier (e.g., AIT-123, PROJ-456)
- `[AUTHOR]` - Person creating the artifact
- `[DATE]` - Creation date
- `[VERSION]` - Version number
- `[DESCRIPTION]` - Detailed description
- `[JIRA/LINEAR/GITHUB]` - Ticket system name

## Usage Notes

- Templates define **structure and format** only
- Workflows in `01-workflows/` reference these templates
- Keep templates generic enough to reuse
- Customize placeholders for your project

## Adding New Templates

1. Create file with descriptive name: `{artifact}-template.md`
2. Include format, guidelines, example, and usage
3. Update this README with a link
4. Reference from relevant workflow in `01-workflows/`

---

**Customize this folder** by creating templates that match your team's artifact formats and standards.