# Context - Active Work Workspace

Working directory for active development work. Contents are **gitignored** (except documentation files).

## Overview

The `06-context/` folder is a **personal workspace** for:
- Drafting ticket requirements before ticket system creation
- Fetching and working with tickets
- Creating implementation versions (V0, V1, V2)
- Storing analysis, findings, and work documents

**Key Differences**:
- **06-context/**: Gitignored, personal workspace, active work
- **ticket-administration/**: Committed, team-shared, archived work

## Directory Structure

```
memory-bank/06-context/
├── README.md                           # This file - overview (COMMITTED)
├── folder-structure.md                 # Structure conventions (COMMITTED)
├── best-practices.md                   # Best practices (COMMITTED)
├── workflows.md                        # Context-specific workflows (COMMITTED)
│
├── LOCAL/                              # Local draft tickets (GITIGNORED)
│   ├── local1/                         # First draft
│   │   └── requirements.md             # Draft requirements
│   ├── local2/                         # Second draft
│   │   └── requirements.md
│   └── local3/                         # Third draft
│       └── requirements.md
│
└── JIRA/                               # Fetched tickets (GITIGNORED)
    ├── [project]-123/                  # Ticket number (lowercase)
    │   ├── README.md                   # Main ticket documentation
    │   ├── V0/                         # Version 0 (first implementation)
    │   │   ├── README.md               # Version-specific docs
    │   │   ├── analysis.md             # Analysis documents
    │   │   └── findings.md             # Discovery findings
    │   ├── V1/                         # Version 1 (refactor/pivot)
    │   │   ├── README.md
    │   │   └── updated-approach.md
    │   └── V2/                         # Version 2 (if needed)
    │       └── README.md
    │
    └── [project]-456/                  # Another ticket
        ├── README.md
        └── V0/
            └── README.md
```

**Note**: Replace `JIRA` with your ticket system name (Linear, GitHub Issues, etc.)

## Folder Types

### LOCAL/ - Draft Tickets

**Purpose**: Draft ticket requirements before creating ticket

**Naming**: `localN/` where N increments (local1, local2, local3...)

**When to Use**:
- User provides requirements for new ticket
- Requirements need validation/refinement
- Before ticket creation

**Lifecycle**:
1. Create: `LOCAL/local1/requirements.md` (DRAFT)
2. Iterate: Add missing sections
3. Validate: Check all required sections complete
4. Create Ticket: Returns ticket key (e.g., PROJ-789)
5. Fetch to JIRA: Move work to `JIRA/[project]-789/`
6. Delete: After work complete

### [TICKET_SYSTEM]/ - Fetched Tickets

**Purpose**: Working copies of tickets with implementation versions

**Naming**: `[project]-{number}/` (lowercase, e.g., proj-123, ait-456)

**When to Use**:
- User says: "Implement PROJ-123"
- Starting work on existing ticket

**Lifecycle**:
1. Fetch: Get ticket details from ticket system
2. Create: `JIRA/[project]-123/README.md` + `V0/`
3. Work: Add analysis, findings, documents
4. Version: Create V1, V2 if approach changes
5. Complete: Archive to `ticket-administration/JIRA/[PROJECT]-123/`
6. Delete: Remove from context after archiving

## Version Folders (V0, V1, V2)

### Purpose
Track multiple implementation attempts, refactors, or approach changes for the same ticket.

### Naming
- `V0/` - First version/attempt
- `V1/` - Second version/refactor
- `V2/` - Third version
- Continue sequentially as needed

### When to Create New Version

**Create new version when**:
- ✅ Implementation approach changes significantly
- ✅ Major refactor with different architecture
- ✅ Previous attempt blocked/rejected (e.g., PR rejected)
- ✅ Technology choice changes

**Don't create new version for**:
- ❌ Minor code changes
- ❌ Bug fixes within same approach
- ❌ Documentation updates
- ❌ Small refactors

## Required Files

### LOCAL/localN/requirements.md
Draft ticket requirements following your team's template.

**Template**: `memory-bank/02-templates/local-draft-template.md`

### [TICKET_SYSTEM]/[ticket-id]/README.md
Main ticket documentation (REQUIRED in every ticket folder).

**Template**: `memory-bank/02-templates/ticket-context-readme-template.md`

### [TICKET_SYSTEM]/[ticket-id]/VX/README.md
Version-specific documentation (REQUIRED in each version folder).

**Template**: `memory-bank/02-templates/version-readme-template.md`

## Gitignore Policy

Add to `.gitignore`:
```
# Context folder - working directories only (keep documentation)
memory-bank/06-context/LOCAL/
memory-bank/06-context/JIRA/
memory-bank/06-context/[YOUR_TICKET_SYSTEM]/

# Keep documentation files
!memory-bank/06-context/*.md
```

**Why**:
- Personal workspace during active development
- Work-in-progress documents
- May contain sensitive investigation notes
- Avoids merge conflicts between developers

## Typical Workflows

### Workflow 1: Create New Ticket
```
1. User: "Create ticket for [feature]"
2. Create: LOCAL/local1/requirements.md (DRAFT)
3. Iterate: Add sections, validate
4. Complete: All required sections validated
5. Create Ticket: Returns PROJ-789
6. Fetch: Create JIRA/proj-789/README.md + V0/
7. Work: Add documents to V0/
8. Complete: Move to ticket-administration/JIRA/PROJ-789/
9. Delete: LOCAL/local1/ and JIRA/proj-789/
```

### Workflow 2: Work on Existing Ticket
```
1. User: "Implement PROJ-123"
2. Fetch: Get ticket from ticket system
3. Create: JIRA/proj-123/README.md + V0/
4. Add: analysis.md, findings.md, plan.md
5. (Optional) Refactor: Create V1/ with new approach
6. Complete: PR merged
7. Archive: Move to ticket-administration/JIRA/PROJ-123/
8. Commit: For team visibility
9. Delete: JIRA/proj-123/ from context
```

### Workflow 3: Archive to ticket-administration
```
1. Work complete in: 06-context/JIRA/proj-123/
2. Verify: All documents finalized
3. Move: cp -r 06-context/JIRA/proj-123/ ticket-administration/JIRA/PROJ-123/
4. Case fix: Rename proj-123 → PROJ-123 (uppercase in ticket-administration)
5. Commit: git add, git commit
6. Delete: rm -rf 06-context/JIRA/proj-123/
7. Clean: Remove from context
```

## Naming Conventions

### Folder Names
- **LOCAL folders**: `local1`, `local2`, `local3`
- **Ticket folders (context)**: lowercase `proj-123`, `ait-456`
- **Ticket folders (archive)**: uppercase `PROJ-123`, `AIT-456`
- **Version folders**: `V0`, `V1`, `V2`

### File Names
Use kebab-case:
- ✅ `breaking-changes-analysis.md`
- ✅ `phase1-investigation.md`
- ❌ `BreakingChanges.md`

## Maintenance & Cleanup

### When to Clean Up
- **LOCAL drafts**: After ticket created or after 7 days of inactivity
- **Ticket working copies**: After complete and archived, or after 30 days

### Cleanup Commands
```bash
# Remove LOCAL drafts older than 7 days
find memory-bank/06-context/LOCAL -type d -mtime +7 -exec rm -rf {} +

# Remove ticket working copies older than 30 days
find memory-bank/06-context/JIRA -type d -maxdepth 1 -mtime +30 -exec rm -rf {} +

# Clean up after archiving specific ticket
rm -rf memory-bank/06-context/JIRA/proj-123/
```

## Integration with ticket-administration/

Work always flows from context → ticket-administration:

```
06-context/JIRA/proj-123/
    ↓ (work complete)
ticket-administration/JIRA/PROJ-123/
    ↓ (git commit)
Team visibility
```

## Customization Guide

1. **Rename JIRA folder** to match your ticket system (Linear, GitHub, etc.)
2. **Update templates** in `02-templates/` to match your ticket format
3. **Configure .gitignore** to exclude working folders
4. **Create workflow docs** specific to your ticket system
5. **Document version policy** for your team

## Related Documentation

- **Workflows**: See `workflows.md` for detailed procedures
- **Templates**: See `memory-bank/02-templates/` for file templates
- **Archive**: See `memory-bank/ticket-administration/` for completed work

---

**Customize this folder** by adapting the structure to your ticket system and team workflow.