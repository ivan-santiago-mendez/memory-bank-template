# Team Processes

Documentation for team collaboration processes, agile practices, and development workflow.

## Purpose

This folder documents how your team works together:
- Agile ceremonies and practices
- Estimation techniques
- Sprint planning
- Team roles and responsibilities
- Continuous improvement processes
- Velocity tracking and forecasting

## Recommended Files

### Agile Ceremonies
- **sprint-planning.md** - Sprint planning process
  - Planning meeting structure
  - Capacity calculation
  - Story selection criteria
  - Sprint goal definition

- **daily-standup.md** - Daily standup format
  - What to discuss
  - Time management
  - Blockers escalation

- **sprint-review.md** - Sprint review/demo process
  - Demo preparation
  - Stakeholder feedback
  - Acceptance criteria validation

- **retrospective.md** - Retrospective format
  - Retro formats (Start/Stop/Continue, etc.)
  - Action items tracking
  - Continuous improvement

### Estimation
- **story-point-estimation.md** - Estimation guidelines
  - Story point scale (Fibonacci, T-shirt, etc.)
  - Reference stories
  - Estimation techniques (Planning Poker, etc.)
  - What to consider when estimating

### Planning
- **velocity-planning.md** - Velocity tracking and forecasting
  - Calculating velocity
  - Forecasting delivery
  - Handling velocity changes
  - Planning releases

- **capacity-planning.md** - Team capacity calculation
  - Available hours per sprint
  - Time off considerations
  - Meeting overhead
  - Focus factor

### Roles
- **team-roles.md** - Roles and responsibilities
  - Product Owner
  - Scrum Master / Team Lead
  - Developers
  - QA
  - DevOps

### Workflow
- **ticket-lifecycle.md** - Ticket states and transitions
  - Ticket states (To Do, In Progress, Review, Done)
  - Transition criteria
  - Definition of Ready
  - Definition of Done

- **code-review-process.md** - Code review expectations
  - Review turnaround time
  - Review checklist
  - Approval requirements
  - Feedback guidelines

- **deployment-process.md** - How deployments work
  - Deployment schedule
  - Release process
  - Rollback procedures
  - Hotfix process

### Improvement
- **continuous-improvement.md** - How team improves
  - Metrics tracked
  - Experimentation process
  - Learning opportunities
  - Knowledge sharing

## Document Template

```markdown
# [Process Name]

## Purpose
[Why this process exists]

## When
[When this process happens]

## Who
[Who participates]

## Duration
[How long it takes]

## Prerequisites
- [ ] Prerequisite 1
- [ ] Prerequisite 2

## Process

### Step 1: [Phase Name]
**Duration**: [Time]
**Participants**: [Who]
**Activities**:
- Activity 1
- Activity 2

**Output**: [What's produced]

### Step 2: [Phase Name]
[Repeat structure]

## Success Criteria
- [ ] Criterion 1
- [ ] Criterion 2

## Common Pitfalls
| Pitfall | Solution |
|---------|----------|
| Pitfall 1 | How to avoid |

## Tools
- Tool 1: [Purpose]
- Tool 2: [Purpose]

## Metrics
[What to measure to ensure process health]

## Related Processes
- [Process 1] - [Relationship]
- [Process 2] - [Relationship]
```

## Example: Story Point Estimation

```markdown
# Story Point Estimation

## Purpose
Estimate relative complexity of work for sprint planning.

## Scale
Fibonacci: 1, 2, 3, 5, 8, 13, 21

## Reference Stories

### 1 Point - Trivial
- Update text in UI
- Fix typo in documentation
- Change log level

### 3 Points - Small
- Add new API endpoint (CRUD)
- Write unit tests for class
- Update configuration

### 5 Points - Medium
- Implement new feature (single component)
- Refactor module
- Fix complex bug

### 8 Points - Large
- New feature across multiple components
- Database migration
- Integration with external service

### 13+ Points - Too Large
- Should be broken down into smaller stories

## What to Consider
1. **Complexity**: How difficult is the logic?
2. **Unknowns**: How much discovery is needed?
3. **Dependencies**: What else must change?
4. **Testing**: How complex is testing?

## Process
1. Product Owner presents story
2. Clarify requirements
3. Everyone estimates simultaneously (Planning Poker)
4. Discuss differences (highest and lowest explain)
5. Re-estimate until consensus

## When Story is Too Large
- Break into smaller stories
- Create spike for investigation
- Defer until more information available
```

## Customization Guide

### Step 1: Document Current Processes
Write down how your team currently:
- Plans sprints
- Estimates work
- Reviews code
- Deploys changes
- Handles incidents
- Improves processes

### Step 2: Define Team Roles
Create `team-roles.md`:
- List all roles
- Define responsibilities
- Clarify decision authority
- Document escalation paths

### Step 3: Establish Estimation Standards
Create `story-point-estimation.md`:
- Choose scale (Fibonacci, T-shirt, etc.)
- Define reference stories
- Document factors to consider
- Explain estimation process

### Step 4: Map Ticket Lifecycle
Create `ticket-lifecycle.md`:
- List all ticket states
- Define transition criteria
- Document Definition of Ready
- Document Definition of Done

### Step 5: Track Velocity
Create `velocity-planning.md`:
- How to calculate velocity
- Historical velocity data
- How to forecast
- When to adjust velocity

### Step 6: Plan Ceremonies
For each agile ceremony:
- Document purpose
- Define schedule
- List participants
- Outline agenda
- Specify outputs

## Usage Notes

- Review and update processes regularly
- Document what actually happens (not ideal)
- Improve processes iteratively
- Get team buy-in on changes

## Integration with Other Folders

- **Workflows (01)**: Team processes inform development workflows
- **Templates (02)**: Ceremony outputs use templates
- **Architecture (03)**: Roles align with architecture
- **Standards (04)**: Processes enforce standards

## Metrics to Track

### Velocity Metrics
- Story points completed per sprint
- Story points committed vs. completed
- Velocity trend over time

### Quality Metrics
- Defect rate
- Code review turnaround time
- Test coverage
- Production incidents

### Process Metrics
- Estimation accuracy
- Sprint goal success rate
- Team satisfaction
- Cycle time

### Delivery Metrics
- Lead time
- Deployment frequency
- Change failure rate
- Mean time to recovery (MTTR)

## Common Agile Practices

### Scrum
- 2-week sprints
- Sprint planning, review, retro
- Daily standup
- Product backlog refinement

### Kanban
- Continuous flow
- WIP limits
- Pull system
- Lead time tracking

### Scrumban
- Hybrid approach
- Sprints with WIP limits
- Continuous refinement
- Flow-based metrics

## Continuous Improvement

### Retrospective Action Items
Track and follow up on retro actions:
- What was the action?
- Who owns it?
- Status?
- Impact?

### Experiments
Try new processes:
- Hypothesis
- Duration
- Metrics to track
- Decision criteria

### Learning
Knowledge sharing:
- Tech talks
- Pair programming
- Code reviews
- Documentation

## Troubleshooting

### Velocity dropping
**Check**:
- Team capacity changes?
- More unplanned work?
- Technical debt increasing?
- Estimation calibration?

### Estimation inaccurate
**Solution**:
- Review reference stories
- Retrospect on estimates
- Calibrate as team
- Break down larger stories

### Tickets stuck in review
**Solution**:
- Define review SLA
- Assign reviewers explicitly
- Parallelize reviews
- Improve PR quality

---

**Customize this folder** by documenting your team's specific processes, ceremonies, and collaboration practices.