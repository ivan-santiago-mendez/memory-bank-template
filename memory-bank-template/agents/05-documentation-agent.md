# Documentation Agent

Responsibilities for maintaining the memory bank and project documentation.

## Core Responsibilities

- [ ] Keep memory bank up to date
- [ ] Review documentation in PRs
- [ ] Identify documentation gaps
- [ ] Improve documentation clarity
- [ ] Maintain cross-references
- [ ] Archive obsolete documentation
- [ ] Ensure consistency across docs

## Documentation Maintenance

### Daily Tasks
- Review PRs for documentation updates
- Update 01-active-context.md as work shifts
- Keep 02-progress.md current
- Document decisions as they're made

### Weekly Tasks
- Review 01-active-context.md for accuracy
- Check for broken links
- Update ticket documentation
- Identify documentation debt

### Monthly Tasks
- Review entire memory bank
- Archive obsolete content
- Update technology stack versions
- Refresh examples and screenshots

### Quarterly Tasks
- Major memory bank audit
- Reorganize if needed
- Update all "last updated" dates
- Review and improve structure

## Documentation Review Checklist

### For PRs
- [ ] Ticket documentation complete
- [ ] Memory bank updated if needed
- [ ] Inline comments for complex code
- [ ] README updated if API changed
- [ ] Cross-references correct
- [ ] Formatting consistent
- [ ] Links work

### For Memory Bank Updates
- [ ] Content is accurate and current
- [ ] Structure follows conventions
- [ ] Formatting is consistent
- [ ] Examples are working
- [ ] Cross-references are correct
- [ ] "Last updated" date added
- [ ] Related docs updated

## Documentation Standards

### Formatting
```markdown
# Title (H1) - Once per document

## Major Section (H2)

### Subsection (H3)

- Bullet lists use `-`
- Not asterisks

1. Numbered lists
2. For sequences

`Inline code` for file names, commands

\`\`\`bash
# Code blocks for multi-line
mise run build
\`\`\`

**Bold** for emphasis

[Links](path/to/file.md)
```

### Writing Style
- Active voice: "The service processes requests"
- Present tense: "The system does X"
- Clear and concise
- Specific examples
- Scannable (headers, lists)

### File Organization
```
memory-bank/
├── README.md (index)
├── foundation/ (unchanging fundamentals)
├── context/ (living project state)
├── workflows/ (how team works)
├── agents/ (role definitions)
├── ticket-administration/ (ticket-driven work)
└── prompts/ (AI assistant prompts)
```

## Common Documentation Tasks

### Updating Technology Stack
```markdown
# When dependency changes:
1. Update foundation/02-technology-stack.md
2. Add version number
3. Note why changed
4. Update "last updated" date
```

### Documenting Architectural Changes
```markdown
# When architecture changes:
1. Update foundation/03-module-architecture.md
2. Update context/03-system-patterns.md
3. Consider creating ADR in ticket-administration/JIRA/AIT-ADR/
4. Update diagrams if applicable
```

### Creating Ticket Documentation
```markdown
# For each ticket:
1. Create folder: memory-bank/ticket-administration/JIRA/AIT-XXX/V1/
2. Create README.md with template
3. Document approach and decisions
4. Update as work progresses
5. Complete before PR merge
```

### Archiving Old Documentation
```bash
# Create archive folder
mkdir -p memory-bank/archive/2025-Q4

# Move obsolete docs
mv old-doc.md memory-bank/archive/2025-Q4/

# Update references in other files
# Add note in archive explaining why archived
```

## Documentation Quality

### Good Documentation:
- ✅ Accurate and up to date
- ✅ Clear and concise
- ✅ Well-organized and scannable
- ✅ Includes working examples
- ✅ Has correct cross-references
- ✅ Uses consistent formatting
- ✅ Addresses user needs

### Poor Documentation:
- ❌ Outdated or incorrect
- ❌ Vague or confusing
- ❌ Poorly organized
- ❌ No examples
- ❌ Broken links
- ❌ Inconsistent formatting
- ❌ Doesn't answer questions

## Tools and Automation

### Markdown Linting
```bash
# Check formatting
markdownlint memory-bank/**/*.md

# Auto-fix
markdownlint --fix memory-bank/**/*.md
```

### Link Checking
```bash
# Find broken links
find memory-bank -name "*.md" -exec markdown-link-check {} \;
```

### Search and Update
```bash
# Find all references to a term
grep -r "search term" memory-bank/

# Find files needing updates
find memory-bank -name "*.md" -mtime +90
```

## Success Criteria

### You're a Good Documentation Agent When:
- ✅ Documentation is always current
- ✅ Links never broken
- ✅ New team members find docs helpful
- ✅ Documentation gaps identified quickly
- ✅ Consistent quality across all docs
- ✅ Archive is well-organized

---

_Last updated: 2025-10-09_