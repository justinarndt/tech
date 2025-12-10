---
title: Task-Based Writing for Technical Documentation
description: Learn how to structure technical documentation around user tasks rather than product features for more effective user guidance.
---

# Task-Based Writing

Task-based writing organizes documentation around what users want to accomplish rather than how products are structured. Instead of documenting feature by feature, task-based documentation answers "How do I...?" questions.

## Why Task-Based Organization

### Users Think in Tasks

Users approach documentation with goals:

- "How do I set up authentication?"
- "How do I import my data?"
- "How do I troubleshoot connection errors?"

They do not think:

- "I want to learn about the Authentication module"
- "I need to understand the Import functionality"
- "Tell me about the Connection Manager"

Task-based documentation meets users where they are.

### Features Span Multiple Tasks

A single feature may support multiple tasks:

**The Settings panel** is involved in:

- Creating user accounts
- Configuring security
- Setting up integrations
- Customizing notifications

Feature-based documentation makes users hunt across sections for complete task information.

### Tasks Span Multiple Features

Completing a task often requires multiple features:

**Setting up authentication** involves:

- User management
- Role configuration
- Security settings
- Integration setup

Task-based documentation brings this together logically.

## Identifying User Tasks

### Task Analysis

Understand what users need to accomplish:

**Research methods:**

- User interviews about their goals
- Support ticket analysis
- Search query analysis
- Workflow observation

**Questions to answer:**

- What do users want to achieve?
- What steps are involved?
- What decisions do users make?
- Where do users encounter problems?

### Task Hierarchy

Organize tasks at appropriate levels:

**High-level goals:**
> Manage user access to the application

**Tasks:**
> - Set up new user accounts
> - Configure user permissions
> - Remove user access
> - Reset user passwords

**Subtasks:**
> Set up new user accounts:
> - Create user account
> - Assign role
> - Send invitation
> - Verify account activation

Different documentation serves different levels of this hierarchy.

### Task Prioritization

Focus on:

- **Frequent tasks**: What do users do most often?
- **Critical tasks**: What must users get right?
- **Problematic tasks**: Where do users struggle?
- **Entry tasks**: What do new users need to do first?

Not all tasks need equal documentation depth.

## Task-Based Document Structure

### Task Page Structure

Task pages follow a consistent pattern:

```markdown
# [Task Name]

Brief description of what this task accomplishes and when users would do it.

## Before You Begin

Prerequisites and required information.

## Steps

1. First step
2. Second step
3. Third step

## Verify Success

How to confirm the task completed successfully.

## Troubleshooting

Common problems and solutions.

## Next Steps

Related tasks users might want to do next.
```

### Example Task Page

```markdown
# Create a New User Account

Add team members to your organization so they can access the platform.

## Before You Begin

You need:
- Administrator role in your organization
- Email address for the new user
- Decision on what role to assign

## Steps

1. Go to **Settings > Users**.
2. Click **Add User**.
3. Enter the user's email address.
4. Select a role from the dropdown:
   - **Admin**: Full access to all features and settings
   - **Editor**: Can create and modify content
   - **Viewer**: Read-only access
5. Click **Send Invitation**.

The user receives an email with instructions to set up their account.

## Verify Success

The new user appears in the Users list with "Pending" status until they accept the invitation.

## Troubleshooting

**Invitation not received**
Check that the email address is correct. Check spam folders. Resend from the user's Actions menu.

**Cannot add user**
Verify you have administrator permissions. Check if you have reached your plan's user limit.

## Next Steps

- [Configure user permissions](configure-permissions.md)
- [Set up teams](create-teams.md)
- [Enable single sign-on](sso-setup.md)
```

## Task-Based Navigation

### Navigation Patterns

Organize navigation around task categories:

```markdown
Getting Started
├── Create your account
├── Set up your first project
└── Invite team members

Managing Content
├── Create new content
├── Edit existing content
├── Organize content into collections
└── Archive old content

Working with Integrations
├── Connect to external services
├── Configure webhooks
├── Set up API access
└── Troubleshoot integration issues
```

### Scenario-Based Organization

Group tasks by user scenarios:

```markdown
For New Users
├── Initial setup tasks

For Content Creators
├── Daily content tasks

For Administrators
├── Organization management tasks

For Developers
├── Integration and API tasks
```

### Mixed Organization

Combine task-based and reference organization:

