---
title: Writing Deprecation Notices
description: Learn how to communicate product deprecations and end-of-life effectively, giving users time and guidance to transition.
---

# Deprecation Notices

Deprecation notices communicate that features, APIs, or products are being phased out. Good deprecation communication gives users adequate warning, clear timelines, and migration paths. Poor communication damages trust and creates support burden.

## Deprecation Lifecycle

### Standard Timeline

```
Announcement → Deprecated → End of Life → Removed
     ↓              ↓            ↓           ↓
  6+ months     Warnings     Support ends   Gone
```

### Timeline Considerations

| Change Impact | Minimum Notice |
|---------------|----------------|
| Minor feature removal | 3 months |
| Major feature deprecation | 6 months |
| API version retirement | 12 months |
| Product end-of-life | 12-24 months |

## Deprecation Notice Content

### Essential Elements

```markdown
# Deprecation Notice: [Feature Name]

## Summary
- **What**: [Feature being deprecated]
- **When**: [Deprecation date and end-of-life date]
- **Why**: [Reason for deprecation]
- **Action**: [What users should do]

## Timeline

| Date | Event |
|------|-------|
| [Date] | Deprecation announced |
| [Date] | Feature deprecated (warnings begin) |
| [Date] | End of life (feature removed) |

## Migration Path

How to transition to the replacement.

## Support

What support is available during transition.
```

### Example Notice

```markdown
# Deprecation Notice: API Version 1

## Summary

API v1 is being deprecated in favor of API v2. v1 will be removed
on June 30, 2025.

**Action required**: Migrate your integrations to API v2 before
June 30, 2025 to avoid service disruption.

## Why We're Deprecating v1

API v2 provides:
- Better performance (3x faster response times)
- Improved error handling
- New features not available in v1
- Enhanced security

Maintaining both versions creates overhead that slows development
of new features for all users.

## Timeline

| Date | Event |
|------|-------|
| January 1, 2025 | Deprecation announced |
| March 1, 2025 | v1 deprecated (warnings added to responses) |
| May 1, 2025 | v1 rate limits reduced |
| June 30, 2025 | v1 removed (requests will fail) |

## What You Need to Do

### 1. Check If You're Affected

You're affected if you use any of these endpoints:
- `https://api.example.com/v1/*`

Check your application logs for requests to `/v1/` endpoints.

### 2. Plan Your Migration

Review the [v1 to v2 Migration Guide](../migration/v1-to-v2.md) and
estimate the effort required for your integration.

### 3. Migrate

Update your code to use v2 endpoints. The migration guide provides
step-by-step instructions.

### 4. Test

Verify your updated integration works correctly in a test
environment before deploying to production.

### 5. Deploy

Deploy your updated integration before June 30, 2025.

## What Happens If You Don't Migrate

After June 30, 2025:
- All v1 API requests will return 410 Gone errors
- Your integration will stop working
- No exceptions will be granted

## Migration Resources

- [v1 to v2 Migration Guide](../migration/v1-to-v2.md)
- [API v2 Documentation](../api/v2/reference.md)
- [Breaking Changes Summary](../migration/breaking-changes.md)

## Getting Help

- **Questions**: Post in our [community forum](https://community.example.com)
- **Issues**: File a [support ticket](https://support.example.com)
- **Enterprise customers**: Contact your account manager

## FAQ

### Can I get an extension?

No extensions will be granted. The timeline provides 6 months for
migration, which is sufficient for most integrations.

### Will v1 data be affected?

No. Your data is stored independently of the API version. Only
the API endpoints are changing.

### What if I find bugs in v2?

Report bugs through our [issue tracker](https://github.com/example/issues).
We'll prioritize fixes for migration-blocking issues.
```

## Communication Strategy

### Multiple Channels

Communicate deprecations through:

- **Documentation**: Deprecation notices in docs
- **API responses**: Warning headers on deprecated endpoints
- **Email**: Direct notification to affected users
- **In-app**: Warnings in the user interface
- **Blog/changelog**: Public announcements

### Warning Headers

Add headers to deprecated API responses:

```
Deprecation: Sun, 01 Mar 2025 00:00:00 GMT
Sunset: Mon, 30 Jun 2025 00:00:00 GMT
Link: <https://docs.example.com/migration>; rel="deprecation"
```

### Progressive Warnings

Increase urgency over time:

**6 months before**: "This API version will be deprecated."

**3 months before**: "This API version is deprecated. Migrate soon."

**1 month before**: "⚠️ This API version will stop working in 30 days."

**1 week before**: "🚨 URGENT: This API version stops working in 7 days."

## Writing Guidelines

### Be Clear About Impact

State exactly what will happen:

**Vague:**
> This feature may not be available in future versions.

**Clear:**
> This feature will stop working on June 30, 2025. After this date,
> requests to deprecated endpoints will return HTTP 410 errors.

### Explain the Reasoning

Help users understand why:

```markdown
## Why We're Making This Change

Maintaining multiple API versions requires significant resources
that could otherwise go toward new features. API v2 addresses
performance issues and security concerns present in v1.

We understand migrations require effort, and we've provided a
6-month window and comprehensive migration documentation to
support your transition.
```

### Provide Clear Alternatives

Always offer a path forward:

**No alternative:**
> The legacy export feature is deprecated.

**With alternative:**
> The legacy export feature is deprecated. Use the new Export API
> instead, which provides the same functionality with additional
> format options. [Migration guide](../migration/export.md)

### Show Empathy

Acknowledge the inconvenience:

```markdown
We know migrations take time and effort. We're committed to
making this transition as smooth as possible:

- Comprehensive migration documentation
- Extended support during the transition period
- Office hours for migration questions
- Priority support for migration-blocking issues
```

## Documentation Updates

### Mark Deprecated Content

Clearly label deprecated documentation:

```markdown
!!! warning "Deprecated"
    This API version is deprecated and will be removed on
    June 30, 2025. See the [migration guide](../migration/v1-to-v2.md)
    for upgrade instructions.
```

### Maintain Until Removal

Keep deprecated documentation available:

- Users need docs during migration
- Remove only after end-of-life date
- Archive for historical reference

### Update Related Docs

Update all affected documentation:

- Getting started guides
- Tutorials
- Reference documentation
- Code samples

## Summary

Effective deprecation notices:

- Announce with adequate lead time
- State clear timelines and dates
- Explain the reasoning
- Provide migration paths
- Communicate through multiple channels
- Show empathy for the disruption

Good deprecation communication maintains trust even while making necessary changes.

---

**Next**: [Architecture Documents](architecture-documents.md) covers technical design documentation.
