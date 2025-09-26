# Ticket Templates

This document provides standardized templates for creating tickets with proper story point estimation.

## User Story Template

```
**Title**: Should be concise and user-focused ("As a [type of user], I want to [action] or action-oriented for tasks (eg: "Implement X Feature") so that [*we can achieve XYZ]

**Description**:
Explain the goal/scope of this specific task within the larger context 

**Technical Notes**:
- Add details about where and what we are going to change in the current codebase
- Also add any architectural decisions or major design patterns if relevant to this specific item.
- Add component impacted details 
- Add API level details 

**Acceptance Criteria**:
I'll know this is done when…..
- Add AC in the form of checklist 
    - [ ] Criterion 1
    - [ ] Criterion 2
    - [ ] Criterion 3
- Add clear, testable statements that define when the story is "done"

**Testing & Verification**:
- Clearly define how the story will be tested, distinguishing between different levels:
- Unit Tests: What areas require new or updated unit tests? 
- Integration Tests: What integration tests to be added to test the functionality
- Manual Testing: Specific scenarios that need manual verification

**Story Points**: [1, 2, 3, 5, 8, 13]
**Estimation Rationale**:
- Complexity: [Low/Medium/High]
- Effort: [Small/Medium/Large]
- Uncertainty: [Low/Medium/High]
- Dependencies: [List any dependencies]
**Definition of Done**:
- [ ] Code implemented and reviewed
- [ ] Unit tests written and passing
- [ ] Integration tests passing
- [ ] Documentation updated
- [ ] Deployed to staging environment
```
## Bug Report Template

```
**Title**: [Brief description of the bug]

**Priority**: [Critical/High/Medium/Low]

**Description**:
[Detailed description of the issue]

**Steps to Reproduce**:
1. Step 1
2. Step 2
3. Step 3

**Expected Behavior**:
[What should happen]

**Actual Behavior**:
[What actually happens]

**Environment**:
- OS: [Operating System]
- Browser: [Browser and version]
- Version: [Application version]

**Story Points**: [1, 2, 3, 5, 8]
**Estimation Rationale**:
- Investigation effort: [Low/Medium/High]
- Fix complexity: [Simple/Moderate/Complex]
- Risk of regression: [Low/Medium/High]
- Testing requirements: [Basic/Moderate/Extensive]

**Definition of Done**:
- [ ] Root cause identified
- [ ] Fix implemented and reviewed
- [ ] Regression tests added
- [ ] Bug verified as resolved
- [ ] Documentation updated if needed
```

## Technical Task Template

```
**Title**: [Clear description of technical work]

**Type**: [Refactoring/Infrastructure/Tech Debt/Research]

**Description**:
[Detailed technical requirements and context]

**Technical Requirements**:
- Requirement 1
- Requirement 2
- Requirement 3

**Story Points**: [1, 2, 3, 5, 8, 13]
**Estimation Rationale**:
- Technical complexity: [Low/Medium/High]
- Research required: [None/Some/Extensive]
- Impact scope: [Limited/Moderate/Wide]
- Testing complexity: [Simple/Moderate/Complex]

**Risks and Mitigation**:
- Risk 1: [Description and mitigation]
- Risk 2: [Description and mitigation]

**Definition of Done**:
- [ ] Technical implementation complete
- [ ] Code reviewed and approved
- [ ] Performance benchmarks met
- [ ] Documentation updated
- [ ] No regression in existing functionality
```

## Epic Template

```
**Title**: [High-level feature or initiative]

**Strategic Goal**:
[How this epic aligns with business objectives]

**Description**:
[Comprehensive description of the epic scope]

**User Stories**:
- [ ] Story 1 ([X] points)
- [ ] Story 2 ([X] points)
- [ ] Story 3 ([X] points)

**Total Story Points**: [Sum of all stories]

**Success Metrics**:
- Metric 1: [Target value]
- Metric 2: [Target value]

**Dependencies**:
- Dependency 1
- Dependency 2

**Timeline**: [Expected duration based on story points and team velocity]

**Definition of Done**:
- [ ] All user stories completed
- [ ] Success metrics achieved
- [ ] User acceptance testing passed
- [ ] Production deployment successful
```

## Estimation Guidelines for Templates

### Quick Estimation Reference
- **1-2 Points**: Small changes, bug fixes, simple features
- **3-5 Points**: Medium features, moderate complexity
- **8 Points**: Large features, high complexity
- **13+ Points**: Should be broken down into smaller stories

### Estimation Factors to Consider
1. **Complexity**: Algorithm complexity, integration challenges
2. **Effort**: Development time, testing time, documentation
3. **Uncertainty**: Unknown requirements, new technology
4. **Dependencies**: External systems, team dependencies
5. **Risk**: Potential for scope creep, technical challenges

### Best Practices
- Always include estimation rationale
- Re-estimate if scope changes during implementation
- Use Planning Poker or similar collaborative techniques
- Track actual vs. estimated for continuous improvement
- Break down stories larger than 8 points

---

_Last updated: [YYYY-MM-DD]_