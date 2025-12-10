---
title: Information Architecture
description: Designing documentation structure for findability and usability.
---

# Information Architecture

Information architecture (IA) organizes and structures documentation so users can find what they need. Good IA makes documentation intuitive; poor IA makes even great content hard to use.

## What Information Architecture Does

### Core Functions

IA answers these questions for users:

- **Where am I?** (Location awareness)
- **What's here?** (Content understanding)
- **Where can I go?** (Navigation options)
- **How do I find X?** (Search and discovery)

### Components

- **Organization**: How content is grouped
- **Labeling**: What things are called
- **Navigation**: How users move through content
- **Search**: How users find specific information

## IA Principles

### User-Centered Design

Design for how users think, not how the product is built:

```
Product Structure (Internal):
├── Core Engine
├── Plugin System
├── API Layer
└── Configuration Module

User Mental Model (Better):
├── Getting Started
├── Common Tasks
├── Advanced Features
└── Troubleshooting
```

### Progressive Disclosure

Reveal complexity gradually:

```
Level 1: Overview (everyone)
Level 2: Common tasks (most users)
Level 3: Advanced features (power users)
Level 4: API reference (developers)
```

### Consistency

Use consistent patterns throughout:

- Same terms for same concepts
- Same structure for similar content
- Same navigation patterns
- Same URL conventions

## Organization Schemes

### By Task

Organize around what users want to do:

```markdown
# Task-Based Organization

docs/
├── getting-started/
│   ├── quick-start.md
│   ├── installation.md
│   └── first-project.md
├── working-with-data/
│   ├── importing-data.md
│   ├── exporting-data.md
│   └── transforming-data.md
├── collaboration/
│   ├── sharing-projects.md
│   ├── managing-team.md
│   └── permissions.md
└── troubleshooting/
    ├── common-errors.md
    └── getting-help.md
```

### By User Type

Organize for different audiences:

```markdown
# Audience-Based Organization

docs/
├── users/
│   ├── getting-started.md
│   ├── daily-workflows.md
│   └── tips-and-tricks.md
├── administrators/
│   ├── setup.md
│   ├── configuration.md
│   └── security.md
└── developers/
    ├── api-reference.md
    ├── integrations.md
    └── customization.md
```

### By Topic

Organize around subject areas:

```markdown
# Topic-Based Organization

docs/
├── accounts/
│   ├── creating-accounts.md
│   ├── managing-users.md
│   └── billing.md
├── projects/
│   ├── creating-projects.md
│   ├── project-settings.md
│   └── archiving.md
└── integrations/
    ├── slack.md
    ├── github.md
    └── jira.md
```

### Hybrid Approaches

Combine schemes as needed:

```markdown
# Hybrid Organization

docs/
├── getting-started/          # Task-based entry point
├── guides/                   # Task-based tutorials
├── reference/                # Topic-based reference
│   ├── api/
│   └── configuration/
└── resources/                # Audience-based resources
    ├── for-developers/
    └── for-admins/
```

## Navigation Design

### Primary Navigation

Top-level categories visible across all pages:

```markdown
# Main Navigation

Home | Docs | API | Guides | Community | Support

# Documentation Navigation

Getting Started | User Guide | API Reference | Tutorials
```

### Local Navigation

Section-specific navigation:

```markdown
# In "Getting Started" section

Getting Started
├── Quick Start     ← You are here
├── Installation
├── Configuration
└── First Project
```

### Breadcrumbs

Show location in hierarchy:

```
Home > Docs > Getting Started > Installation
```

### Cross-Links

Connect related content:

```markdown
## Related Topics

- [Configuring the database](../configuration/database.md)
- [Troubleshooting installation](../troubleshooting/installation.md)
- [Upgrading from v1](../migration/v1-to-v2.md)
```

## Labeling

### Naming Principles

Good labels are:

- **Clear**: Meaning is obvious
- **Concise**: Short but complete
- **Consistent**: Same terms throughout
- **Specific**: Not generic or vague

### Common Patterns

| Instead of | Use |
|------------|-----|
| Miscellaneous | Specific category name |
| Advanced | [Specific feature] |
| More Information | Related Topics |
| Resources | Tutorials, Reference, etc. |
| FAQ | Troubleshooting or specific topic |

### Testing Labels

Validate labels with users:

- Card sorting exercises
- First-click testing
- Navigation testing
- Search log analysis

## Designing for Scale

### Scalable Structure

Plan for growth:

```markdown
# Structure that scales

docs/
├── products/
│   ├── product-a/
│   │   ├── getting-started/
│   │   ├── user-guide/
│   │   └── reference/
│   └── product-b/
│       ├── getting-started/
│       ├── user-guide/
│       └── reference/
└── shared/
    ├── account-management/
    └── billing/
```

### URL Structure

Design URLs for longevity:

```markdown
# Good URL patterns
/docs/guides/getting-started/
/docs/api/v2/endpoints/users/
/docs/reference/configuration/

# Avoid
/docs/page-12345/
/docs/new-feature/  (becomes outdated)
/docs/2024/january/  (date-based)
```

### Versioning Strategy

Handle multiple versions:

```markdown
# Version navigation

Latest (v3) | v2 | v1

# URL patterns
/docs/latest/...
/docs/v2/...
/docs/v1/...
```

## IA Documentation

### Document Your IA

Create a site map:

```markdown
# Documentation Site Map

## Level 1: Primary Sections

1. Getting Started
2. User Guide
3. API Reference
4. Tutorials
5. Troubleshooting

## Level 2: Getting Started

1.1 Quick Start
1.2 Installation
1.3 Configuration
1.4 First Project

## Level 3: Installation

1.2.1 System Requirements
1.2.2 Installing on macOS
1.2.3 Installing on Windows
1.2.4 Installing on Linux
```

### Navigation Matrix

Map navigation elements:

| Page | Global Nav | Local Nav | Breadcrumbs | Related |
|------|-----------|-----------|-------------|---------|
| Home | ✓ | — | — | ✓ |
| Quick Start | ✓ | Getting Started | ✓ | ✓ |
| API Reference | ✓ | API sections | ✓ | ✓ |

## Evaluating IA

### Usability Testing

Test with real users:

- Can users find information?
- Where do users get lost?
- What do users call things?
- What paths do users take?

### Analytics

Measure effectiveness:

- Search queries (what are people looking for?)
- Navigation paths (how do people browse?)
- Exit pages (where do people leave?)
- Time on page (are people finding content?)

### Tree Testing

Test structure without visual design:

1. Present hierarchy as text tree
2. Ask users to find specific information
3. Measure success rate and path

## Summary

Effective information architecture:

- Organizes content around user needs
- Provides clear, consistent navigation
- Uses meaningful labels
- Scales with content growth
- Improves through testing and iteration

Good IA is invisible—users find what they need without thinking about structure.
