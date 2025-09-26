# Roles and Permissions in Ticket Management

This document defines the roles, responsibilities, and permissions for all team members involved in ticket management and story point estimation.

## Role Overview

| Role | Primary Responsibility | Estimation Involvement |
|------|----------------------|----------------------|
| **Product Owner** | Requirements and Priorities | Clarification and Acceptance |
| **Scrum Master** | Process Facilitation | Session Facilitation |
| **Development Team** | Implementation | Active Estimation |
| **QA Team** | Quality Assurance | Testing Effort Input |
| **Technical Lead** | Technical Guidance | Architecture Estimation |
| **Stakeholders** | Business Requirements | Requirements Validation |

## Detailed Role Definitions

### Product Owner

**Core Responsibilities**:
- Define user stories and acceptance criteria
- Prioritize product backlog
- Participate in estimation sessions for clarification
- Accept completed work using Definition of Done
- Make scope change decisions

**Estimation Activities**:
- Provide requirements clarification during Planning Poker
- Help break down large epics into smaller stories
- Validate business complexity factors
- Approve final story estimates

**Permissions**:
- ✅ Create and modify user stories
- ✅ Set story priorities
- ✅ Accept/reject completed work
- ✅ Request re-estimation for scope changes
- ❌ Override technical estimates without team consensus

**Best Practices**:
- Attend all estimation sessions
- Prepare clear acceptance criteria before estimation
- Be available for questions during sprint
- Validate business value against effort estimates

### Scrum Master

**Core Responsibilities**:
- Facilitate Planning Poker sessions
- Ensure estimation best practices are followed
- Track team velocity and estimation accuracy
- Remove impediments affecting story completion
- Coach team on estimation techniques

**Estimation Activities**:
- Moderate estimation discussions
- Ensure all team members participate
- Guide consensus-building process
- Document estimation rationale
- Track estimation vs. actual effort

**Permissions**:
- ✅ Facilitate estimation sessions
- ✅ Access velocity and estimation metrics
- ✅ Modify story workflow status
- ✅ Schedule and run retrospectives
- ❌ Provide technical estimates
- ❌ Override team consensus

**Best Practices**:
- Keep estimation sessions time-boxed
- Encourage equal participation from all team members
- Focus on relative sizing, not absolute time
- Track and share estimation improvement metrics

### Development Team

**Core Responsibilities**:
- Provide technical estimates for all stories
- Implement features according to acceptance criteria
- Write and maintain automated tests
- Participate actively in estimation sessions
- Update story status throughout development

**Estimation Activities**:
- Participate in Planning Poker sessions
- Provide input on technical complexity
- Consider implementation effort and risk
- Break down large stories into manageable pieces
- Track actual effort against estimates

**Permissions**:
- ✅ Participate in estimation sessions
- ✅ Update story status and progress
- ✅ Request story re-estimation for scope changes
- ✅ Create technical tasks and subtasks
- ✅ Add implementation notes and comments
- ❌ Change accepted estimates without team agreement

**Best Practices**:
- Come prepared to estimation sessions
- Consider all aspects: development, testing, deployment
- Speak up about technical risks and unknowns
- Update story progress regularly
- Learn from estimation accuracy over time

### QA Team

**Core Responsibilities**:
- Validate acceptance criteria completeness
- Estimate testing effort and complexity
- Execute comprehensive test scenarios
- Report defects with appropriate priority
- Participate in Definition of Done validation

**Estimation Activities**:
- Provide input on testing complexity
- Identify test automation requirements
- Estimate manual testing effort
- Consider regression testing scope
- Input on user acceptance testing needs

**Permissions**:
- ✅ Participate in estimation sessions
- ✅ Add testing-related tasks to stories
- ✅ Update testing status and results
- ✅ Create defect reports with estimates
- ✅ Validate Definition of Done completion
- ❌ Approve stories without proper testing

**Best Practices**:
- Review acceptance criteria before estimation
- Consider both happy path and edge cases
- Factor in test data preparation time
- Include accessibility and performance testing
- Maintain test automation alongside development

### Technical Lead / Architect

**Core Responsibilities**:
- Provide technical guidance for complex stories
- Review architectural implications of features
- Identify technical dependencies and risks
- Mentor team on estimation techniques
- Make final decisions on disputed estimates

**Estimation Activities**:
- Guide technical complexity assessment
- Identify architecture and integration challenges
- Help break down complex technical stories
- Provide input on technical risk factors
- Validate technical feasibility of estimates

**Permissions**:
- ✅ Participate in estimation sessions
- ✅ Provide architectural guidance
- ✅ Request technical spikes for complex stories
- ✅ Make final call on technical estimate disputes
- ✅ Review and approve technical task estimates
- ❌ Override business priority decisions

**Best Practices**:
- Share architectural context during estimation
- Help team understand technical dependencies
- Encourage proper breakdown of complex work
- Balance technical debt with new feature work
- Document architectural decisions affecting estimates

## Permission Matrix

| Activity | PO | SM | Dev | QA | TL | Stakeholder |
|----------|----|----|-----|----|----|-------------|
| **Create User Stories** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Participate in Estimation** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| **Facilitate Planning Poker** | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ |
| **Provide Technical Estimates** | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ |
| **Provide Testing Estimates** | ❌ | ❌ | ✅ | ✅ | ❌ | ❌ |
| **Break Down Stories** | ✅ | ❌ | ✅ | ❌ | ✅ | ❌ |
| **Accept Completed Work** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Update Story Status** | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ |
| **View Velocity Metrics** | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ |
| **Modify Estimates Post-Planning** | ❌ | ❌ | ⚠️* | ❌ | ⚠️* | ❌ |

*⚠️ = Requires team consensus and documentation

## Escalation Hierarchy

### Estimation Disputes
1. **Team Discussion** → Development Team consensus
2. **Technical Clarification** → Technical Lead decision
3. **Business Priority** → Product Owner decision
4. **Process Issue** → Scrum Master facilitation
5. **Final Escalation** → Management decision

### Story Acceptance Disputes
1. **Acceptance Criteria Review** → Product Owner and QA Team
2. **Technical Implementation** → Technical Lead review
3. **Definition of Done** → Scrum Master validation
4. **Business Value** → Product Owner decision
5. **Quality Standards** → QA Team validation

## Communication Protocols

### Daily Standups
- **Who**: Development Team, Scrum Master, Product Owner (optional)
- **Focus**: Progress against estimated stories
- **Duration**: 15 minutes maximum

### Sprint Planning
- **Who**: All team members
- **Focus**: Story selection and commitment based on estimates
- **Duration**: 2 hours per week of sprint

### Backlog Refinement
- **Who**: Development Team, Product Owner, Scrum Master
- **Focus**: Story estimation and breakdown
- **Duration**: 10% of sprint capacity

### Sprint Review
- **Who**: All team members, Stakeholders
- **Focus**: Demonstrate completed estimated work
- **Duration**: 1 hour per week of sprint

### Retrospectives
- **Who**: Development Team, Scrum Master, Product Owner
- **Focus**: Estimation accuracy and process improvement
- **Duration**: 45 minutes per sprint

## Training and Development

### Onboarding New Team Members
- Review story point scale and examples
- Participate in 2-3 estimation sessions as observer
- Practice with historical stories for calibration
- Pair with experienced estimators for mentoring

### Continuous Improvement
- Regular calibration sessions using completed stories
- Workshops on estimation techniques
- Retrospectives focused on estimation accuracy
- Cross-team sharing of best practices

---

_Last updated: [YYYY-MM-DD]_