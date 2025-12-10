---
title: Writing Internal Documentation
description: Learn how to create effective internal documentation for team processes, onboarding, and organizational knowledge management.
---

# Internal Documentation

Internal documentation serves team members rather than external users. It captures organizational knowledge, documents processes, and enables team coordination. Good internal docs improve productivity, reduce onboarding time, and preserve institutional knowledge.

## Internal Documentation Types

### Team Processes

How the team works:

- Development workflows
- Code review guidelines
- Meeting protocols
- Communication norms

### Onboarding

Getting new team members productive:

- Environment setup
- Account access
- Key contacts
- Team overview

### Technical Reference

Internal technical knowledge:

- System architecture
- Codebase guides
- Infrastructure documentation
- Development environment

### Decision Records

How and why decisions were made:

- Architecture decisions
- Process decisions
- Tool selections

## Team Process Documentation

### Development Workflow

```markdown
# Development Workflow

## Branch Strategy

We use trunk-based development with short-lived feature branches.

### Branch Naming

```
feature/JIRA-123-brief-description
bugfix/JIRA-456-brief-description
hotfix/JIRA-789-critical-fix
```

### Workflow

1. Create branch from `main`
2. Make changes with atomic commits
3. Open PR when ready for review
4. Address review feedback
5. Merge when approved (squash merge)

### Commit Messages

```
JIRA-123: Brief description of change

- Detail of what changed
- Why it was necessary
- Any notable implementation details
```

## Code Review

### Expectations

- Reviews completed within 24 hours
- At least one approval required
- Author addresses all comments
- Reviewer approves or requests changes (no "LGTM" only)

### What to Look For

- [ ] Code works as intended
- [ ] Tests cover new functionality
- [ ] No obvious security issues
- [ ] Follows team conventions
- [ ] Documentation updated if needed
```

### Meeting Documentation

```markdown
# Team Meetings

## Standup

**When**: Daily, 9:30 AM
**Where**: #team-standup (async) or Zoom (sync Tuesdays)
**Format**:
- What I did yesterday
- What I'm doing today
- Any blockers

## Sprint Planning

**When**: Every other Monday, 10:00 AM
**Duration**: 1 hour
**Preparation**: Review backlog before meeting

## Retrospectives

**When**: End of each sprint
**Duration**: 45 minutes
**Format**: Start/Stop/Continue
```

## Onboarding Documentation

### New Team Member Guide

```markdown
# Welcome to the Team!

## Week 1 Goals

By the end of your first week, you should:
- [ ] Have all accounts and access set up
- [ ] Complete environment setup
- [ ] Make your first commit (even a small one!)
- [ ] Meet everyone on the team

## Day 1

### Accounts to Request

| System | How to Request | Who Approves |
|--------|---------------|--------------|
| GitHub | IT ticket | Team Lead |
| AWS | IT ticket | Manager |
| Jira | IT ticket | Auto |
| Slack | Automatic | - |

### Install Required Software

Follow [Environment Setup](./environment-setup.md)

### Key Contacts

| Role | Person | Contact |
|------|--------|---------|
| Manager | Alice Smith | @alice |
| Tech Lead | Bob Jones | @bob |
| Buddy | Carol White | @carol |

## First Week

### Codebase Tour

Schedule with your buddy:
- Repository structure
- Key services
- Development workflow
- Testing approach

### Team Norms

Read these documents:
- [Development Workflow](./workflow.md)
- [Code Review Guidelines](./code-review.md)
- [On-Call Procedures](./on-call.md)

### First Task

Your first task will be a "good first issue" in the backlog.
Your buddy will help you through the process.
```

### Environment Setup

```markdown
# Environment Setup

## Prerequisites

- macOS 12+ or Ubuntu 22.04+
- 16GB RAM minimum
- 50GB free disk space

## Step 1: Install Homebrew (macOS)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Step 2: Install Required Tools

```bash
brew install git node python@3.11 docker docker-compose
```

## Step 3: Clone Repositories

```bash
mkdir ~/work
cd ~/work
git clone git@github.com:company/api.git
git clone git@github.com:company/web.git
git clone git@github.com:company/infrastructure.git
```

## Step 4: Configure Environment

Copy example environment file:
```bash
cp api/.env.example api/.env
```

Get secrets from 1Password vault "Development".

## Step 5: Start Services

```bash
cd ~/work/api
docker-compose up -d
npm install
npm run dev
```

## Step 6: Verify Setup

```bash
curl http://localhost:3000/health
```

Expected: `{"status":"ok"}`

## Troubleshooting

### Docker won't start

Check Docker Desktop is running and has sufficient resources allocated.

### npm install fails

Try clearing cache: `npm cache clean --force`

### Need Help?

Ask in #dev-help or ping your buddy.
```

## Technical Reference

### Codebase Guide

```markdown
# Codebase Overview

## Repository Structure

```
api/
├── src/
│   ├── controllers/    # HTTP request handlers
│   ├── services/       # Business logic
│   ├── models/         # Database models
│   ├── middleware/     # Express middleware
│   └── utils/          # Shared utilities
├── tests/
│   ├── unit/
│   └── integration/
├── scripts/            # Build and deployment scripts
└── docs/               # Technical documentation
```

## Key Files

| File | Purpose |
|------|---------|
| `src/index.js` | Application entry point |
| `src/config.js` | Configuration loading |
| `src/routes.js` | Route definitions |
| `docker-compose.yml` | Local development setup |

## Adding a New Endpoint

1. Create controller in `src/controllers/`
2. Add business logic in `src/services/`
3. Register route in `src/routes.js`
4. Add tests in `tests/`
5. Update API documentation

See [Adding Endpoints](./guides/adding-endpoints.md) for details.
```

## Writing Internal Docs

### Right Level of Detail

Internal docs can assume more context:

**For external users:**
> Click **Settings** in the navigation menu. In the Settings page,
> locate the **API Keys** section and click **Create New Key**.

**For internal teams:**
> Generate API key: Settings > API Keys > Create New Key

### Keep It Practical

Focus on what people need to do:

**Too theoretical:**
> Our CI/CD pipeline implements continuous integration principles...

**Practical:**
> To deploy: push to `main` and CI deploys automatically.
> Monitor deployment in #deployments.

### Encourage Contribution

Make docs easy to update:

```markdown
---
**Found something wrong?**
Edit this page: [link to source]
---
```

### Accept Imperfection

Internal docs can be rougher than external docs:

- Some incompleteness is acceptable
- "Ask @alice for details" is valid
- Notes and TODOs are fine
- Update as you go

## Maintenance

### Ownership

Assign documentation owners:

| Doc Area | Owner | Review Cycle |
|----------|-------|--------------|
| Onboarding | Team Lead | Quarterly |
| Runbooks | On-call rotation | Monthly |
| Architecture | Tech Lead | On change |

### Regular Review

Schedule documentation reviews:

- After incidents: Update runbooks
- After onboarding: Fix gaps new hires found
- Quarterly: Review for staleness

### Documentation Days

Periodically focus on documentation:

- Dedicated time for doc updates
- Fix known gaps
- Remove outdated content
- Improve organization

## Summary

Internal documentation enables team effectiveness:

- Document processes, onboarding, and technical reference
- Match detail to internal audience
- Focus on practical, actionable content
- Assign ownership and review regularly
- Accept iteration over perfection

Good internal docs reduce bus factor and improve team productivity.

---

This concludes the Document Types section. Explore [Tools & Technology](../tools/index.md) for documentation software and workflows.
