# Context Documentation

## Purpose

The **context** folder contains the living, breathing documentation of your project's current state. Unlike the stable foundation documents, context files change frequently—sometimes daily—to reflect what's happening right now in your project.

Think of context as the **"pulse"** of your project: it tells you where you are, what you're working on, and where you're going next.

## What Belongs in Context

Context documentation captures:

- **Current Work**: What's being actively developed right now
- **Recent Changes**: What was recently completed or modified
- **Active Decisions**: Decisions being made or recently finalized
- **Progress Status**: What works, what doesn't, what's left to build
- **System Patterns**: Architectural patterns and design decisions that have emerged
- **Known Issues**: Current bugs, technical debt, and blockers

## Context vs. Foundation

Understanding the difference is critical:

| Aspect | Foundation | Context |
|--------|-----------|---------|
| **Nature** | Stable, rarely changes | Dynamic, frequently changes |
| **Content** | Project fundamentals | Current work state |
| **Examples** | Tech stack, architecture | Active tickets, recent changes |
| **Update Frequency** | Quarterly or on major changes | Daily to weekly |
| **Audience** | Everyone, always | Active contributors |
| **Purpose** | Understanding "what we built" | Understanding "what we're building" |

**Rule of thumb**: If it changes every sprint, it belongs in **context**. If it changes every quarter, it belongs in **foundation**.

## Context Documents

### [01-active-context.md](01-active-context.md)
**Purpose**: Snapshot of current work and immediate focus
**Contains**:
- What we're working on RIGHT NOW
- Recent changes (last 2-4 weeks)
- Next immediate steps
- Active decisions being made
- Current blockers or challenges
- Team focus areas

**Update frequency**: Daily to weekly
**Who updates**: Developers, AI assistants, team leads
**When to update**:
- Starting new tickets
- Completing major work
- Making important decisions
- Encountering blockers
- Shifting team focus

**Why it matters**: This is the first place anyone should look to understand "what's happening now." It prevents duplicate work and keeps everyone aligned.

---

### [02-progress.md](02-progress.md)
**Purpose**: Track what works, what doesn't, and what's left to build
**Contains**:
- ✅ What's completed and working
- 🚧 What's in progress
- ⏳ What's planned but not started
- ❌ Known issues and bugs
- 📝 Technical debt
- 🎯 Upcoming milestones

**Update frequency**: Weekly or after major milestones
**Who updates**: Developers, QA, team leads
**When to update**:
- Completing features or tickets
- Identifying new bugs or issues
- Planning sprints
- Reaching milestones
- Discovering technical debt

**Why it matters**: Provides a clear picture of project health and helps with planning. Essential for status updates and roadmap discussions.

---

### [03-system-patterns.md](03-system-patterns.md)
**Purpose**: Document architectural patterns and design decisions as they emerge
**Contains**:
- Design patterns being used
- Architectural decisions and rationale
- Code organization patterns
- Integration patterns
- Best practices that have emerged
- Anti-patterns to avoid
- Cross-cutting concerns

**Update frequency**: When architectural patterns are established or changed
**Who updates**: Architects, senior developers, AI assistants
**When to update**:
- Introducing new patterns
- Refactoring existing patterns
- Making architectural decisions
- Discovering what works well
- Identifying what doesn't work

**Why it matters**: Captures the "why" behind architectural decisions. Helps maintain consistency as the project grows and helps new team members understand design choices.

---

## How to Use Context Documents

### For New Team Members
**Read context AFTER foundation:**
1. First, read all foundation documents (see [../foundation/README.md](../foundation/README.md))
2. Then come here to understand current state
3. Read in this order:
   - **[01-active-context.md](01-active-context.md)** - What's happening now
   - **[02-progress.md](02-progress.md)** - Where we are
   - **[03-system-patterns.md](03-system-patterns.md)** - How we build

### For AI Assistants
**Always load context at the start of each session:**
```markdown
1. Load memory-bank/README.md (index)
2. Load memory-bank/foundation/README.md + all foundation docs
3. Load memory-bank/context/README.md (this file)
4. Load ALL context documents (01-03)
5. Then proceed with ticket-specific work
```

**Update context as you work:**
- Starting work on a ticket? Update `01-active-context.md`
- Completed a feature? Update `02-progress.md`
- Made an architectural decision? Update `03-system-patterns.md`

