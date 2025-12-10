---
title: Content Reuse in Technical Documentation
description: Learn strategies for writing modular content that can be reused across documents, reducing maintenance burden and ensuring consistency.
---

# Content Reuse

Content reuse means writing information once and using it in multiple places. When the same information appears in several documents, maintaining separate copies creates inconsistency and multiplies update effort. Reuse solves this problem.

## Why Reuse Content

### Efficiency

Writing once instead of multiple times:

- Reduces initial writing effort
- Concentrates expertise in one location
- Allows faster documentation of new products

### Consistency

Single source of truth ensures:

- Same information everywhere it appears
- Updates propagate automatically
- No contradicting versions

### Maintenance

Updating one source instead of many:

- Reduces update effort
- Prevents missed updates
- Simplifies version control

### Quality

Focus effort on making one version excellent:

- Better reviewed and refined
- Easier to keep current
- Higher overall quality

## Reuse Approaches

### Copy-and-Paste (Anti-Pattern)

The simplest approach is copying content between documents.

**Problems:**

- Creates multiple sources of truth
- Updates must be made everywhere
- Copies drift apart over time
- No tracking of where content appears

Copy-and-paste creates the illusion of reuse while creating maintenance burden.

### Transclusion

Transclusion includes content from one file in another. The source remains in one location; the output appears in multiple places.

**Markdown example with MkDocs:**

```markdown
<!-- In shared/prerequisites.md -->
Before you begin, ensure you have:
- Admin access to your account
- API key with write permissions
- Network access to api.example.com

<!-- In installation.md -->
## Prerequisites

--8<-- "shared/prerequisites.md"

## Installation Steps
...
```

Changes to `prerequisites.md` appear everywhere it is included.

### Variables

Variables allow single values to appear in multiple places:

```markdown
<!-- Configuration -->
product_name: "Acme Platform"
current_version: "3.2.1"

<!-- In documentation -->
Welcome to {{ product_name }}. This guide covers version {{ current_version }}.
```

Changing the variable updates all instances.

### Conditional Content

Conditional content shows different variations from the same source:

```text
if platform == "windows":
    Open Command Prompt and run:
    installer.exe

elif platform == "mac":
    Open Terminal and run:
    ./installer.sh
```

The actual syntax varies by tool (DITA, Flare, static site generators).

Single source, multiple outputs.

### Content References

References point to content without including it:

```markdown
For installation prerequisites, see [Prerequisites](../getting-started/prerequisites.md).
```

Less powerful than transclusion but simpler to implement.

## Designing Reusable Content

Not all content can be reused. Effective reuse requires intentional design.

### Modularity

Reusable content must be self-contained:

**Not modular (depends on context):**
> This step is similar to what you did in the previous section...

**Modular (self-contained):**
> To configure authentication, open Settings and select Security.

Modular content makes sense wherever it appears.

### Appropriate Granularity

Find the right size for reusable chunks:

**Too small:**
Reusing individual sentences creates management overhead without significant benefit.

**Too large:**
Reusing entire documents limits flexibility for different contexts.

**Right-sized:**
Reusing procedures, concept explanations, or reference tables provides benefit without excessive complexity.

### Context Independence

Reusable content should not assume context:

**Context-dependent:**
> After completing the above steps, you can now configure webhooks.

**Context-independent:**
> After installing the application, you can configure webhooks.

Explicit context allows use in different documents.

### Consistent Structure

Reused content benefits from consistent structure:

```markdown
<!-- All procedure includes follow this pattern -->
## Prerequisites
[what's needed before starting]

## Steps
[numbered procedure]

## Verification
[how to confirm success]
```

Consistent structure makes content predictable wherever it appears.

## Reuse Patterns

### Warning and Note Reuse

Standard warnings appear across documentation:

```markdown
<!-- shared/warnings/data-loss.md -->
!!! warning "Data Loss Risk"
    This action cannot be undone. Ensure you have backed up your data before proceeding.
```

Include wherever the warning applies:

```markdown
## Deleting Your Account

--8<-- "shared/warnings/data-loss.md"

To delete your account:
1. Go to Settings...
```

### Procedure Reuse

Common procedures appear in multiple contexts:

```markdown
<!-- shared/procedures/sign-in.md -->
1. Navigate to [example.com/login](https://example.com/login).
2. Enter your email address.
3. Enter your password.
4. Click **Sign In**.
```

