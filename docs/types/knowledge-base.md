---
title: Writing Knowledge Base Articles
description: Learn how to create effective knowledge base articles that help users solve problems and find answers through self-service support.
---

# Knowledge Base Articles

Knowledge base (KB) articles provide self-service support content. They answer common questions, explain features, and help users solve problems without contacting support. A good knowledge base reduces support costs while improving user satisfaction.

## Knowledge Base Purpose

Knowledge bases serve multiple goals:

- **Deflect support tickets**: Users find answers themselves
- **Improve user satisfaction**: Faster answers than waiting for support
- **Scale support**: Content serves unlimited users simultaneously
- **Capture expertise**: Document solutions for reuse
- **Improve SEO**: Attract users searching for solutions

## Article Types

### How-To Articles

Step-by-step instructions for tasks:

```markdown
# How to Reset Your Password

If you forgot your password or want to change it, follow these steps.

## Steps

1. Go to the login page.
2. Click **Forgot Password**.
3. Enter your email address.
4. Click **Send Reset Link**.
5. Check your email for the reset link.
6. Click the link and enter your new password.
7. Click **Save**.

You can now sign in with your new password.

## Related Articles

- [Password requirements](password-requirements.md)
- [Two-factor authentication setup](2fa-setup.md)
```

### Troubleshooting Articles

Solutions for specific problems:

```markdown
# Error: "Connection Refused" When Signing In

## Symptoms

When trying to sign in, you see the error message:
> Connection refused. Please try again later.

## Causes

This error occurs when:
- The service is temporarily unavailable
- Your network blocks the connection
- Your firewall settings prevent access

## Solutions

### Check Service Status

1. Visit our [status page](https://status.example.com)
2. Check for ongoing incidents
3. If there's an incident, wait for resolution

### Check Your Network

1. Try accessing other websites
2. If other sites work, continue to next solution
3. If other sites fail, contact your network administrator

### Check Firewall Settings

1. Ensure your firewall allows connections to *.example.com
2. Allow outbound HTTPS (port 443)
3. Try signing in again

## Still Having Issues?

If these solutions don't work, [contact support](../support.md)
with the following information:
- Your browser and version
- Your operating system
- The exact error message
- Any error codes displayed
```

### Concept Explanations

Explain features or concepts:

```markdown
# Understanding User Roles

User roles determine what actions users can take in your account.

## Available Roles

| Role | Description | Permissions |
|------|-------------|-------------|
| Viewer | Read-only access | View content |
| Editor | Create and edit | View, create, edit content |
| Admin | Full access | All actions including user management |

## Role Inheritance

Users can have different roles in different workspaces. The highest
role applies when roles conflict.

## Best Practices

- Assign the minimum role needed for each user's job
- Use Admin sparingly
- Review role assignments quarterly

## Related Articles

- [How to assign user roles](assign-roles.md)
- [Custom roles](custom-roles.md)
```

### FAQ Articles

Answer specific questions:

```markdown
# Can I Export My Data?

**Yes.** You can export your data at any time.

## Export Options

- **Individual items**: Export single documents or reports
- **Bulk export**: Export all data in your account
- **API export**: Export programmatically

## How to Export

1. Go to **Settings > Data Management**
2. Click **Export Data**
3. Select what to export
4. Choose format (CSV, JSON, or PDF)
5. Click **Export**

You'll receive an email with a download link when the export is ready.

## Related Questions

- [What formats can I export to?](export-formats.md)
- [How long are export files available?](export-availability.md)
```

## Article Structure

### Standard Components

Every KB article should include:

**Title**: Clear, searchable question or topic

**Summary**: Brief answer or overview (first paragraph)

**Body**: Detailed explanation, steps, or solutions

**Related articles**: Links to connected content

### Title Guidelines

Write searchable titles:

**Vague:**
> Getting Started
> Password Help
> Error Message

**Searchable:**
> How to Reset Your Password
> Error: "Invalid API Key" When Making Requests
> Setting Up Two-Factor Authentication

Match how users search. Use the same words they would use.

### Summary (First Paragraph)

Answer the question immediately:

```markdown
# Can I Cancel My Subscription?

**Yes.** You can cancel your subscription at any time from your
account settings. You'll continue to have access until the end
of your current billing period.

## How to Cancel
[detailed steps]
```

Users scanning should get the answer from the first paragraph.

## Writing Guidelines

### Use Clear Language

- Simple words over complex ones
- Short sentences
- Active voice
- Second person ("you")

### Be Scannable

- Use headings for sections
- Use lists for steps and options
- Use bold for key terms
- Keep paragraphs short

### Provide Complete Answers

Answer the full question:

**Incomplete:**
> To reset your password, click Forgot Password on the login page.

**Complete:**
> To reset your password:
> 1. Go to the login page
> 2. Click **Forgot Password**
> 3. Enter your email address
> 4. Check your email for the reset link
> 5. Click the link and create a new password

### Include Visual Aids

Add screenshots and diagrams where helpful:

- Complex UI interactions
- Settings locations
- Error messages
- Workflow diagrams

### Address Edge Cases

Anticipate follow-up questions:

```markdown
## Notes

- Password reset links expire after 24 hours
- You can request a new link if the first one expires
- If you don't receive the email, check your spam folder
```

## Organization

### Categories

Organize articles logically:

```
Getting Started
├── Creating your account
├── Initial setup
└── First project

Account Management
├── Profile settings
├── Password and security
└── Billing

Features
├── Documents
├── Reports
└── Integrations

Troubleshooting
├── Sign-in issues
├── Performance problems
└── Error messages
```

### Search Optimization

Make articles findable:

- Include keywords users search for
- Add synonyms (login, log in, sign in)
- Tag articles with related terms
- Use consistent terminology

### Cross-Linking

Connect related articles:

- "See also" sections
- In-line links to related topics
- "Related articles" at the end
- Links to deeper documentation

## Maintenance

### Regular Review

Review articles periodically:

- Are procedures still accurate?
- Do screenshots match current UI?
- Are there better solutions?
- Is anything missing?

### Usage Analytics

Track article performance:

- Most viewed articles
- Search queries with no results
- Article ratings
- Exit rates (users leaving without finding help)

### Feedback Integration

Act on user feedback:

- "Was this helpful?" ratings
- Comment submissions
- Support tickets citing article gaps
- Search analytics

### Continuous Improvement

Use data to improve:

- Create articles for common search failures
- Update low-rated articles
- Expand frequently viewed articles
- Archive outdated content

## Quality Metrics

### Deflection Rate

Percentage of users who find answers without contacting support.

**Track**: Support tickets before and after KB article creation

### Self-Service Success

Whether users accomplish their goals.

**Track**: Article completion, ratings, return visits

### Search Success

Whether users find relevant articles.

**Track**: Search-to-article, zero-result searches

### User Satisfaction

Direct feedback on article helpfulness.

**Track**: Article ratings, comments, surveys

## Summary

Knowledge base articles enable self-service support:

- Match article types to user needs (how-to, troubleshooting, concepts, FAQ)
- Structure for scannability and searchability
- Answer questions completely
- Organize for findability
- Maintain through regular review and feedback

A well-maintained knowledge base improves user satisfaction while reducing support costs.

---

**Next**: [Installation Guides](installation-guides.md) covers setup documentation.
