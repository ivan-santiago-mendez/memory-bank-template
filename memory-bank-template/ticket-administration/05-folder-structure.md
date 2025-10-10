# Ticket Folder Structure and Organization

This document defines the standard folder structure and organization conventions for ticket documentation in the intapi-assistant project.

## Overview

All ticket-related documentation is stored in the `memory-bank/ticket-administration/` directory, organized by ticket type and version. This structure ensures consistency, traceability, and easy navigation across all project work.

## Directory Structure

```
memory-bank/ticket-administration/
├── README.md                           # Overview and usage guidelines
├── 01-best-practices.md                # Best practices for ticket writing
├── 02-roles-and-permissions.md        # Roles and permissions
├── 03-ticket-templates.md             # Ticket templates
├── 04-workflows.md                     # Ticket workflows and lifecycle
├── 05-folder-structure.md             # This file - folder structure conventions
│
├── JIRA/                               # Official JIRA tickets
│   └── AIT-XXX/                        # Ticket number (e.g., AIT-636, AIT-654)
│       ├── README.md                   # Main ticket documentation (REQUIRED)
│       ├── V0/                         # Version 0 (first attempt/implementation)
│       │   ├── README.md               # Version-specific documentation
│       │   ├── [analysis].md           # Analysis documents
│       │   ├── [findings].md           # Discovery findings
│       │   ├── [plan].md               # Implementation plans
│       │   └── [notebook].ipynb        # Jupyter notebooks for testing
│       ├── V1/                         # Version 1 (second attempt/refactor)
│       │   ├── README.md               # Version-specific documentation
│       │   └── [documents].md          # Version-specific documents
│       └── V2/                         # Additional versions as needed
│           └── README.md
│
└── LOCAL/                              # Local development tickets (not in JIRA)
    └── AIT-XXXX/                       # Local ticket identifier (e.g., AIT-mise01)
        ├── README.md                   # Main documentation (REQUIRED)
        └── [documents].md              # Supporting documentation
```

## Folder Types

### JIRA Tickets (`JIRA/`)

**Purpose:** Official tickets tracked in Atlassian JIRA

**Naming Convention:** `JIRA/AIT-XXX/`
- Where `XXX` is the JIRA ticket number
- Examples: `AIT-636`, `AIT-654`, `AIT-640`

**When to Use:**
- Feature implementations
- Bug fixes
- Architecture decisions (ADRs)
- Official tasks assigned via JIRA

**Requirements:**
- Must have a valid JIRA ticket: https://taulia.atlassian.net/browse/AIT-XXX
- Must include README.md with ticket summary and links
- Should reference JIRA ticket in all commits

### LOCAL Tickets (`LOCAL/`)

**Purpose:** Local development work, experiments, or internal documentation not tracked in JIRA

**Naming Convention:** `LOCAL/AIT-XXXX/`
- Use descriptive identifier (e.g., `AIT-mise01`, `AIT-mise05`)
- Should still follow AIT- prefix for consistency

**When to Use:**
- Local development experiments
- Environment setup documentation
- Troubleshooting logs
- Internal investigations
- Prototype work before JIRA ticket creation

**Requirements:**
- Must include README.md explaining the work
- Should document outcomes and decisions
- Can be promoted to JIRA ticket if work becomes official

## Version Folders (VX)

### Purpose

Version folders track multiple implementation attempts, refactors, or pivots for the same ticket.

### Naming Convention

- `V0/` - First version/attempt (Version 0)
- `V1/` - Second version/refactor (Version 1)
- `V2/` - Third version if needed
- Continue sequentially as needed

### When to Use Version Folders

**Use version folders when:**
- ✅ Implementation approach changes significantly (architectural pivot)
- ✅ Major refactor requires different approach
- ✅ Previous attempt was rejected/blocked (e.g., PR rejected)
- ✅ Technology choice changes (e.g., different library version)
- ✅ Need to preserve history of multiple attempts

**Don't use version folders for:**
- ❌ Minor code changes or iterations
- ❌ Bug fixes within same implementation
- ❌ Documentation updates
- ❌ Small refactors

### Version Folder Examples

