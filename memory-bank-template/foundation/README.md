# Foundation Documentation

## Purpose

The **foundation** folder contains the core, unchanging documentation that defines the fundamental aspects of your project. This is the bedrock of your memory bank—the essential knowledge that every team member and AI assistant must understand before working on the project.

Think of foundation documents as the **"constitution"** of your project: they change rarely, but when they do, it's significant.

## What Belongs in Foundation

Foundation documentation covers:

- **Project Structure**: How the codebase is organized
- **Technology Stack**: What technologies, frameworks, and tools are used
- **Architecture**: How components interact and depend on each other
- **Build System**: How the project is built, tested, and deployed
- **Product Context**: Why the project exists and what problems it solves
- **Project Brief**: The master document that shapes all other documentation
- **Technical Context**: Development environment, constraints, and dependencies

## Foundation Documents

### [01-project-overview.md](01-project-overview.md)
**Purpose**: High-level understanding of the project
**Contains**:
- Project purpose and goals
- Module structure and organization
- Key responsibilities of each module
- Entry points and main components

**When to update**:
- Adding new modules
- Restructuring the codebase
- Changing project scope

---

### [02-technology-stack.md](02-technology-stack.md)
**Purpose**: Complete inventory of technologies used
**Contains**:
- Programming languages and versions
- Frameworks and libraries
- Build tools and dependencies
- External services and integrations
- Development tools

**When to update**:
- Adding new dependencies
- Upgrading major versions
- Integrating new services
- Changing build tools

---

### [03-module-architecture.md](03-module-architecture.md)
**Purpose**: Detailed architectural documentation
**Contains**:
- Module dependencies and relationships
- Naming conventions and standards
- Package structure
- Design patterns used
- Component interactions

**When to update**:
- Architectural refactoring
- Adding new patterns
- Changing dependencies
- Major structural changes

---

### [04-build-configuration.md](04-build-configuration.md)
**Purpose**: Build, test, and deployment configuration
**Contains**:
- Build tool configuration
- Versioning strategy
- Environment setup
- CI/CD pipeline details
- Release processes

**When to update**:
- Changing build process
- Updating CI/CD
- New environment requirements
- Version strategy changes

---

### [05-product-context.md](05-product-context.md)
**Purpose**: Understanding the product and user needs
**Contains**:
- Why this project exists
- Problems it solves
- Target users and use cases
- User experience goals
- Success metrics

**When to update**:
- Pivoting product direction
- Adding major features
- Changing target audience
- Refining value proposition

---

### [06-project-brief.md](06-project-brief.md)
**Purpose**: Master document that shapes all other files
**Contains**:
- Project requirements and scope
- Goals and objectives
- Constraints and limitations
- Success criteria
- Story point estimation methodology

**When to update**:
- Major scope changes
- New requirements
- Changing objectives
- Process updates

**Note**: This is the **source of truth** for project scope and requirements.

---

### [07-tech-context.md](07-tech-context.md)
**Purpose**: Technical environment and setup details
**Contains**:
- Development environment setup
- Required tools and versions
- Technical constraints
- Infrastructure dependencies
- Configuration requirements

**When to update**:
- Environment changes
- New tool requirements
- Infrastructure updates
- Configuration changes

---

## How to Use Foundation Documents

### For New Team Members
**Start here first!** Read foundation documents in this order:
1. **[06-project-brief.md](06-project-brief.md)** - Understand what and why
2. **[05-product-context.md](05-product-context.md)** - Understand the user perspective
3. **[01-project-overview.md](01-project-overview.md)** - Understand the structure
4. **[02-technology-stack.md](02-technology-stack.md)** - Understand the technologies
5. **[07-tech-context.md](07-tech-context.md)** - Set up your environment
6. **[03-module-architecture.md](03-module-architecture.md)** - Deep dive into architecture
7. **[04-build-configuration.md](04-build-configuration.md)** - Learn build and deployment

### For AI Assistants
**Always load foundation documents at the start of every session:**
```markdown
1. Read memory-bank/README.md (the index)
2. Read memory-bank/foundation/README.md (this file - your guide)
3. Read ALL foundation documents in order listed above
4. Then proceed to context/ and other relevant sections
```

### For Developers
**Reference foundation documents when:**
- Starting a new feature or bug fix
- Making architectural decisions
- Adding new dependencies
- Setting up development environment
- Onboarding to the project
- Writing documentation