### For Developers
**Reference context when:**
- Starting your work day (check active context)
- Beginning a new ticket (understand current focus)
- Making architectural decisions (check existing patterns)
- Running into blockers (see if others hit the same issue)
- Finishing work (update progress and active context)

### For Team Leads
**Use context for:**
- Daily standups (active context)
- Sprint planning (progress status)
- Architecture reviews (system patterns)
- Status updates to stakeholders (progress)
- Identifying blockers and bottlenecks (active context)

## Update Workflow

### Daily Updates (01-active-context.md)

```markdown
# Morning (Start of day):
1. Review active context
2. Update your current focus
3. Note any blockers

# During work:
1. Update when starting new major tasks
2. Document important decisions
3. Note any discoveries or challenges

# End of day:
1. Update what you completed
2. Update what you're working on next
3. Document any blockers for tomorrow
```

### Weekly Updates (02-progress.md)

```markdown
# End of week or sprint:
1. Move completed items from "In Progress" to "Completed"
2. Add new items starting next sprint
3. Update known issues list
4. Review and update milestones
5. Document any new technical debt
```

### As-Needed Updates (03-system-patterns.md)

```markdown
# When making architectural decisions:
1. Document the pattern being introduced
2. Explain why this approach was chosen
3. Note any alternatives considered
4. Add examples or references
5. Document any trade-offs
```

## Context Quality Standards

### Good Context Documentation:
- ✅ **Current**: Reflects reality right now (not last month)
- ✅ **Specific**: Uses concrete examples, dates, ticket numbers
- ✅ **Actionable**: Helps people make decisions
- ✅ **Concise**: Gets to the point quickly
- ✅ **Honest**: Documents both successes and struggles
- ✅ **Linked**: References tickets, PRs, and other docs

### Poor Context Documentation:
- ❌ **Stale**: Outdated information that misleads
- ❌ **Vague**: "Working on some features"
- ❌ **Academic**: Just lists facts without context
- ❌ **Verbose**: Long paragraphs that bury the key info
- ❌ **Optimistic**: Hides problems or blockers
- ❌ **Orphaned**: No links to related work

## Common Scenarios

### Scenario: Starting Your Work Day

```markdown
1. Open 01-active-context.md
2. Check "Current Focus" - is this still accurate?
3. Check "Active Work" - what are others doing?
4. Check "Blockers" - anything affecting you?
5. Update your current focus if changed
```

### Scenario: Completing a Major Feature

```markdown
1. Update 01-active-context.md:
   - Move feature from "Active Work" to "Recent Changes"
   - Update "Current Focus" if shifting

2. Update 02-progress.md:
   - Move from "In Progress" to "Completed"
   - Note any new issues discovered

3. Consider 03-system-patterns.md:
   - Did you establish any new patterns?
   - Any architectural decisions worth documenting?
```

### Scenario: Encountering a Blocker

```markdown
1. Document in 01-active-context.md:
   - Add to "Blockers" section
   - Include ticket number, description, who's affected
   - Note any workarounds

2. Communicate to team:
   - Post in team chat
   - Update ticket comments
   - Mention in standup

3. Track resolution:
   - Update blocker status as it's addressed
   - Document solution when resolved
   - Move to "Recent Changes" when complete
```

### Scenario: Making an Architectural Decision

```markdown
1. Document in 03-system-patterns.md:
   - Pattern name and description
   - Why this approach
   - Alternatives considered
   - Trade-offs and implications

2. Update 01-active-context.md:
   - Add to "Active Decisions"
   - Link to detailed documentation

3. Consider creating ADR:
   - For major decisions, create Architecture Decision Record
   - Store in ticket-administration/JIRA/AIT-ADR/
```

## Integration with Memory Bank

Context fits into the larger memory bank structure:

```
memory-bank/
├── README.md                  # Index - start here
├── foundation/                # Stable fundamentals (read first)
│   ├── README.md
│   └── 01-07 foundation docs
├── context/                   # ← YOU ARE HERE
│   ├── README.md             # This guide
│   ├── 01-active-context.md  # What's happening now
│   ├── 02-progress.md        # Where we are
│   └── 03-system-patterns.md # How we build
├── workflows/                 # How team works
├── agents/                    # Role definitions
├── ticket-administration/     # Ticket-driven work
└── prompts/                  # AI assistant prompts
```

### Information Flow

```
Foundation → Context → Tickets
  (What)      (How)     (Details)

Foundation: "We use Spring Boot and Groovy"
Context: "Currently refactoring chat service to use Spring AI"
Ticket: "AIT-645: Implement Spring AI Advisors API"
```