Include in any document requiring sign-in:

```markdown
## Accessing the Dashboard

First, sign in to your account:

--8<-- "shared/procedures/sign-in.md"

After signing in, you'll see the dashboard.
```

### Reference Table Reuse

Reference information appears in multiple places:

```markdown
<!-- shared/reference/error-codes.md -->
| Code | Meaning | Resolution |
|------|---------|------------|
| 401 | Unauthorized | Check API key |
| 403 | Forbidden | Verify permissions |
| 404 | Not Found | Check endpoint URL |
| 429 | Rate Limited | Reduce request frequency |
```

Include in troubleshooting, API reference, and error handling guides.

### Boilerplate Reuse

Standard content like legal notices or support information:

```markdown
<!-- shared/boilerplate/support.md -->
## Getting Help

- **Documentation**: [docs.example.com](https://docs.example.com)
- **Community Forum**: [community.example.com](https://community.example.com)
- **Support Email**: support@example.com
- **Status Page**: [status.example.com](https://status.example.com)
```

## Reuse Systems

### File-Based Reuse

Simple systems use file includes:

```
docs/
├── shared/
│   ├── procedures/
│   │   ├── sign-in.md
│   │   └── api-auth.md
│   ├── warnings/
│   │   ├── data-loss.md
│   │   └── rate-limits.md
│   └── reference/
│       └── error-codes.md
├── getting-started/
├── guides/
└── reference/
```

File includes work with static site generators like MkDocs, Hugo, and Jekyll.

### Component Libraries

Larger systems use component libraries:

- Documented components with usage guidelines
- Versioned for controlled updates
- Searchable for discoverability
- Preview-able before use

### Content Management Systems

Enterprise CCMS (Component Content Management Systems) provide:

- Granular content management
- Reuse tracking and reporting
- Workflow for updates
- Publishing to multiple outputs

Tools include Paligo, MadCap Flare, and Adobe FrameMaker.

## Managing Reuse

### Tracking Reuse

Know where reused content appears:

- Which documents include which components?
- What breaks if a component changes?
- Which components are most reused?

Tracking prevents unexpected consequences from changes.

### Updating Reused Content

When updating reusable content:

1. Understand all places content appears
2. Verify update works in all contexts
3. Review impact in different output formats
4. Test any conditional variations

### Versioning Reused Content

For significant changes:

- Consider versioning reusable components
- Allow documents to reference specific versions
- Manage migration to new versions

### Governance

Define rules for reusable content:

- Who can create reusable components?
- What approval is needed for changes?
- How are components documented?
- When should content be reusable vs. standalone?

## Reuse Challenges

### Over-Engineering

Too much reuse creates complexity:

- Difficulty understanding content flow
- Cognitive load tracking includes
- Maintenance burden of the reuse system itself

Reuse should simplify, not complicate.

### Context Mismatch

Content that does not quite fit:

> "Sign in to your account" (in a document about account management)
> "Sign in to your account" (in a document about API usage—awkward)

Sometimes separate versions are better than forced reuse.

### Inheritance Confusion

Deep reuse hierarchies become hard to follow:

```
page.md
└── includes procedure.md
    └── includes prerequisites.md
        └── includes note.md
```

Keep reuse shallow enough to understand.

### Update Coordination

Widespread reuse makes updates complex:

- Change affects many documents
- Different contexts have different needs
- Coordinating review across teams

Plan for coordination overhead.

## Reuse Best Practices

### Start Simple

- Begin with obvious, high-value reuse candidates
- Add complexity only as needed
- Prefer explicit includes over complex systems

### Document Reusable Components

- Explain what each component contains
- Document where it should be used
- Provide usage examples

### Review in Context

- Preview reused content in actual documents
- Check all variations before publishing
- Test all output formats

### Balance Effort and Benefit

- Not everything should be reusable
- Reuse infrastructure has costs
- Focus on high-value, stable content

## Summary

Content reuse reduces duplication and ensures consistency:

- **Transclusion** includes content from shared sources
- **Variables** manage single values used throughout
- **Conditional content** creates variations from one source
- **Modular design** makes content suitable for reuse
- **Governance** keeps reuse manageable

Done well, reuse improves efficiency and consistency. Done poorly, it creates complexity that outweighs benefits. Start simple, focus on high-value opportunities, and grow the system as needs justify.

---

**Next**: [Minimalist Writing](minimalist-writing.md) covers writing only what users need.
