# Getting Started with Memory Bank Template

Quick start guide for using this template to create a knowledge repository for Claude Code.

## What Is This?

This is a **template** for creating a structured knowledge repository that helps Claude Code work effectively on your project. It's based on the intapi-assistant memory-bank structure and designed to be customized for any project.

## Why Use This?

When properly configured, this memory bank enables Claude Code to:
- ✅ Understand your project structure instantly
- ✅ Follow your team's coding standards
- ✅ Execute workflows consistently
- ✅ Create properly formatted artifacts (tickets, PRs, commits)
- ✅ Invoke specialized sub-agents as quality gates
- ✅ Learn from past work (archived tickets)

## Quick Start (15 minutes)

### 1. Copy Template to Your Project
```bash
# Option A: Copy entire template
cp -r /path/to/this/template your-project/memory-bank/

# Option B: Start from scratch with this as reference
# (Keep this template as reference, build your own)
```

### 2. Create Minimal Configuration

**Create these 3 files to get started:**

#### A. CLAUDE.md (project root)
```bash
cp memory-bank/CLAUDE-template.md ../CLAUDE.md
# Edit and replace [placeholders]
```

#### B. memory-bank/03-component-architecture/project-structure.md
```markdown
# Project Structure

## Root Directory
- `src/` - Source code
- `tests/` - Tests
- `scripts/` - Automation

[Add your specific structure]
```

#### C. memory-bank/04-standards/coding-style-guide.md
```markdown
# Coding Standards

## Naming Conventions
[Your conventions]

## Code Organization
[Your patterns]

[Add your standards]
```

### 3. Configure .gitignore
```bash
# Add to your project's .gitignore
cat memory-bank/.gitignore-template >> .gitignore
```

### 4. Test with Claude
Ask Claude: "What is the project structure?"

If Claude references `memory-bank/03-component-architecture/project-structure.md`, it's working! ✅

## Full Customization (2-4 hours)

For complete customization, follow:
**`CUSTOMIZATION_GUIDE.md`** - Step-by-step instructions

## Template Structure

This template includes:

### Core Documentation (README files)
- `README.md` - Main overview
- `01-workflows/README.md` - Workflows catalog
- `02-templates/README.md` - Templates catalog
- `03-component-architecture/README.md` - Architecture docs
- `04-standards/README.md` - Coding standards
- `05-cache/README.md` - Cache management
- `06-context/README.md` - Context folder usage
- `07-scripts-documentation/README.md` - Scripts docs
- `08-agents/README.md` - Sub-agents guide
- `09-team-processes/README.md` - Team processes
- `ticket-administration/README.md` - Archive guide

### Example Files
- `01-workflows/example-workflow.md` - Workflow template
- `02-templates/example-template.md` - Template template
- `CLAUDE-template.md` - CLAUDE.md template

### Helper Files
- `.gitignore-template` - Gitignore configuration
- `CUSTOMIZATION_GUIDE.md` - Full customization guide
- `GETTING_STARTED.md` - This file

## File Tree

```
memory-bank/
├── README.md                                  ✅ Main overview
├── GETTING_STARTED.md                         ✅ This file
├── CUSTOMIZATION_GUIDE.md                     ✅ Step-by-step guide
├── CLAUDE-template.md                         ✅ CLAUDE.md template
├── .gitignore-template                        ✅ Gitignore config
│
├── 01-workflows/                              📂 Step-by-step procedures
│   ├── README.md                              ✅ Workflows catalog
│   └── example-workflow.md                    📋 Workflow template
│
├── 02-templates/                              📂 Artifact templates
│   ├── README.md                              ✅ Templates catalog
│   └── example-template.md                    📋 Template template
│
├── 03-component-architecture/                 📂 Architecture docs
│   └── README.md                              ✅ Architecture guide
│
├── 04-standards/                              📂 Coding standards
│   └── README.md                              ✅ Standards guide
│
├── 05-cache/                                  📂 Cached API data
│   └── README.md                              ✅ Cache guide
│
├── 06-context/                                📂 Active work workspace
│   ├── README.md                              ✅ Context guide
│   ├── LOCAL/                                 📁 Draft tickets (gitignored)
│   └── JIRA/                                  📁 Fetched tickets (gitignored)
│
├── 07-scripts-documentation/                  📂 Scripts docs
│   └── README.md                              ✅ Scripts guide
│
├── 08-agents/                                 📂 Sub-agents
│   └── README.md                              ✅ Agents guide
│
├── 09-team-processes/                         📂 Team processes
│   └── README.md                              ✅ Processes guide
│
└── ticket-administration/                     📂 Archived tickets
    ├── README.md                              ✅ Archive guide
    └── JIRA/                                  📁 Completed tickets

Legend:
✅ Documentation file (customize)
📋 Example/template file (reference)
📂 Folder (populate)
📁 Working folder (gitignored)
```

