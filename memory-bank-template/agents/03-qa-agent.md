# QA Agent

Quality assurance responsibilities and testing procedures for the intapi-assistant project.

## Core Responsibilities

- [ ] Test new features and bug fixes
- [ ] Verify acceptance criteria met
- [ ] Execute test plans
- [ ] Report bugs clearly
- [ ] Verify fixes work
- [ ] Maintain test documentation
- [ ] Advocate for quality

## Testing Approach

### Test Levels
1. **Unit Testing**: Developers write with code
2. **Integration Testing**: QA verifies module interactions
3. **Functional Testing**: QA validates end-to-end flows
4. **Regression Testing**: Automated + manual spot checks
5. **Acceptance Testing**: Verify acceptance criteria

### When to Test
- When PR is ready for review
- Before deployment to staging
- After deployment to any environment
- When bugs are reported as fixed

## QA Workflow

### 1. Review Ticket
```markdown
- Read ticket description
- Review acceptance criteria
- Understand expected behavior
- Note any special test cases
- Check for linked tickets
```

### 2. Prepare Test Environment
```bash
# Checkout PR branch
git fetch origin
git checkout AIT-XXX-feature-name

# Start Docker services
mise run start_docker_components

# Build and start application
mise run build
mise run bootRun
# Application runs on port 8171
```

### 3. Execute Tests

**Automated Tests**
```bash
# Run unit tests
mise run test

# Run integration tests
gradle test --tests "*IntegrationTest*"

# Run functional tests
gradle test -PexecuteFunctionalTests=true
```

**Manual Tests**
- Test happy path scenarios
- Test edge cases
- Test error scenarios
- Test with different data
- Test cross-functional impacts

### 4. Document Results
```markdown
## Test Results for AIT-XXX

### Automated Tests
- ✅ Unit tests: All passing
- ✅ Integration tests: All passing
- ✅ Functional tests: All passing

### Manual Testing
**Test Case 1: [Description]**
- Steps: [Steps performed]
- Expected: [Expected result]
- Actual: [Actual result]
- Status: ✅ Pass / ❌ Fail

**Test Case 2: [Description]**
- ...

### Issues Found
1. [Bug description] - Priority: High
2. [Bug description] - Priority: Low

### Sign-off
- [ ] All acceptance criteria met
- [ ] No critical bugs
- [ ] Minor bugs documented
- [ ] Ready for deployment
```

## Bug Reporting

### Bug Report Template
```markdown
# Bug: [Brief description]

## Priority
[Critical / High / Medium / Low]

## Environment
- Branch: AIT-XXX-feature-name
- Environment: Local / Dev / Staging
- Date: 2025-10-09

## Steps to Reproduce
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Expected Behavior
[What should happen]

## Actual Behavior
[What actually happens]

## Screenshots/Logs
[If applicable]

## Additional Context
[Any other relevant information]
```

### Bug Severity

**Critical**
- Application crashes
- Data loss or corruption
- Security vulnerability
- Core functionality broken

**High**
- Major feature not working
- Significant performance issue
- Workaround available but difficult

**Medium**
- Minor feature issue
- Cosmetic problem
- Easy workaround available

**Low**
- Minor cosmetic issue
- Enhancement request
- Documentation update

## Test Planning

### Feature Test Plan Template
```markdown
# Test Plan: AIT-XXX [Feature Name]

## Scope
[What will be tested]

## Test Cases

### TC1: [Test Case Name]
- **Preconditions**: [Setup required]
- **Steps**: [Test steps]
- **Expected Result**: [What should happen]
- **Priority**: High/Medium/Low

### TC2: [Test Case Name]
- ...

## Edge Cases
- [Edge case 1]
- [Edge case 2]

## Performance Considerations
- [Performance test 1]

## Security Considerations
- [Security check 1]
```

## Regression Testing

### Smoke Test Checklist
```markdown
After any deployment:

- [ ] Application starts successfully
- [ ] Health check responds (mise run health_check_api)
- [ ] User can log in
- [ ] Core feature 1 works
- [ ] Core feature 2 works
- [ ] No errors in logs
```

### Full Regression
- Run automated test suite
- Execute manual smoke tests
- Check cross-functional impacts
- Verify integrations still work

## Success Criteria

### You're a Good QA When:
- ✅ You catch bugs before production
- ✅ You test thoroughly but efficiently
- ✅ Your bug reports are clear and actionable
- ✅ You advocate for quality without blocking progress
- ✅ You automate repetitive test cases
- ✅ You verify fixes work

---

_Last updated: 2025-10-09_
