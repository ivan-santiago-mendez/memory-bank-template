# Code Review Workflow

This document defines the pull request creation, review, and approval process for the intapi-assistant project.

## Pull Request Creation

### Prerequisites Checklist

Before creating a PR, ensure:
- [ ] All tests pass (`mise run test`)
- [ ] Project builds successfully (`mise run build`)
- [ ] Application runs without errors (`mise run bootRun`)
- [ ] Code follows Groovy guidelines from CLAUDE.md
- [ ] Ticket documentation is complete and up-to-date
- [ ] Commit messages reference ticket number
- [ ] Memory bank updated if architectural changes made

### Creating the Pull Request

#### 1. Finalize Your Branch
```bash
# Ensure you're on your feature branch
git checkout AIT-XXX-VX-feature-name

# Pull latest main and rebase if needed
git fetch upstream main
git rebase upstream/main

# Resolve any conflicts

# Push final changes
git push origin AIT-XXX-VX-feature-name
```

#### 2. Create PR via GitHub
```bash
# Option 1: Use GitHub CLI
gh pr create --title "feat(AIT-XXX): Feature Title" \
  --body "$(cat <<'EOF'
## Summary
Brief executive summary of changes (non-technical)

## Changes
- Change 1
- Change 2
- Change 3

## Testing
- Test approach 1
- Test approach 2

## Documentation
- Updated [other relevant docs]

## Complexity
[Low/Medium/High]

🤖
EOF
)"

# Option 2: Use GitHub web interface
# Push branch and click "Create Pull Request" in GitHub
```

#### 3. PR Title Format
```
<type>: AIT-XXX: <Brief description>

Examples:
feat(AIT-645): Add Spring AI Advisors API with MessageChatMemoryAdvisor
fix(AIT-640): Resolve Spring AI 1.0.0 compatibility issues
docs(AIT-636): Update memory bank with MCP integration strategy
refactor(AIT-654): Implement MCP client integration
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `refactor`: Code restructuring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

#### 4. PR Description Template
```markdown
## Summary
[Executive summary - what problem does this solve?]