## Maintenance Guidelines

### Keep Context Fresh

**Weekly Review**:
```markdown
- [ ] Review 01-active-context.md for accuracy
- [ ] Update 02-progress.md with completed work
- [ ] Archive old entries (move to ticket documentation)
- [ ] Verify all links still work
- [ ] Remove resolved blockers
```

**Monthly Cleanup**:
```markdown
- [ ] Move old "Recent Changes" to ticket history
- [ ] Archive completed milestones in progress.md
- [ ] Review system-patterns.md for outdated patterns
- [ ] Update "Last updated" dates
- [ ] Verify context aligns with foundation
```

### When Context Becomes Foundation

Sometimes context information stabilizes and should move to foundation:

**Move to foundation when**:
- Pattern is used consistently across codebase
- Decision won't change for foreseeable future
- Information is needed by all future contributors

**Example**: A pattern documented in `03-system-patterns.md` that's now standard across all modules should move to `foundation/03-module-architecture.md`.

## Anti-Patterns to Avoid

### ❌ DON'T: Let context go stale
```markdown
# 01-active-context.md (BAD - dated 3 months ago)
Current Focus:
- Working on user authentication (AIT-123)

# This is useless if it's outdated!
```

### ✅ DO: Keep context current
```markdown
# 01-active-context.md (GOOD - dated this week)
Current Focus:
- Refactoring chat service to Spring AI (AIT-645) - 80% complete
- Integrating MCP client for analytics (AIT-654) - starting

Last updated: 2025-10-10
```

### ❌ DON'T: Duplicate foundation info
```markdown
# 03-system-patterns.md (BAD - duplicates foundation)
## Technology Stack
We use Spring Boot 3.2, Groovy 4.0, MySQL 8.0...

# This belongs in foundation/02-technology-stack.md!
```

### ✅ DO: Document emerging patterns
```markdown
# 03-system-patterns.md (GOOD - new pattern)
## Chat Service Pattern
When implementing chat endpoints, we follow this pattern:
1. Use MessageChatMemoryAdvisor for conversation history
2. Store conversationId in request parameters
3. Return ChatResponse with structured messages

Rationale: Provides consistent conversation context across sessions.
Introduced in: AIT-645 (2025-10-08)
```

### ❌ DON'T: Be vague about progress
```markdown
# 02-progress.md (BAD - not actionable)
## In Progress
- Some chat stuff
- Working on integrations
```

### ✅ DO: Be specific and linked
```markdown
# 02-progress.md (GOOD - specific and actionable)
## In Progress
- AIT-645: Spring AI Advisors API (90% - PR in review)
- AIT-654: MCP Client Integration (40% - architecture defined)
- AIT-660: Bug fix for conversation memory (20% - investigating)
```

## Success Criteria

### Context is Working Well When:
- ✅ Team members know what others are working on
- ✅ No duplicate work happens
- ✅ Blockers are visible and addressed quickly
- ✅ Architectural decisions are documented as they're made
- ✅ New team members can get up to speed quickly
- ✅ Status updates to stakeholders are easy to generate
- ✅ Context is updated daily/weekly without prompting

### Warning Signs:
- ❌ "I didn't know you were working on that!"
- ❌ Context docs are weeks or months old
- ❌ Duplicate work across team members
- ❌ Hidden blockers that surprise the team
- ❌ New members can't understand current state
- ❌ Status updates require digging through tickets
- ❌ No one updates context (it's seen as extra work)

## Quick Reference

### What Goes Where?

| Information Type | Goes In |
|-----------------|---------|
| What ticket I'm working on today | 01-active-context.md |
| Decision I made this week | 01-active-context.md |
| Feature completed last sprint | 02-progress.md |
| Known bug discovered | 02-progress.md |
| New architectural pattern | 03-system-patterns.md |
| Technology choice (established) | foundation/02-technology-stack.md |
| Module structure (stable) | foundation/03-module-architecture.md |

### Update Frequency

| Document | Frequency | Who Updates |
|----------|-----------|-------------|
| 01-active-context.md | Daily | Everyone actively working |
| 02-progress.md | Weekly | Developers, QA, Leads |
| 03-system-patterns.md | As needed | Architects, Senior Devs |

---

**Remember**: Context is about **NOW**. If it's not current, it's not useful. Keep it fresh, keep it honest, keep it updated.

_Last updated: 2025-10-10_