### For Documentation Maintainers
**Keep foundation current by:**
- Reviewing quarterly for accuracy
- Updating immediately when fundamentals change
- Ensuring consistency across all foundation docs
- Archiving obsolete information properly

## Foundation vs. Context

Understanding the difference:

### Foundation (This Folder)
- **Nature**: Stable, rarely changes
- **Content**: Project fundamentals
- **Examples**: Technology stack, architecture, build setup
- **Update frequency**: Quarterly or when major changes occur
- **Audience**: Everyone, all the time

### Context (`../context/`)
- **Nature**: Dynamic, frequently changes
- **Content**: Current work state
- **Examples**: Active work, recent changes, current progress
- **Update frequency**: Daily or weekly
- **Audience**: Active contributors

## Maintenance Guidelines

### When to Update Foundation

Foundation documents should be updated when:
- ✅ Adding or removing major modules
- ✅ Changing technology stack (languages, frameworks, tools)
- ✅ Architectural refactoring or pattern changes
- ✅ Build process modifications
- ✅ Major product direction changes
- ✅ Infrastructure or environment changes

Foundation should **NOT** be updated for:
- ❌ Day-to-day development progress
- ❌ Current ticket work
- ❌ Temporary decisions
- ❌ Bug fixes (unless they reveal architectural issues)
- ❌ Minor configuration tweaks

### Update Process

1. **Identify What Changed**
   - What foundation aspect changed?
   - Which documents need updating?

2. **Update Relevant Documents**
   - Make changes in appropriate foundation files
   - Update cross-references
   - Add "Last updated" date

3. **Review for Consistency**
   - Ensure all foundation docs align
   - Check cross-references work
   - Verify examples are current

4. **Communicate Changes**
   - Announce significant updates to team
   - Update dependent documentation
   - Consider creating ADR for major changes

### Quality Standards

Foundation documentation should be:
- ✅ **Accurate**: Reflects current reality
- ✅ **Complete**: Covers all fundamental aspects
- ✅ **Clear**: Easy to understand
- ✅ **Consistent**: Aligned across all docs
- ✅ **Maintained**: Regularly reviewed and updated
- ✅ **Accessible**: Easy to find and navigate

## Integration with Memory Bank

Foundation is part of the larger memory bank strategy:

```
memory-bank/
├── README.md                 # Index - start here
├── foundation/              # ← YOU ARE HERE
│   ├── README.md            # This guide
│   ├── 01-project-overview.md
│   ├── 02-technology-stack.md
│   ├── 03-module-architecture.md
│   ├── 04-build-configuration.md
│   ├── 05-product-context.md
│   ├── 06-project-brief.md
│   └── 07-tech-context.md
├── context/                 # Dynamic work state
├── workflows/               # How team works
├── agents/                  # Role definitions
├── ticket-administration/   # Ticket-driven work
└── prompts/                # AI assistant prompts
```

### Related Sections

- **[context/](../context/README.md)** - Current work state (read after foundation)
- **[workflows/](../workflows/README.md)** - Development processes
- **[agents/](../agents/README.md)** - Team role definitions
- **[ticket-administration/](../ticket-administration/README.md)** - Ticket management

## Success Criteria

### Foundation is Working Well When:
- ✅ New team members can onboard quickly
- ✅ Everyone has shared understanding of project
- ✅ Architectural decisions are documented
- ✅ Technology choices are clear and justified
- ✅ Documentation rarely contradicts reality
- ✅ AI assistants have correct context

### Warning Signs:
- ❌ New members confused about project structure
- ❌ Documentation doesn't match codebase
- ❌ Frequent questions about "why we do this"
- ❌ Multiple conflicting sources of truth
- ❌ Foundation docs haven't been updated in 6+ months
- ❌ Team members bypass documentation

## Quick Reference

### Starting a New Project?
1. Copy this foundation folder structure
2. Fill in each document with your project details
3. Replace `[PLACEHOLDERS]` with actual values
4. Review and validate with team
5. Link from main memory-bank README.md

### Inheriting an Existing Project?
1. Read foundation docs in order (see "For New Team Members" above)
2. Verify accuracy against actual codebase
3. Update any outdated information
4. Fill in any gaps you discover
5. Share findings with team

### Regular Maintenance?
- **Monthly**: Quick review for accuracy
- **Quarterly**: Comprehensive review and updates
- **Major Changes**: Update immediately

---

**Remember**: Foundation is your project's single source of truth. Keep it accurate, keep it current, and always start here.

_Last updated: 2025-10-10_