**Example 1: AIT-640 (Spring AI Upgrade)**
```
JIRA/AIT-640/
├── README.md          # Main ticket documentation
└── V0/                # First upgrade attempt (rejected)
    ├── README.md
    ├── breaking-changes-analysis.md
    ├── phase1-investigation-findings.md
    └── remediation-plan.md
```
- V0 attempted Spring AI 1.1.0-M2 upgrade
- PR was rejected due to Spring Boot incompatibility
- No V1 because ticket was closed (decided not to upgrade)

**Example 2: AIT-654 (MCP Implementation)**
```
JIRA/AIT-654/
├── README.md          # Main ticket documentation
└── V1/                # Current implementation version
    ├── README.md
    ├── phase1-setup.md
    ├── phase2-implementation.md
    └── AIT-654.ipynb
```
- V1 is the active implementation
- No V0 because this is the first implementation approach

**Example 3: AIT-636 (Architecture Decision)**
```
JIRA/AIT-636/
└── README.md          # ADR doesn't need version folders
```
- Architecture decisions typically don't have versions
- The README contains the full ADR and history

## Required Files

### README.md (REQUIRED in every ticket folder)

**Location:** `JIRA/AIT-XXX/README.md` or `LOCAL/AIT-XXXX/README.md`

**Required Sections:**
```markdown
# AIT-XXX: [Ticket Title]

## Ticket Information
- **Ticket ID**: AIT-XXX
- **Status**: [Current Status]
- **Date Created**: YYYY-MM-DD
- **Component**: [Component Name]
- **Related Tickets**: [List of related tickets]
- **JIRA URL**: https://taulia.atlassian.net/browse/AIT-XXX

## Summary
[Brief summary of the ticket]

## Objectives
[What needs to be accomplished]

## Status History
| Date | Status | Notes |
|------|--------|-------|
| YYYY-MM-DD | Created | Initial ticket creation |
| YYYY-MM-DD | In Progress | Started implementation |
| YYYY-MM-DD | Complete | Work finished |
```

### Version README.md (if using version folders)

**Location:** `JIRA/AIT-XXX/VX/README.md`

**Required Sections:**
```markdown
# AIT-XXX Version X Implementation

## Version Information
- **Version**: VX
- **Status**: [Active/Abandoned/Complete]
- **Branch**: [Git branch name]
- **Date Started**: YYYY-MM-DD

## Version Summary
[Why this version exists, what changed from previous version]

## Implementation Details
[Specific details for this version]

## Outcome
[Results, decision, next steps]
```

## Supporting Documents

### Common Document Types

**Analysis Documents:**
- `discovery-findings.md` - Research and discovery results
- `breaking-changes-analysis.md` - Analysis of breaking changes
- `phase1-investigation-findings.md` - Investigation results

**Planning Documents:**
- `implementation-plan.md` - Implementation approach
- `remediation-plan.md` - Plan to fix issues
- `security-integration-proposal.md` - Security proposals

**Testing Documents:**
- `test-results.md` - Test execution results
- `validation-sources.md` - Validation and verification
- `[ticket].ipynb` - Jupyter notebooks for manual testing

**Decision Documents:**
- `team-review.md` - Team decision documentation
- `architecture-decision.md` - Architectural choices

### Naming Conventions for Documents

**Use kebab-case:** `my-document-name.md`
- ✅ `phase1-investigation-findings.md`
- ✅ `breaking-changes-analysis.md`
- ✅ `security-integration-proposal.md`
- ❌ `Phase1InvestigationFindings.md` (avoid PascalCase)
- ❌ `phase_1_investigation.md` (avoid snake_case)

**Be descriptive:**
- ✅ `spring-ai-upgrade-breaking-changes.md`
- ❌ `changes.md`

**Include phase/version if relevant:**
- ✅ `phase1-setup.md`, `phase2-implementation.md`
- ✅ `v0-attempt-summary.md`

## Real-World Examples

### Example 1: Simple Feature Implementation (No Versions)

```
JIRA/AIT-593/
├── README.md                    # Main ticket documentation
└── V0/
    ├── README.md
    ├── TicketPlan.md
    └── HandshakeTestInstructions.md
```

