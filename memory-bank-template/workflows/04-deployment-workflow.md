# Deployment Workflow

This document defines the build, release, and deployment procedures for the intapi-assistant project.

## Build Process

### Local Build
```bash
# Clean and build
mise run build

# Build specific module
gradle :services:build
gradle :server:build

# Build without tests (faster)
gradle build -x test

# Build with all tests including functional
gradle build -PexecuteFunctionalTests=true
```

### Build Output
- Artifacts: `build/libs/*.jar`
- Test results: `build/test-results/`
- Reports: `build/reports/`

## Release Process

### Version Management

**Versioning Strategy**: Semantic Versioning (SemVer)
- `MAJOR.MINOR.PATCH` (e.g., 1.2.3)
- `MAJOR`: Breaking changes
- `MINOR`: New features, backwards compatible
- `PATCH`: Bug fixes, backwards compatible

**Version Location**: `build.gradle`
```groovy
version = '1.2.3'
```

### Creating a Release

#### 1. Prepare Release Branch
```bash
# Create release branch from main
git checkout main
git pull origin main
git checkout -b release/v1.2.3

# Update version in build.gradle
# Update CHANGELOG.md with release notes
```

#### 2. Release Checklist
- [ ] All planned features merged
- [ ] All tests passing
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] Version bumped in build.gradle
- [ ] No known critical bugs

#### 3. Build Release Artifact
```bash
# Clean build with all tests
mise run build
gradle build -PexecuteFunctionalTests=true

# Verify artifact
ls -lh build/libs/
```

#### 4. Create Release Tag
```bash
# Commit version bump
git add build.gradle CHANGELOG.md
git commit -m "chore: Bump version to 1.2.3"

# Create annotated tag
git tag -a v1.2.3 -m "Release version 1.2.3

## Features
- Feature 1
- Feature 2

## Bug Fixes
- Fix 1
- Fix 2

## Breaking Changes
- None
"

# Push tag and branch
git push origin release/v1.2.3
git push origin v1.2.3
```

#### 5. Merge to Main
```bash
# Create PR from release branch to main
gh pr create --title "Release v1.2.3" \
  --base main \
  --head release/v1.2.3 \
  --body "Release version 1.2.3"

# After approval, merge
gh pr merge --squash
```

## Deployment Environments

### Environment Overview
```
Development → Staging → Production
    ↓           ↓           ↓
  Local      Pre-prod    Live
```

### Environment Configuration

**Development**
- **Purpose**: Active development and testing
- **Data**: Test data, can be reset
- **Deployment**: Automatic on main branch merge
- **Config**: `application-dev.gconf`

**Staging**
- **Purpose**: Pre-production validation
- **Data**: Production-like data (anonymized)
- **Deployment**: Manual trigger on release branch
- **Config**: `application-staging.gconf`

**Production**
- **Purpose**: Live customer-facing environment
- **Data**: Real production data
- **Deployment**: Manual trigger on release tag
- **Config**: `application-prod.gconf`

## Deployment Process

### Deployment via CI/CD Pipeline

#### Development Deployment
```yaml
# Automatic on merge to main
trigger: main
steps:
  - Build application
  - Run tests
  - Build Docker image
  - Deploy to development
  - Run smoke tests
```

#### Staging Deployment
```bash
# Manual trigger via GitHub Actions
# 1. Navigate to Actions → Deploy to Staging
# 2. Select branch: release/v1.2.3
# 3. Click "Run workflow"
# 4. Monitor deployment logs
# 5. Verify deployment
```

#### Production Deployment
```bash
# Manual trigger via GitHub Actions
# 1. Navigate to Actions → Deploy to Production
# 2. Select tag: v1.2.3
# 3. Require approval from team lead
# 4. Click "Run workflow"
# 5. Monitor deployment carefully
# 6. Verify deployment
# 7. Monitor application health
```

### Deployment Verification

#### Post-Deployment Checklist
- [ ] Application starts successfully
- [ ] Health check endpoint responding
- [ ] Database migrations applied
- [ ] Integration points working
- [ ] Logs show no errors
- [ ] Metrics reporting correctly