```markdown
Guides (task-based)
├── Getting Started
├── Common Tasks
└── Advanced Topics

Reference (feature-based)
├── API Reference
├── Configuration Options
└── Error Codes
```

Users performing tasks use guides; users looking up specifics use reference.

## Writing Task Steps

### Clear Step Structure

Each step should:

- Begin with an action verb
- Describe one action
- Include location information
- Show expected result when helpful

**Vague step:**
> Configure the settings.

**Clear step:**
> In **Settings > Security**, enable **Two-Factor Authentication**.

### Step Granularity

Find appropriate granularity:

**Too granular:**
> 1. Move your mouse to the menu bar.
> 2. Click the Settings menu.
> 3. Wait for the menu to open.
> 4. Move your mouse to the Security option.
> 5. Click Security.

**Too coarse:**
> 1. Configure security settings.

**Appropriate:**
> 1. Go to **Settings > Security**.
> 2. Enable **Two-Factor Authentication**.
> 3. Select your preferred method: App or SMS.

### Decision Points

Document decisions users must make:

```markdown
5. Select a notification method:
   - **Email**: Receive notifications via email (may be delayed)
   - **Push**: Receive instant push notifications (requires mobile app)
   - **Both**: Receive both email and push notifications
```

### Conditional Steps

Handle variations clearly:

```markdown
4. Configure your connection:
   - **If using cloud hosting**: Enter your cloud instance URL
   - **If self-hosting**: Enter your server IP address and port
```

Or use tabs:

=== "Cloud Hosting"
    Enter your cloud instance URL (e.g., `https://mycompany.example.com`).

=== "Self-Hosting"
    Enter your server IP address and port (e.g., `192.168.1.100:8080`).

## Connecting Tasks

### Prerequisites

Link to prerequisite tasks:

```markdown
## Before You Begin

Complete these tasks first:
- [Create an account](create-account.md)
- [Verify your email](verify-email.md)
```

### Related Tasks

Connect related tasks:

```markdown
## Related Tasks

- [Edit user permissions](edit-permissions.md)
- [Bulk import users](bulk-import.md)
- [Export user list](export-users.md)
```

### Task Sequences

For multi-task workflows, provide roadmaps:

```markdown
## Deployment Workflow

1. [Prepare your environment](prepare-environment.md)
2. [Configure settings](configure-settings.md)
3. [Deploy the application](deploy-app.md) ← You are here
4. [Verify deployment](verify-deployment.md)
5. [Configure monitoring](setup-monitoring.md)
```

## Task-Based Content Types

### Getting Started Guides

Sequence of tasks for new users:

1. Create account
2. Complete initial setup
3. Try core feature
4. Explore next steps

Goal: Fastest path to initial value.

### How-To Guides

Single-task documentation:

- Focused on one outcome
- Complete steps from start to finish
- Self-contained

### Tutorials

Learning-oriented task sequences:

- Build understanding progressively
- Include explanations with tasks
- Guide exploration

### Workflows

Multi-task processes:

- Complex procedures spanning multiple tasks
- Decision points with different paths
- Integration of multiple features

## Common Mistakes

### Feature-Based Disguise

Labeling feature documentation as tasks:

**Feature-based (disguised):**
> How to Use the Dashboard

**Genuinely task-based:**
> Monitor Your Application Performance

The first describes a feature; the second addresses a goal.

### Missing Context

Tasks without clear purpose:

**Missing why:**
> # Configure Webhooks
> 1. Go to Settings > Webhooks...

**With context:**
> # Configure Webhooks
> Set up webhooks to notify external services when events occur in your application.

Users should understand why they would perform the task.

### Incomplete Tasks

Stopping before the goal is achieved:

**Incomplete:**
> ...Click Save. The webhook is configured.

**Complete:**
> ...Click Save.
>
> To verify the webhook is working, click **Test**. You should receive a test notification at your endpoint within 30 seconds.

Tasks should include verification that the goal was achieved.

## Summary

Task-based writing organizes documentation around user goals:

- **Identify tasks** through user research and analysis
- **Structure pages** with consistent patterns (prerequisites, steps, verification, troubleshooting)
- **Write clear steps** with action verbs and appropriate granularity
- **Connect tasks** with prerequisites, related tasks, and workflows
- **Navigate by tasks** rather than features

Task-based documentation meets users where they are—trying to accomplish something—rather than forcing them to understand product structure first.

---

**Next**: [Writing for Translation](writing-for-translation.md) covers preparing content for localization.