**When:** Single implementation approach, no pivots

### Example 2: Complex Implementation with Versions

```
JIRA/AIT-654/
├── README.md                    # Main ticket overview
└── V1/                          # Current implementation
    ├── README.md                # V1-specific documentation
    ├── phase1-setup.md
    ├── phase2-implementation.md
    ├── phase3-testing.md
    ├── phase4-quality.md
    └── AIT-654.ipynb            # Manual testing notebook
```

**When:** Active development with multiple phases

### Example 3: Architecture Decision Record

```
JIRA/AIT-636/
├── README.md                    # Complete ADR
└── V0/
    └── MCP doc.pdf              # Original design document
```

**When:** Architecture decisions with supporting documents

### Example 4: Failed Implementation Attempt

```
JIRA/AIT-640/
├── README.md                    # Main ticket (closed)
└── V0/                          # Failed attempt
    ├── README.md
    ├── breaking-changes-analysis.md
    ├── phase1-investigation-findings.md
    ├── remediation-plan.md
    └── validation-sources.md
```

**When:** Implementation attempted but blocked/rejected

### Example 5: Local Development Work

```
LOCAL/AIT-mise05/
└── README.md                    # Setup documentation
```

**When:** Local troubleshooting, environment setup

## Workflow: Creating a New Ticket Folder

### For JIRA Tickets

1. **Create JIRA ticket** in Atlassian
2. **Create folder structure:**
   ```bash
   mkdir -p memory-bank/ticket-administration/JIRA/AIT-XXX
   touch memory-bank/ticket-administration/JIRA/AIT-XXX/README.md
   ```

3. **Populate README.md** with required sections

4. **Add version folder** if needed:
   ```bash
   mkdir -p memory-bank/ticket-administration/JIRA/AIT-XXX/V0
   touch memory-bank/ticket-administration/JIRA/AIT-XXX/V0/README.md
   ```

5. **Update memory bank index** if needed

### For LOCAL Tickets

1. **Choose descriptive identifier:**
   - Use `AIT-` prefix for consistency
   - Add descriptive suffix (e.g., `AIT-mise01`, `AIT-docker-fix`)

2. **Create folder structure:**
   ```bash
   mkdir -p memory-bank/ticket-administration/LOCAL/AIT-XXXX
   touch memory-bank/ticket-administration/LOCAL/AIT-XXXX/README.md
   ```

3. **Populate README.md** explaining the work

4. **Document outcomes** and decisions

## Best Practices

### DO ✅

- **Always create README.md** in ticket folders
- **Use version folders** for significant pivots or refactors
- **Document decisions** in README or dedicated docs
- **Link related tickets** in README
- **Update status history** as work progresses
- **Use descriptive file names** for supporting documents
- **Keep JIRA and LOCAL separate** - don't mix
- **Reference JIRA URL** in all JIRA ticket READMEs

### DON'T ❌

- **Don't skip README.md** - it's required
- **Don't create version folders** for minor iterations
- **Don't use vague names** like `notes.md` or `temp.md`
- **Don't duplicate information** across multiple files
- **Don't mix JIRA and LOCAL** tickets in same folder
- **Don't create LOCAL tickets** for official work (use JIRA)
- **Don't forget to update** main ticket README when adding versions

## Maintenance

### When to Update This Document

- New folder structure patterns emerge
- Team adopts new conventions
- Structure requirements change
- Examples need updating

### Related Documentation

- [Ticket Administration README](README.md) - Overview
- [Best Practices](01-best-practices.md) - Ticket writing guidelines
- [Workflows](04-workflows.md) - Ticket lifecycle
- [CLAUDE.md](../../CLAUDE.md) - Project instructions

## Summary

The ticket folder structure provides:
- **Consistency** - All tickets follow same pattern
- **Traceability** - Easy to track work history
- **Organization** - Clear separation of official vs local work
- **Versioning** - Support for multiple implementation attempts
- **Documentation** - Comprehensive record of decisions and work

Always follow this structure to maintain project organization and enable efficient collaboration.

---

_Last updated: 2025-10-10_