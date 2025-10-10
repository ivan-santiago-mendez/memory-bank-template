# Automation Agent

Responsibilities for CI/CD, automation tooling, and infrastructure on the intapi-assistant project.

## Core Responsibilities

- [ ] Maintain CI/CD pipelines
- [ ] Manage mise task definitions
- [ ] Monitor automation health
- [ ] Improve build and test automation
- [ ] Maintain Docker configuration
- [ ] Manage deployment automation
- [ ] Document automation changes

## Mise Task Management

### Adding New Tasks
```toml
# In .mise.toml

[tasks.new_task]
description = "Clear description of what this does"
run = "command to execute"

# Example:
[tasks.integration_test]
description = "Run integration tests only"
run = "gradle test --tests '*IntegrationTest*'"
```

### Task Best Practices
- Clear, descriptive names
- Comprehensive descriptions
- Idempotent when possible
- Fail fast with clear errors
- Log meaningful output

### Common Tasks to Maintain
```bash
# Build and test
mise run build
mise run test
mise run test_one

# Docker management
mise run start_docker_components
mise run stop_docker_components
mise run restart_docker_components

# Application
mise run bootRun
mise run health_check_api

# Database
mise run mysql_shell

# Utilities
mise run gradle-tasks-all
```

## CI/CD Pipeline Management

### GitHub Actions Workflows
```yaml
# Location: .github/workflows/

# Key workflows:
- ci.yml: Build and test on PR
- deploy-dev.yml: Deploy to development
- deploy-staging.yml: Deploy to staging
- deploy-prod.yml: Deploy to production
```

### Pipeline Maintenance
- Monitor for failures
- Keep actions up to date
- Optimize build times
- Ensure tests are stable
- Document pipeline changes

### When Pipeline Fails
1. Investigate logs immediately
2. Identify root cause
3. Fix if automation issue
4. Notify team if code issue
5. Update documentation if needed

## Docker Configuration

### docker-compose.yml Maintenance
```yaml
# Key services to maintain:
- MySQL 8.0.16
- Redis 7.0.4
- Kafka 3.4 (if applicable)
- Zookeeper 3.8 (if applicable)
```

### Docker Best Practices
- Pin specific versions
- Document port mappings
- Maintain volume mounts
- Keep images up to date
- Test configuration changes

### Common Docker Issues
```bash
# MySQL won't start
# Check data directory permissions
sudo chown -R root:staff /path/to/mysql/data
sudo chmod -R 777 /path/to/mysql/data

# Port conflicts
# Find process using port
lsof -i :3307

# Container cleanup
docker-compose down -v
docker system prune -a
```

## Build Configuration

### Gradle Maintenance
```gradle
# build.gradle files to maintain:
- Root build.gradle
- Module-specific build.gradle files
- gradle.properties
```

### Version Management
- Keep dependencies up to date
- Test compatibility before updating
- Document version changes
- Update technology stack doc

### Build Optimization
- Enable build cache
- Parallelize where possible
- Minimize test dependencies
- Use incremental compilation

## Monitoring and Alerts

### What to Monitor
- CI/CD pipeline success rate
- Build times
- Test execution times
- Deployment success rate
- Application health

### Setting Up Alerts
- Pipeline failures
- Long-running builds
- Test flakiness
- Deployment issues
- Docker service issues

### Responding to Alerts
1. Acknowledge alert
2. Investigate cause
3. Fix or escalate
4. Document resolution
5. Prevent recurrence

## Automation Improvements

### Identifying Opportunities
- Manual tasks done repeatedly
- Slow or painful processes
- Error-prone procedures
- Inconsistent execution

### Implementing Automation
1. Identify task to automate
2. Design automation approach
3. Implement and test
4. Document usage
5. Train team
6. Monitor and iterate

### Examples
```bash
# Database reset automation
[tasks.db_reset]
description = "Reset database to clean state"
run = """
docker-compose down
rm -rf data/mysql/*
docker-compose up -d
sleep 10
mise run mysql_shell < schema.sql
"""

# Code quality checks
[tasks.quality_check]
description = "Run all quality checks"
run = """
mise run test
gradle check
markdownlint memory-bank/**/*.md
"""
```

## Infrastructure as Code

### Configuration Management
- Docker Compose for local
- Kubernetes manifests for cloud
- Helm charts if applicable
- Terraform for infrastructure

### Version Control
- All configuration in Git
- Review changes via PR
- Test before deploying
- Document changes

## Documentation

### Automation Documentation
```markdown
# For each automation:
- What it does
- When to use it
- How to use it
- What it requires
- What it outputs
- How to troubleshoot
```

### Maintaining .mise.toml
- Keep descriptions current
- Remove obsolete tasks
- Add new common tasks
- Group related tasks

## Success Criteria

### You're a Good Automation Agent When:
- ✅ Pipelines are stable and fast
- ✅ Docker environment is reliable
- ✅ Builds are reproducible
- ✅ Deployments are automated
- ✅ Issues are caught early
- ✅ Documentation is current
- ✅ Team trusts automation

### Red Flags:
- ❌ Frequent pipeline failures
- ❌ Slow or unreliable builds
- ❌ Manual deployment steps
- ❌ Flaky tests
- ❌ Undocumented automation
- ❌ Configuration drift

---

_Last updated: 2025-10-09_