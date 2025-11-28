# Example Template

Use this as a template for creating new template files.

---

# [Template Name]

Brief description of what artifact this template is for.

## Format

```
[TEMPLATE STRUCTURE WITH PLACEHOLDERS]

Title: [Brief descriptive title]

Section 1: [SECTION_NAME]
[Placeholder for content]

Section 2: [SECTION_NAME]
- [List item placeholder]
- [List item placeholder]

Section 3: [SECTION_NAME]
- [ ] [Checkbox item]
- [ ] [Checkbox item]

Footer:
[Footer information]
```

## Guidelines

Rules for filling out this template:

### Required Sections
1. **[Section 1]**: [What to include, how to format]
2. **[Section 2]**: [What to include, how to format]
3. **[Section 3]**: [What to include, how to format]

### Optional Sections
- **[Optional Section]**: [When to include, what to put]

### Placeholders
- `[PLACEHOLDER_NAME]`: [What this represents, examples]
- `[ANOTHER_PLACEHOLDER]`: [What this represents, examples]

### Formatting Rules
- **Titles**: [How to format]
- **Lists**: [When to use bullets vs. numbered]
- **Checkboxes**: [When to use]
- **Length**: [Recommended length guidelines]

### When to Use
Use this template when:
- Situation 1
- Situation 2
- Situation 3

Don't use when:
- Situation 1
- Situation 2

## Example

Here's a filled-out example:

```
Real Example Title: Implement User Authentication

Section 1: Description
We need to implement OAuth2 authentication for the user login flow.
This will replace the current basic auth system and provide better
security and user experience.

Section 2: Implementation Details
- Add OAuth2 library dependency
- Create authentication middleware
- Update login endpoints
- Add token refresh logic

Section 3: Acceptance Criteria
- [ ] Users can log in with OAuth2
- [ ] Tokens are properly refreshed
- [ ] Old basic auth still works during transition
- [ ] Documentation is updated

Footer:
Story Points: 5
Priority: High
Labels: security, authentication
```

## Common Mistakes

❌ **Mistake 1**: [What people often do wrong]
✅ **Instead**: [What to do correctly]

❌ **Mistake 2**: [What people often do wrong]
✅ **Instead**: [What to do correctly]

## Usage

### In Workflows
This template is used by:
- `memory-bank/01-workflows/[workflow-name].md` - [When/how]

### Creating from Template
```bash
# Copy template to create new artifact
cp memory-bank/02-templates/[template-name].md [destination]

# Fill in placeholders
# [Instructions]
```

## Related Templates

- `[other-template].md` - [Relationship/when to use instead]
- `[another-template].md` - [Relationship/when to use instead]

---

**Customization Notes**: [Any project-specific notes about adapting this template]