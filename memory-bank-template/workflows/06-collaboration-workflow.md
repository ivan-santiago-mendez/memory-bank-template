# Collaboration Workflow

This document defines team communication patterns, sync procedures, and decision-making processes for the intapi-assistant project.

## Communication Channels

### Primary Channels

**Slack/Teams** - Day-to-day communication
- **#intapi-assistant**: General discussion
- **#intapi-assistant-dev**: Technical discussions
- **#intapi-assistant-alerts**: CI/CD and monitoring alerts

**JIRA** - Work tracking
- All work items and tickets
- Sprint planning and backlog
- Status updates and progress tracking

**GitHub** - Code collaboration
- Pull requests and code reviews
- Issue tracking and discussions
- Documentation in memory bank

**Confluence** - Long-form documentation
- Architecture decisions
- Meeting notes
- Project planning docs

### Communication Guidelines

**Response Time Expectations**
- Urgent (production issue): < 15 minutes
- High priority (blocking): < 2 hours
- Normal priority: Same day
- Low priority: Within 2 days

**When to Use Which Channel**
- **Slack**: Quick questions, status updates, informal chat
- **JIRA**: Work items, bugs, feature requests
- **GitHub**: Code review, technical discussions about PRs
- **Email**: External communication, formal announcements

## Daily Collaboration

### Daily Standup (Async or Sync)

**Format**: Written or verbal (15 minutes max)

**Each team member shares**:
1. **Yesterday**: What I completed
2. **Today**: What I'm working on
3. **Blockers**: Anything preventing progress

**Example Standup Update**:
```markdown
**Yesterday**:
- ✅ Completed AIT-645: Added Spring AI Advisors API
- ✅ Code review for AIT-640

**Today**:
- 🚧 Working on AIT-654: MCP client integration
- 📝 Will update memory bank with findings

**Blockers**:
- None (or: Need clarification on MCP server configuration)
```

### Work Visibility

**Update JIRA Regularly**
- Move tickets as status changes
- Add comments with progress updates
- Link related tickets and PRs
- Estimate complexity

**Keep Memory Bank Current**
- Update ticket documentation as you work
- Document decisions immediately
- Update 01-active-context.md with current focus

## Code Collaboration

### Pair Programming

**When to Pair**:
- Complex or critical features
- Onboarding new team members
- Debugging difficult issues
- Learning new technologies

**Pairing Workflow**:
```bash
# 1. Set up shared session
# Use VS Code Live Share, tmux, or screen sharing

# 2. Define roles
# Driver: Writes code
# Navigator: Thinks ahead, reviews, suggests

# 3. Switch roles regularly (every 15-30 minutes)

# 4. Take breaks
# Every hour, 5-10 minute break

# 5. Document outcomes
# Update ticket README with decisions and learnings
```

### Code Review Collaboration

**Requesting Review**
```markdown
@reviewer Ready for review!

Context: This PR implements [feature]
Focus areas: [specific areas to review]
Testing: [what you tested]

Let me know if you have questions!
```

**Reviewing Code**
```markdown
# Be specific and constructive
❌ "This is wrong"
✅ "Consider using X instead of Y because [reason]"

# Acknowledge good work
✅ "Nice refactoring here, much cleaner!"

# Ask questions, don't demand
❌ "Why didn't you do X?"
✅ "Have you considered X? It might help with [benefit]"
```

**Resolving Disagreements**
1. Discuss rationale and trade-offs
2. Reference standards or patterns
3. If still stuck, escalate to team lead
4. Document final decision

## Sprint and Planning

### Sprint Planning (Every 2 Weeks)

**Goals**:
- Review sprint goals
- Estimate and commit to work
- Identify dependencies and risks

**Process**:
1. Review backlog
2. Estimate tickets (complexity: Low/Medium/High)
3. Assign tickets to sprint
4. Identify pairing opportunities
5. Confirm everyone understands their work

### Backlog Refinement (Weekly)

**Goals**:
- Clarify upcoming work
- Break down large tickets
- Ensure tickets are ready

**Process**:
1. Review upcoming tickets
2. Add acceptance criteria
3. Estimate complexity
4. Identify dependencies
5. Answer open questions

### Retrospective (End of Sprint)

**Format**: Start/Stop/Continue

**Each team member shares**:
- **Start**: What should we start doing?
- **Stop**: What should we stop doing?
- **Continue**: What's working well?

**Action Items**:
- Document decisions
- Assign owners
- Track in JIRA
- Review in next retro

## Decision-Making

### Decision Levels

**Level 1: Individual Decisions**
- Implementation details
- Test approaches
- Code style choices within guidelines

**Level 2: Team Decisions**
- Architecture patterns
- Library choices
- Process changes
- Requires: Discussion in PR or meeting

**Level 3: Lead Decisions**
- Major architecture changes
- Technology stack changes
- Requires: ADR (Architecture Decision Record)

### Making Technical Decisions

**Small Decisions (Level 1)**:
```markdown
# Make decision
# Document in ticket README
# Proceed with implementation
```

**Medium Decisions (Level 2)**:
```markdown
# 1. Propose in PR or Slack
"I'm considering X for [feature]. Thoughts?"

# 2. Discuss alternatives and trade-offs

# 3. Reach consensus or compromise

# 4. Document decision in ticket README

# 5. Proceed with implementation
```