#### Verification Commands
```bash
# Health check
curl https://<environment-url>/actuator/health

# Application info
curl https://<environment-url>/actuator/info

# Check logs
kubectl logs -f deployment/intapi-assistant -n <namespace>

# Check metrics
# Access monitoring dashboard
```

#### Smoke Tests
```bash
# Test critical endpoints
curl -X POST https://<environment-url>/api/v1/assistant/query \
  -H "Content-Type: application/json" \
  -H "x-tau-client-type: BUYER" \
  -H "x-tau-userid: test-user" \
  -d '{"userInput": "test", "category": "WORKING_CAPITAL"}'

# Verify response is successful
```

## Rollback Procedures

### When to Rollback
- Critical bugs in production
- Performance degradation
- Data integrity issues
- Integration failures

### Rollback Process

#### Quick Rollback (Kubernetes)
```bash
# Rollback to previous deployment
kubectl rollout undo deployment/intapi-assistant -n <namespace>

# Verify rollback
kubectl rollout status deployment/intapi-assistant -n <namespace>

# Check pod status
kubectl get pods -n <namespace>
```

#### Full Rollback (Re-deploy Previous Version)
```bash
# 1. Identify previous stable version
git tag -l

# 2. Trigger deployment with previous tag
# Via GitHub Actions: Deploy to Production
# Select tag: v1.2.2 (previous stable)

# 3. Monitor deployment

# 4. Verify rollback successful
```

#### Database Rollback
```bash
# If database migrations need rollback
# 1. Identify migration to rollback to
# 2. Create rollback changeset in Liquibase
# 3. Apply rollback migration
# 4. Verify data integrity
```

### Post-Rollback Actions
1. Notify team of rollback
2. Create incident ticket
3. Investigate root cause
4. Fix issue in development
5. Re-test thoroughly
6. Plan new deployment

## Monitoring and Observability

### Application Metrics
- **Response Times**: API endpoint latency
- **Error Rates**: 4xx and 5xx errors
- **Throughput**: Requests per second
- **Resource Usage**: CPU, memory, disk

### Logging
```bash
# View application logs
kubectl logs -f deployment/intapi-assistant -n <namespace>

# Search logs for errors
kubectl logs deployment/intapi-assistant -n <namespace> | grep ERROR

# View logs from specific pod
kubectl logs <pod-name> -n <namespace>
```

### Alerts
Configure alerts for:
- Application down
- High error rate (>5%)
- High response time (>2s p95)
- Memory usage (>80%)
- Database connection issues

## Deployment Best Practices

### Pre-Deployment
- Review and test changes thoroughly
- Communicate deployment schedule to team
- Verify all tests pass
- Check for dependency updates
- Review release notes

### During Deployment
- Monitor deployment progress
- Watch logs for errors
- Be ready to rollback
- Have team available for support

### Post-Deployment
- Verify deployment successful
- Run smoke tests
- Monitor metrics for anomalies
- Update status page
- Notify stakeholders

### Emergency Deployment (Hotfix)
```bash
# 1. Create hotfix branch from production tag
git checkout v1.2.3
git checkout -b hotfix/v1.2.4

# 2. Make minimal fix and test
# [make changes]
mise run test

# 3. Bump patch version
# Update to 1.2.4 in build.gradle

# 4. Commit and tag
git commit -m "fix: Critical hotfix for [issue]"
git tag v1.2.4
git push origin hotfix/v1.2.4
git push origin v1.2.4

# 5. Deploy to production immediately
# Via GitHub Actions with approval

# 6. Merge hotfix back to main
git checkout main
git merge hotfix/v1.2.4
git push origin main
```

## Deployment Checklist

### Release Preparation
- [ ] Version updated in build.gradle
- [ ] CHANGELOG.md updated
- [ ] Documentation updated
- [ ] All tests passing
- [ ] Security scan completed
- [ ] Performance testing done

### Deployment Execution
- [ ] Deployment announcement sent
- [ ] Backup created (if applicable)
- [ ] Deployment triggered
- [ ] Deployment logs monitored
- [ ] Smoke tests executed
- [ ] Metrics verified

### Post-Deployment
- [ ] Application health verified
- [ ] Integration points tested
- [ ] Stakeholders notified
- [ ] Documentation updated
- [ ] Rollback plan ready if needed

---

_Last updated: 2025-10-09_