## Common Use Cases

### Use Case 1: Quick Setup for Small Project

**Time**: 30 minutes

1. Copy template
2. Create `CLAUDE.md` with basic commands
3. Document project structure
4. Add 1-2 coding standards
5. Start using with Claude

### Use Case 2: Full Setup for Team Project

**Time**: 4 hours

1. Copy template
2. Follow complete `CUSTOMIZATION_GUIDE.md`
3. Document all workflows
4. Create all templates
5. Setup sub-agents
6. Document team processes
7. Test thoroughly
8. Train team

### Use Case 3: Incremental Adoption

**Time**: Ongoing

1. Start with minimal setup (30 min)
2. Add documentation as needed
3. Document workflows when they solidify
4. Create templates as patterns emerge
5. Build knowledge over time

## What to Customize First

### Priority 1: Essential (Do First)
1. ✅ **CLAUDE.md** - Main instructions for Claude
2. ✅ **Project structure** - Architecture overview
3. ✅ **Coding standards** - At least 1 language style guide
4. ✅ **.gitignore** - Exclude cache and context folders

### Priority 2: Important (Do Soon)
5. ⚠️ **Key workflows** - Most common operations
6. ⚠️ **Templates** - Ticket and PR templates
7. ⚠️ **Scripts docs** - Document main scripts

### Priority 3: Nice-to-Have (Do Later)
8. ℹ️ **Sub-agents** - Quality gate automation
9. ℹ️ **Team processes** - Agile ceremonies
10. ℹ️ **Archive process** - Ticket administration

## Tips for Success

### Do
- ✅ Start small - minimal setup first
- ✅ Document what you actually do (not ideal)
- ✅ Test with Claude as you go
- ✅ Iterate based on real usage
- ✅ Keep it simple
- ✅ Update as project evolves

### Don't
- ❌ Try to document everything at once
- ❌ Create workflows you don't follow
- ❌ Over-engineer the structure
- ❌ Forget to test with Claude
- ❌ Let it get stale
- ❌ Make it too rigid

## Getting Help

### Resources
1. **This template's README files** - Each folder has detailed instructions
2. **Example files** - See `example-workflow.md` and `example-template.md`
3. **Customization guide** - Step-by-step in `CUSTOMIZATION_GUIDE.md`
4. **Original implementation** - intapi-assistant memory-bank (if you have access)

### Common Questions

**Q: Where do I start?**
A: Create `CLAUDE.md`, document project structure, add one coding standard. Test with Claude.

**Q: Do I need all folders?**
A: No. Start with 03-component-architecture and 04-standards. Add others as needed.

**Q: How do I know if it's working?**
A: Ask Claude about your project. It should reference memory-bank docs in responses.

**Q: Can I change the structure?**
A: Yes! But keep the core principle: single responsibility per folder/file.

**Q: How much detail is enough?**
A: Enough for Claude to understand and follow. Start minimal, add when needed.

**Q: What if my team doesn't use Jira?**
A: Rename `JIRA/` folders to your ticket system (Linear, GitHub, etc.)

## Next Steps

1. **If just browsing**: Read `README.md` to understand the structure
2. **If planning to use**: Read `CUSTOMIZATION_GUIDE.md` for full instructions
3. **If starting now**: Follow Quick Start above (15 minutes)
4. **If customizing fully**: Allocate 2-4 hours, follow customization guide

## Success Criteria

You'll know the memory bank is working when:
- ✅ Claude references memory-bank docs when answering questions
- ✅ Claude follows your workflows correctly
- ✅ Claude uses your templates automatically
- ✅ Claude suggests appropriate sub-agents
- ✅ Your team finds it helpful
- ✅ It stays updated as project evolves

## Support

This template is based on the intapi-assistant memory-bank structure. For questions about:
- **This template**: Review README files in each folder
- **Claude Code**: Check Claude Code documentation
- **Your project specifics**: Ask your team

---

**Remember**: This is a living system. Start simple, use it, improve it, and let it evolve with your project.

Good luck! 🚀