**Large Decisions (Level 3)**:
```markdown
# 1. Create ADR draft
memory-bank/ticket-administration/JIRA/AIT-ADR/XXX/

# 2. Share with team for review

# 3. Discuss in team meeting

# 4. Finalize ADR with decision

# 5. Update architecture docs

# 6. Communicate to stakeholders
```

## Knowledge Sharing

### Documentation
- Write as you learn
- Share discoveries in ticket README
- Update memory bank
- Link related context

### Code Walkthroughs
```markdown
# When to do walkthrough:
- New major feature
- Complex refactoring
- New architecture pattern

# Format:
1. Screen share or recorded video
2. Walk through code and decisions
3. Answer questions
4. Document Q&A in ticket
```

### Brown Bag Sessions
- Weekly or bi-weekly
- Topics: New tech, patterns, tools
- Informal and interactive
- Document key points

### Mentoring
- Experienced devs mentor new members
- Regular check-ins
- Pair on challenging tasks
- Review code together

## Conflict Resolution

### Disagreements on Approach

**Step 1: Understand**
- Listen to other perspective
- Ask clarifying questions
- Assume good intentions

**Step 2: Discuss**
- Present your rationale
- Discuss trade-offs
- Reference standards or precedents

**Step 3: Compromise or Escalate**
- Find middle ground if possible
- If blocked, involve team lead
- Document final decision
- Move forward together

### Code Review Conflicts

**When reviewer and author disagree**:
1. Both explain reasoning
2. Consider bringing in third opinion
3. Refer to coding standards
4. Team lead makes final call if needed
5. Document decision for future reference

## Remote Collaboration

### Best Practices for Remote Work

**Communication**:
- Over-communicate status
- Use video for complex discussions
- Share screen when helpful
- Document async decisions

**Availability**:
- Set working hours in calendar
- Use status indicators (Slack, Teams)
- Communicate when stepping away
- Be responsive during work hours

**Meetings**:
- Camera on when possible
- Mute when not speaking
- Use chat for questions
- Record if async attendance needed

## Team Health

### Healthy Team Indicators
- PRs reviewed within 24 hours
- Standups are informative, not rote
- Conflicts resolved constructively
- Knowledge shared openly
- Retrospectives lead to improvements

### Warning Signs
- PRs sitting for days
- Same people always blocking others
- Passive-aggressive communication
- Knowledge hoarding
- Repeated issues never addressed

### Addressing Issues
1. Identify problem early
2. Discuss in retro or 1-on-1
3. Agree on solution
4. Track improvement
5. Celebrate when fixed

## Onboarding New Team Members

### Week 1: Setup and Context
```markdown
- [ ] Complete environment setup (see 01-development-workflow.md)
- [ ] Load memory bank (all foundation docs)
- [ ] Review recent tickets for context
- [ ] Shadow standup and meetings
- [ ] Ask lots of questions
```

### Week 2: First Contributions
```markdown
- [ ] Pick up small ticket (Low complexity)
- [ ] Pair with experienced dev
- [ ] Create first PR
- [ ] Participate in code review
- [ ] Update documentation
```

### Week 3-4: Ramp Up
```markdown
- [ ] Take on medium complexity ticket
- [ ] Lead a feature implementation
- [ ] Review others' code
- [ ] Share learnings with team
```

### Ongoing
```markdown
- Regular check-ins with mentor
- Gradually increase complexity
- Build expertise in area
- Help onboard next new member
```

## Meeting Guidelines

### Effective Meetings

**Before Meeting**:
- Clear agenda shared in advance
- Required attendees identified
- Pre-reads distributed
- Time limit set

**During Meeting**:
- Start and end on time
- Follow agenda
- Take notes
- Track action items

**After Meeting**:
- Share notes and action items
- Update relevant documentation
- Follow through on commitments

### Meeting Types

**Sprint Planning** (2 hours, bi-weekly)
- Review goals
- Estimate and assign work
- Identify risks

**Daily Standup** (15 minutes, daily)
- Share progress and plans
- Identify blockers
- Keep it brief

**Backlog Refinement** (1 hour, weekly)
- Clarify upcoming tickets
- Estimate complexity
- Prepare for sprint planning

**Retrospective** (1 hour, bi-weekly)
- Reflect on sprint
- Identify improvements
- Commit to changes

**Code Review** (30 minutes, as needed)
- Walk through complex PRs
- Discuss approach
- Resolve questions

## Emergency Collaboration

### Production Incident
```markdown
# 1. Identify and alert
Post in #intapi-assistant-alerts: "🚨 Production issue: [brief description]"

# 2. Assemble team
Ping on-call engineer and team lead

# 3. Create incident channel
#incident-2025-10-09-api-down

# 4. Assign roles
- Incident Commander: Coordinates response
- Investigators: Debug and fix
- Communicator: Updates stakeholders

# 5. Resolve and document
- Fix issue
- Verify resolution
- Create postmortem ticket
- Schedule postmortem meeting
```

### Urgent Hotfix
```markdown
# 1. Alert team
"🔥 Need urgent review on hotfix PR"

# 2. Fast-track review
- Reviewer prioritizes immediately
- Focus on correctness and safety
- Accept minor style issues

# 3. Deploy carefully
- Follow deployment workflow
- Monitor closely
- Be ready to rollback

# 4. Retrospect
- Document in postmortem
- Identify prevention measures
```

---

_Last updated: 2025-10-09_