# Documentation Workflow

This document defines how to maintain the memory bank and project documentation for the intapi-assistant project.

## Documentation Principles

### Memory Bank as Source of Truth
- **ALWAYS** The memory bank is the **canonical source** for all project knowledge
- All team members and AI assistants must load and reference it
- Keep documentation updated alongside code changes
- Document decisions, context, and rationale, not just facts

### Documentation Philosophy
1. **Living Documentation**: Docs evolve with the project
2. **Just-in-Time**: Document when information is needed
3. **Single Source**: One place for each piece of information
4. **Searchable**: Organize for easy discovery
5. **Actionable**: Docs should enable action, not just inform

## Memory Bank Structure

### Core Sections

**foundation/** - Unchanging project fundamentals
- Project overview and structure
- Technology stack and versions
- Module architecture
- Build configuration
- Product and technical context

**context/** - Living project state
- Active work and focus
- Progress and status
- System patterns and decisions

**workflows/** - How the team works
- Development workflow
- Code review workflow
- Testing workflow
- Deployment workflow
- Documentation workflow
- Collaboration workflow

**agents/** - Team roles and responsibilities
- Developer agent
- Reviewer agent
- QA agent
- AI assistant agent
- Documentation agent
- Automation agent

**ticket-administration/** - Ticket-driven work
- Workflows and lifecycle
- Templates and standards
- Best practices
- Individual ticket folders (JIRA/, LOCAL/)

**prompts/** - AI assistant prompts
- Working capital prompts
- Glossaries and context
- Initial context

## When to Update Documentation

### Always Update When:
- Adding or changing major features
- Modifying architecture or design patterns
- Changing dependencies or technology stack
- Adding new modules or components
- Creating new workflows or processes
- Making architectural decisions
- Discovering important context or gotchas

### How to Know What to Update:
Ask yourself:
1. "Would a new team member need to know this?"
2. "Will I forget this in 3 months?"
3. "Does this change how we work?"
4. "Is this a decision that might be questioned later?"

If yes to any → Update documentation

## Documentation Workflow

### 1. Start of Ticket/Task

**Create Ticket Documentation Folder**
```bash
# For JIRA tickets
mkdir -p memory-bank/ticket-administration/JIRA/AIT-XXX/V1

# For local tasks
mkdir -p memory-bank/ticket-administration/LOCAL/AIT-local-XXX
```

**Create Initial README**
```markdown
# AIT-XXX: [Ticket Title]

## Context
[Brief description of the task/problem]

## Approach
[Initial thoughts on implementation]

## Decisions
- [Decision 1 and rationale]
- [Decision 2 and rationale]

## Progress
- [ ] Task 1
- [ ] Task 2
- [ ] Documentation updated

## Notes
[Any observations, challenges, or learnings]

---
_Created: 2025-10-09_
_Last Updated: 2025-10-09_
```

### 2. During Development

**Update Ticket Documentation**
```bash
# Document decisions as you make them
# Update progress checklist
# Add notes about challenges or solutions
# Document any deviations from plan
```

**Update Relevant Memory Bank Sections**

If architectural change:
```bash
# Update foundation/03-module-architecture.md
# Update context/03-system-patterns.md
# Update context/01-active-context.md
```

If new dependency:
```bash
# Update foundation/02-technology-stack.md
```

If new workflow or process:
```bash
# Create or update workflows/*.md
```

### 3. During Code Review

**Documentation Review Checklist**
- [ ] Ticket documentation complete
- [ ] Memory bank updated if needed
- [ ] Inline code comments added for complex logic
- [ ] README updated if public API changed
- [ ] CHANGELOG.md updated for release

### 4. After Merge

**Finalize Documentation**
```bash
# Mark ticket documentation as complete
# Update context/02-progress.md with what's done
# Update context/01-active-context.md if focus shifted
# Archive old/obsolete documentation
```

## Documentation Templates

### Ticket README Template
```markdown
# AIT-XXX: [Ticket Title]

## Summary
[Executive summary - non-technical, what and why]

## Context
- **Problem**: [What problem are we solving?]
- **Impact**: [Who is affected? Why does it matter?]
- **References**: [Related tickets, docs, discussions]

## Approach
[Technical approach and implementation strategy]

## Architecture Decisions
### Decision 1: [Title]
- **Context**: [Why this decision was needed]
- **Options**: [Alternatives considered]
- **Choice**: [What was chosen]
- **Rationale**: [Why this was chosen]
- **Consequences**: [Trade-offs and implications]

## Implementation
### Changes Made
- [Change 1]
- [Change 2]

### Files Modified
- `path/to/file1.groovy` - [What changed]
- `path/to/file2.groovy` - [What changed]

### Tests Added
- `TestClass1Spec` - [What it tests]
- `TestClass2IntegrationTest` - [What it tests]

## Testing
### Manual Testing
1. [Step 1]
2. [Step 2]
3. [Expected result]

### Automated Testing
- Unit tests: X added/modified
- Integration tests: Y added/modified

## Deployment Notes
[Any special deployment considerations]

## Lessons Learned
[What went well, what didn't, what to do differently next time]

---
_Created: 2025-10-09_
_Completed: 2025-10-09_
```

### Architecture Decision Record (ADR) Template
```markdown
# ADR-XXX: [Title]

## Status
[Proposed | Accepted | Deprecated | Superseded]

## Context
[What is the issue that we're seeing that is motivating this decision or change?]

## Decision
[What is the change that we're proposing and/or doing?]

## Consequences
### Positive
- [Positive consequence 1]
- [Positive consequence 2]

### Negative
- [Negative consequence 1]
- [Negative consequence 2]

### Neutral
- [Neutral consequence 1]

## Alternatives Considered
### Alternative 1: [Name]
- **Pros**: [Advantages]
- **Cons**: [Disadvantages]
- **Why not chosen**: [Reason]

### Alternative 2: [Name]
- **Pros**: [Advantages]
- **Cons**: [Disadvantages]
- **Why not chosen**: [Reason]

## References
- [Link 1]
- [Link 2]

---
_Created: 2025-10-09_
_Last Updated: 2025-10-09_
```

## AI Assistant Documentation Workflow

### For Claude Code and AI Assistants

**Always Start with Memory Bank**
```markdown
1. Load memory-bank/README.md first
2. Load all foundation documents
3. Load relevant ticket documentation
4. Load applicable workflow documents
5. Load agent role definitions
```

**Document As You Work**
```markdown
1. Update ticket README with decisions
2. Note any deviations from plan
3. Document new patterns discovered
4. Update relevant memory bank sections
5. Create executive summaries
```

**Before Completing Task**
```markdown
1. Verify all documentation is complete
2. Update progress indicators
3. Create executive summary for ticket comments
4. Check cross-references are correct
5. Verify links work
```

## Documentation Best Practices

### Writing Style
- **Clear and Concise**: Get to the point quickly
- **Active Voice**: "The service processes requests" not "Requests are processed"
- **Present Tense**: "The system does X" not "The system will do X"
- **Specific**: Use concrete examples, not vague descriptions
- **Scannable**: Use headers, lists, code blocks

### Formatting
```markdown
# Level 1 Header - Document Title

## Level 2 Header - Major Sections

### Level 3 Header - Subsections

- Bullet points for lists
- Use `-` for bullets, not `*`

1. Numbered lists for sequences
2. Step-by-step instructions

`Inline code` for file names, commands, variables

\`\`\`bash
# Code blocks for multi-line code
mise run build
\`\`\`

**Bold** for emphasis on important terms
_Italic_ for less emphasis

> Blockquotes for important notes or warnings

[Links](path/to/file.md) for cross-references
```

### Code Examples
- Include runnable examples
- Show expected output
- Comment complex parts
- Use realistic data

### Updates
- Add "Last updated" date at bottom
- Keep historical context if relevant
- Archive obsolete docs, don't delete
- Update cross-references when moving files

## Documentation Maintenance

### Regular Reviews
- **Weekly**: Check 01-active-context.md is current
- **Monthly**: Review 02-progress.md for accuracy
- **Quarterly**: Audit entire memory bank for obsolete content
- **Per Release**: Update technology stack versions

### Archiving Old Documentation
```bash
# Create archive folder
mkdir -p memory-bank/archive/2025-Q3

# Move obsolete docs
mv memory-bank/ticket-administration/JIRA/AIT-OLD memory-bank/archive/2025-Q3/

# Update links in affected files
```

### Documentation Debt
Track documentation debt like technical debt:
- Tag TODOs in docs: `<!-- TODO: Update this section -->`
- Create tickets for major doc updates
- Address during refactoring work

## Tools and Helpers

### Markdown Linting
```bash
# Check markdown formatting
markdownlint memory-bank/**/*.md

# Auto-fix formatting issues
markdownlint --fix memory-bank/**/*.md
```

### Link Checking
```bash
# Check for broken links
find memory-bank -name "*.md" -exec markdown-link-check {} \;
```

### Documentation Generation
```groovy
// Groovydoc for Groovy code
gradle groovydoc

// View generated docs
open build/docs/groovydoc/index.html
```

## Troubleshooting Documentation

### Issue: Can't Find Documentation
**Solution**: Use grep to search memory bank
```bash
grep -r "search term" memory-bank/
```

### Issue: Outdated Information
**Solution**: Check last updated date, verify with code
```bash
# Find when file was last modified
git log -1 --format="%ai" memory-bank/path/to/file.md
```

### Issue: Conflicting Information
**Solution**: Memory bank takes precedence over other sources
1. Check memory-bank first
2. Verify with actual code
3. Update documentation to match reality
4. Note source of confusion to prevent future issues

---

_Last updated: 2025-10-09_