## Context
- Ticket: [AIT-XXX](https://taulia.atlassian.net/browse/AIT-XXX)
- Related PRs: [if any]

## Changes
### Core Changes
- [Main change 1]
- [Main change 2]

### Supporting Changes
- [Supporting change 1]
- [Supporting change 2]

## Testing
### Automated Tests
- [Test class 1]: [What it tests]
- [Test class 2]: [What it tests]

### Manual Testing
1. [Step 1]
2. [Step 2]
3. [Expected result]

## Complexity Metric
[Low / Medium / High]
- **Low**: Simple change, limited scope, no architectural impact
- **Medium**: Moderate complexity, some architectural consideration
- **High**: Complex change, significant architectural impact

## Checklist
- [ ] Tests pass locally
- [ ] Build succeeds
- [ ] Application runs successfully
- [ ] Code follows project standards
- [ ] Documentation updated
- [ ] Commit messages follow convention

🤖
```

## Code Review Process

### For Reviewers

#### 1. Review Preparation
```bash
# Checkout the PR branch
git fetch origin
git checkout AIT-XXX-VX-feature-name

# Start Docker services
mise run start_docker_components

# Build the project
mise run build

# Run tests
mise run test
```

#### 2. Review Checklist

**Code Quality**
- [ ] Code follows Groovy guidelines from CLAUDE.md
- [ ] No code smells or anti-patterns
- [ ] Proper error handling
- [ ] Logging appropriate and meaningful
- [ ] No hardcoded values (use configuration)

**Architecture**
- [ ] Changes align with project architecture (memory-bank/foundation/03-module-architecture.md)
- [ ] Proper module dependencies (server → services → tdo/core-data)
- [ ] No circular dependencies
- [ ] Spring AI patterns followed correctly

**Testing**
- [ ] Tests cover new functionality
- [ ] Tests cover edge cases and error scenarios
- [ ] Integration tests provided for API changes
- [ ] Tests are meaningful and maintainable

**Documentation**
- [ ] Memory bank updated appropriately
- [ ] Ticket documentation complete
- [ ] Inline comments for complex logic
- [ ] README or configuration changes documented

**Security**
- [ ] No secrets or credentials in code
- [ ] Proper input validation
- [ ] Authentication/authorization maintained
- [ ] No SQL injection or XSS vulnerabilities

**Performance**
- [ ] No obvious performance issues
- [ ] Database queries optimized
- [ ] Caching used appropriately
- [ ] No memory leaks

#### 3. Provide Feedback

**Approval (✅)**
```markdown
✅ LGTM - Looks good to merge

Great work on [specific positive aspect].

Code is clean, tests are comprehensive, and documentation is thorough.

Approved to merge.
```

**Request Changes (❌)**
```markdown
❌ Requesting changes

Overall approach is good, but need some adjustments:

**Critical:**
1. [Critical issue 1] - [Why it's important]
2. [Critical issue 2] - [Why it's important]

**Suggestions:**
1. [Suggestion 1] - [Benefit]
2. [Suggestion 2] - [Benefit]

**Questions:**
1. [Question 1]
2. [Question 2]

Please address critical items before re-review.
```

**Comment (💬)**
```markdown
💬 Some thoughts and questions

The implementation looks solid. A few suggestions:

1. [Non-blocking suggestion 1]
2. [Question about approach]

These are optional improvements. Feel free to address in a follow-up PR if preferred.
```

#### 4. Review Standards

**Response Time**
- Initial review within 24 hours
- Follow-up review within 4 hours after changes

**Review Depth**
- Small PRs (<200 lines): Thorough line-by-line review
- Medium PRs (200-500 lines): Focus on key changes and architecture
- Large PRs (>500 lines): Request breakdown or focus on high-risk areas

**Tone**
- Be constructive and specific
- Explain the "why" behind feedback
- Acknowledge good practices
- Avoid personal criticism

### For PR Authors

#### 1. Responding to Feedback

**Acknowledge All Comments**
```markdown
Thanks for the thorough review!

**Addressed:**
- ✅ Fixed issue 1 in commit abc123
- ✅ Refactored as suggested in commit def456

**Questions:**
- Re: suggestion 2 - I chose approach X because [reasoning]. Open to alternatives.

**Follow-up:**
- Suggestion 3 would require [significant refactoring]. Can we do this in AIT-YYY?
```

**Make Changes**
```bash
# Make requested changes
# [edit files]

# Commit with clear messages
git add .
git commit -m "review: Address code review feedback from @reviewer

- Fixed issue 1 as requested
- Refactored code per suggestion
- Added test coverage for edge case

🤖"

# Push changes
git push origin AIT-XXX-VX-feature-name
```

#### 2. Re-request Review
After addressing feedback:
```markdown
@reviewer Ready for re-review!

All requested changes have been addressed:
- [Summary of changes made]
- [Commits: abc123, def456]

Let me know if you need any clarification.
```

## Merge Process

### Merge Requirements
- [ ] At least 1 approval from team member
- [ ] All CI checks passing
- [ ] No unresolved conversations
- [ ] Branch up-to-date with main
- [ ] All tests passing

### Merge Steps

#### 1. Final Pre-Merge Check
```bash
# Update with latest main
git checkout AIT-XXX-feature-name
git fetch origin main
git rebase origin/main

# Verify tests still pass
mise run test

# Push updated branch
git push origin AIT-XXX-feature-name --force-with-lease
```

#### 2. Merge via GitHub
```bash
# Option 1: GitHub CLI
gh pr merge --squash --delete-branch

# Option 2: GitHub web interface
# Click "Squash and merge"
# Verify commit message
# Confirm merge
# Delete branch
```

#### 3. Post-Merge Actions
```bash
# Update local main
git checkout main
git pull origin main

# Update JIRA ticket
# Move ticket to "Done" or "QA/Testing"

# Add ticket comment with executive summary
# Example:
# Summary: Implemented MCP client integration for intapi-data-analytics
# Complexity: Medium
# [Brief non-technical description of changes]

# Clean up local branch
git branch -d AIT-XXX-feature-name
```

#### 4. Verify Deployment (if applicable)
```bash
# Monitor deployment pipeline
# Verify changes in target environment
# Check application logs for errors
# Smoke test key functionality
```

## Special Cases

### Hotfix Process
```bash
# 1. Create hotfix branch from main
git checkout main
git pull origin main
git checkout -b AIT-XXX-hotfix-description

# 2. Make minimal fix
# [edit code]

# 3. Test thoroughly
mise run test

# 4. Create PR with HOTFIX label
gh pr create --title "fix(AIT-XXX): HOTFIX - Description" \
  --label "hotfix" \
  --body "Urgent fix for [issue]"

# 5. Request immediate review
# Tag reviewers directly

# 6. Merge ASAP after approval
```

### Documentation-Only PR
```markdown
## Summary
Documentation update for [topic]

## Changes
- Updated memory-bank/[path]
- No code changes

## Review Focus
- Accuracy of documentation
- Clarity and completeness
- Proper formatting and links

**Fast-track review requested** - documentation only
```

### Dependency Update PR
```markdown
## Summary
Update [dependency] from [old version] to [new version]

## Verification
- [ ] All tests pass with new version
- [ ] No breaking changes detected
- [ ] Application runs successfully
- [ ] Documentation updated in foundation/02-technology-stack.md

## Testing
- Ran full test suite
- Manual smoke testing completed
- No regressions identified
```

## Review Metrics

### Healthy Review Indicators
- Reviews completed within 24 hours
- Constructive, specific feedback
- Most PRs require 0-2 rounds of review
- Low rate of bugs escaping to production

### Red Flags
- PRs open for >3 days
- Multiple rounds of back-and-forth
- Rubber-stamp approvals without review
- Frequent post-merge issues

---

_Last updated: 2025-10-09_