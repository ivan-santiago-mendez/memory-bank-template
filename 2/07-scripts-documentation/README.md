# Scripts Documentation

Documentation for shell scripts, automation tools, and task runners used in the project.

## Purpose

This folder documents all scripts used in the project, helping Claude Code:
- Understand what each script does
- Know when to run which script
- Troubleshoot script failures
- Suggest appropriate scripts for tasks

## Recommended Structure

### Main Documentation
- **scripts-overview.md** - High-level overview of all scripts
- **task-runner.md** - Documentation for main task runner (Makefile, run.sh, npm scripts, etc.)
- **setup-scripts.md** - Project initialization and setup scripts
- **deployment-scripts.md** - Deployment and release scripts
- **maintenance-scripts.md** - Cleanup, backup, and maintenance utilities

### Script-Specific Docs
- **[script-name].md** - Detailed documentation for individual scripts

## Script Documentation Template

```markdown
# [Script Name]

## Location
`path/to/script.sh`

## Purpose
[One-sentence description of what this script does]

## When to Use
[Situations where this script should be run]

## Prerequisites
- [ ] Prerequisite 1
- [ ] Prerequisite 2

## Usage

### Basic Usage
```bash
./path/to/script.sh [args]
```

### Options
- `--option1` - [Description]
- `--option2` - [Description]

### Examples
```bash
# Example 1: [Description]
./script.sh --option1

# Example 2: [Description]
./script.sh --option2 value
```

## What It Does

### Step 1: [Action]
[Description]

### Step 2: [Action]
[Description]

## Output
[What output to expect]

## Exit Codes
- `0` - Success
- `1` - [Error type]
- `2` - [Error type]

## Dependencies
- Dependency 1
- Dependency 2

## Environment Variables
- `VAR_NAME` - [Description]

## Troubleshooting

### Error: [Error message]
**Cause**: [Why this happens]
**Solution**: [How to fix]

### Error: [Error message]
**Cause**: [Why this happens]
**Solution**: [How to fix]

## Related Scripts
- [script-1.sh] - [Relationship]
- [script-2.sh] - [Relationship]

## Maintenance Notes
[Special considerations for maintaining this script]
```

## Task Runner Documentation

If using a task runner (Makefile, run.sh, package.json scripts), document:

### Task Runner Commands
```markdown
# Task Runner: [Name]

## Available Commands

### Development
| Command | Description |
|---------|-------------|
| `./run.sh dev` | Start development server |
| `./run.sh build` | Build project |
| `./run.sh test` | Run tests |

### Database
| Command | Description |
|---------|-------------|
| `./run.sh db:migrate` | Run migrations |
| `./run.sh db:seed` | Seed database |
| `./run.sh db:reset` | Reset database |

### Docker
| Command | Description |
|---------|-------------|
| `./run.sh docker:up` | Start Docker containers |
| `./run.sh docker:down` | Stop Docker containers |
| `./run.sh docker:logs` | View container logs |

### Utilities
| Command | Description |
|---------|-------------|
| `./run.sh init` | Initialize project |
| `./run.sh clean` | Clean build artifacts |
| `./run.sh format` | Format code |
```

## Customization Guide

### Step 1: List All Scripts
Create an inventory:
```bash
find scripts/ -type f -name "*.sh" -o -name "*.py" | sort
```

### Step 2: Document Task Runner
If you have a task runner (Makefile, run.sh, etc.):
1. Create `task-runner.md`
2. List all commands
3. Group by category
4. Explain common workflows

### Step 3: Document Critical Scripts
For each critical script:
1. Create `[script-name].md`
2. Follow template above
3. Include examples
4. Add troubleshooting section

### Step 4: Document Script Dependencies
Explain:
- What tools must be installed
- What environment variables are needed
- What configuration files are required
- What other scripts must run first

### Step 5: Create Quick Reference
Create `quick-reference.md` with common commands:
```markdown
# Quick Reference

## First Time Setup
1. `./run.sh init`
2. `./run.sh install-deps`
3. `./run.sh db:setup`

## Daily Development
- Start: `./run.sh dev`
- Test: `./run.sh test`
- Build: `./run.sh build`

## Troubleshooting
- Reset database: `./run.sh db:reset`
- Clean build: `./run.sh clean && ./run.sh build`
- View logs: `./run.sh logs`
```

## Usage Notes

- Keep documentation in sync with scripts
- Update docs when adding new scripts or options
- Include real examples, not just syntax
- Document failure modes and recovery steps
- Link to related workflows in `01-workflows/`

## Integration with Other Folders

- **Workflows (01)**: Reference scripts in workflow steps
- **Architecture (03)**: Explain how scripts fit in architecture
- **Standards (04)**: Document scripting standards

## Common Script Types

### Setup Scripts
- Environment initialization
- Dependency installation
- Database setup
- Configuration generation

### Build Scripts
- Compilation
- Bundling
- Asset processing
- Artifact generation

### Test Scripts
- Unit tests
- Integration tests
- E2E tests
- Coverage reports

### Deployment Scripts
- Release preparation
- Deployment automation
- Rollback procedures
- Health checks

### Maintenance Scripts
- Database backups
- Log rotation
- Cache clearing
- Cleanup tasks

## Troubleshooting

### Script not found
**Check**:
- Script location correct?
- Execute permissions set? (`chmod +x script.sh`)
- Script in PATH?

### Permission denied
**Solution**:
```bash
chmod +x path/to/script.sh
```

### Missing dependencies
**Solution**: Document all dependencies in script documentation

### Environment variable not set
**Solution**: Document required environment variables

## Security Notes

- **Never commit secrets** to scripts
- **Use environment variables** for sensitive data
- **Document required secrets** without exposing values
- **Use .env files** for local development
- **Validate inputs** in scripts

---

**Customize this folder** by documenting all scripts and automation tools used in your project.