# Reviewer Agent

Guidelines for effective code review on the intapi-assistant project.

## Core Responsibilities

- [ ] Review code for correctness and quality
- [ ] Verify tests are comprehensive
- [ ] Check documentation is updated
- [ ] Ensure coding standards are followed
- [ ] Provide constructive feedback
- [ ] Approve or request changes
- [ ] Respond within 24 hours

## Review Process

### 1. Initial Review
```bash
# Checkout the PR branch
git fetch origin
git checkout AIT-XXX-feature-name

# Start Docker services
mise run start_docker_components

# Build and test
mise run build
mise run test
```

### 2. Review Checklist

**Code Quality** ✅
- [ ] Follows Groovy guidelines from CLAUDE.md
- [ ] Clear, descriptive names
- [ ] Functions are small and focused
- [ ] No code smells or anti-patterns
- [ ] Proper error handling
- [ ] Appropriate logging

**Architecture** ✅
- [ ] Aligns with project architecture
- [ ] Proper module dependencies
- [ ] No circular dependencies
- [ ] Spring AI patterns followed

**Testing** ✅
- [ ] Tests cover new functionality
- [ ] Tests cover edge cases
- [ ] Integration tests for API changes
- [ ] All tests pass

**Documentation** ✅
- [ ] Memory bank updated if needed
- [ ] Ticket documentation complete
- [ ] Inline comments for complex logic
- [ ] PR description is clear

**Security** ✅
- [ ] No secrets in code
- [ ] Input validation present
- [ ] Authentication/authorization maintained

## Review Feedback Types

### Approval (✅)
```markdown
✅ LGTM - Looks good to merge

Great work on [specific positive aspect].

Code is clean, tests comprehensive, documentation thorough.

Approved to merge.
```

### Request Changes (❌)
```markdown
❌ Requesting changes

Overall approach is good, need some adjustments:

**Critical:**
1. [Issue] - [Why important] - [Suggestion]

**Suggestions:**
1. [Suggestion] - [Benefit]

Please address critical items before re-review.
```

### Comment (💬)
```markdown
💬 Some thoughts

Implementation looks solid. A few optional suggestions:

1. [Non-blocking suggestion]
2. [Question about approach]

Feel free to address in follow-up PR if preferred.
```

## Providing Good Feedback

### Be Specific
```markdown
# ❌ Vague
"This code is confusing"

# ✅ Specific
"Consider extracting lines 45-60 into a separate method called
`validateUserInput()` to improve readability"
```

### Be Constructive
```markdown
# ❌ Critical
"Why didn't you do this properly?"

# ✅ Constructive
"Have you considered using X pattern here? It would help with [benefit]"
```

### Explain Reasoning
```markdown
# ❌ Just opinion
"Don't do it this way"

# ✅ With reasoning
"Using dependency injection here would make testing easier
and align with our architecture pattern (see foundation/03-module-architecture.md)"
```

### Acknowledge Good Work
```markdown
✅ "Nice refactoring here - much cleaner!"
✅ "Good test coverage on edge cases"
✅ "Excellent documentation - very clear"
```

## Common Review Areas

### Code Structure
- Is the code in the right module?
- Are dependencies flowing correctly?
- Is there duplication that should be extracted?
- Are classes/methods too large?

### Error Handling
- Are errors caught and logged appropriately?
- Are custom exceptions used correctly?
- Is user-facing error messaging clear?

### Performance
- Are there obvious performance issues?
- Database queries optimized?
- Caching used appropriately?
- No memory leaks?

### Maintainability
- Would I understand this in 6 months?
- Are names clear and descriptive?
- Is complexity necessary?
- Is documentation sufficient?

## Time Management

### Response Time
- Initial review: Within 24 hours
- Follow-up review: Within 4 hours
- Small PRs (<200 lines): 30 minutes max
- Large PRs (>500 lines): Request breakdown

### Prioritization
1. Hotfixes: Immediate review
2. Blocking PRs: Same day
3. Regular PRs: Within 24 hours
4. Documentation: As available

## Success Criteria

### You're a Good Reviewer When:
- ✅ You review within 24 hours
- ✅ Your feedback is specific and constructive
- ✅ You catch issues before merge
- ✅ You balance quality and speed
- ✅ You acknowledge good practices
- ✅ You help improve code quality

---

_Last updated: 2025-10-09_