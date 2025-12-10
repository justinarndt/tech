---
title: Writing Effective Release Notes
description: Learn how to write release notes that inform users about changes, highlight new features, and guide migration from previous versions.
---

# Release Notes

Release notes document changes between product versions. They inform users about new features, improvements, bug fixes, and breaking changes—helping users understand what changed and what actions they may need to take.

## Purpose of Release Notes

Release notes serve multiple purposes:

- **Inform** users about what changed
- **Highlight** valuable new capabilities
- **Warn** about breaking changes or deprecations
- **Guide** users through required updates
- **Build trust** through transparency

Good release notes improve user experience and reduce support burden.

## Release Note Components

### Version and Date

Clearly identify what release these notes cover:

```markdown
# Release Notes

## Version 3.2.0 - January 15, 2025
```

Use consistent versioning (semantic versioning is common for software).

### Summary

Start with a brief overview:

```markdown
This release adds real-time collaboration features, improves
performance for large datasets, and fixes several reported issues.
```

Highlight the most important changes upfront.

### Categories

Organize changes by type:

**New Features**: New capabilities

**Improvements**: Enhancements to existing features

**Bug Fixes**: Resolved issues

**Breaking Changes**: Changes requiring user action

**Deprecations**: Features being phased out

**Security**: Security-related fixes

### Change Entries

Document each change clearly:

```markdown
### New Features

- **Real-time collaboration**: Multiple users can now edit
  documents simultaneously. Changes appear instantly for all
  collaborators. [Learn more](../guides/collaboration.md)

- **Bulk export**: Export multiple reports at once using the
  new bulk export option in the Reports menu.

### Improvements

- **Performance**: Dashboard loading time reduced by 40% for
  accounts with more than 10,000 records.

- **Search**: Search results now include snippets showing
  where the search term appears.

### Bug Fixes

- Fixed an issue where scheduled reports would not send if
  the scheduled time fell during a maintenance window.

- Resolved a display problem causing charts to render
  incorrectly in Safari 17.

### Breaking Changes

- **API v1 retired**: API version 1 is no longer available.
  Migrate to API v2 before upgrading.
  [Migration guide](../api/migration-v1-to-v2.md)
```

## Writing Guidelines

### Be Specific

Vague descriptions do not help users:

**Vague:**
> Improved performance.

**Specific:**
> Dashboard loading time reduced by 40% for accounts with more than 10,000 records.

**Vague:**
> Fixed bugs.

**Specific:**
> Fixed an issue where CSV exports would fail for reports containing special characters in column names.

### Focus on User Impact

Explain what the change means for users:

**Technical:**
> Implemented WebSocket connections for data synchronization.

**User-focused:**
> Real-time collaboration: Changes made by team members now appear instantly without page refresh.

### Include Actions Required

When users need to do something:

```markdown
### Breaking Changes

- **Minimum Node.js version**: This release requires Node.js 18
  or later. Update your Node.js installation before upgrading.

  To check your version:
  ```bash
  node --version
  ```

  [Node.js upgrade guide](https://nodejs.org)
```

### Link to Documentation

Connect to detailed information:

```markdown
- **New API endpoints for webhooks**: Create, update, and delete
  webhooks programmatically. [API documentation](../api/webhooks.md)
```

## Release Note Formats

### Chronological

List releases newest first:

```markdown
## Version 3.2.0 - January 15, 2025
[changes]

## Version 3.1.2 - January 8, 2025
[changes]

## Version 3.1.1 - December 20, 2024
[changes]
```

Good for: Users tracking ongoing changes

### Single Release

One page per release:

```markdown
# Version 3.2.0 Release Notes

Released: January 15, 2025

[comprehensive changes for this version]
```

Good for: Major releases with extensive changes

### Keep a Changelog

Following the [Keep a Changelog](https://keepachangelog.com/) format:

```markdown
# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [3.2.0] - 2025-01-15

### Added
- Real-time collaboration for documents
- Bulk export for reports

### Changed
- Dashboard performance improved by 40%

### Fixed
- Scheduled reports during maintenance windows
- Safari 17 chart rendering

### Removed
- API version 1 (deprecated in 2.5.0)
```

Good for: Open source projects and developer-focused products

## Breaking Changes

Breaking changes require special attention.

### Clear Identification

Make breaking changes impossible to miss:

```markdown
## ⚠️ Breaking Changes

### API v1 Retirement

API version 1 is no longer available as of this release.

**Action required**: Update your integrations to use API v2
before upgrading.

**Migration guide**: [Migrating from API v1 to v2](../api/migration.md)

**Timeline**:
- v1 deprecated: Version 2.5 (June 2024)
- v1 removed: This release (January 2025)
```

### Migration Guidance

Provide clear migration steps:

```markdown
### Database Schema Changes

This release includes database schema changes that require migration.

**Before upgrading:**

1. Back up your database
2. Run the migration script:
   ```bash
   ./migrate.sh --to-version 3.2
   ```
3. Verify migration completed:
   ```bash
   ./migrate.sh --verify
   ```

**Rollback instructions**: If issues occur, see
[Rollback procedures](../admin/rollback.md)
```

## Audience Considerations

### Different Audiences

Different users need different information:

**End users**: New features, UI changes, bug fixes affecting them

**Administrators**: Configuration changes, security updates, maintenance requirements

**Developers**: API changes, SDK updates, breaking changes

Consider separate sections or documents for different audiences.

### Technical Level

Match technical depth to audience:

**For general users:**
> You can now edit documents together with your team in real time.

**For developers:**
> WebSocket connections replace polling for real-time updates.
> Connections use the `/ws` endpoint with JWT authentication.

## Timing and Distribution

### Release Timing

Publish release notes:

- Before releases (for breaking changes)
- At release time (for all changes)
- After releases (for detailed analysis)

### Distribution Channels

Distribute release notes through:

- Documentation site
- In-app notifications
- Email newsletters
- Blog posts (for major releases)
- Social media (highlights)

### Notification Strategies

For breaking changes:

1. Announce in advance (30-90 days for major changes)
2. Include in multiple release notes leading up to change
3. Email affected users directly
4. Display in-app warnings

## Maintaining Release Notes

### Writing Process

Integrate with development:

1. Developers write change descriptions with code changes
2. Technical writer compiles and edits for release
3. Product manager reviews for accuracy and messaging
4. Publish with release

### Automated Generation

Generate from commit history or tickets:

```bash
# Generate changelog from git commits
git log --oneline v3.1.0..v3.2.0 > changelog-draft.txt
```

Automation provides raw material; human editing adds clarity and context.

### Version History

Maintain accessible history:

- Archive old release notes
- Keep searchable
- Link from current docs

Users on older versions need access to relevant notes.

## Summary

Release notes communicate product changes to users:

- Document all notable changes by category
- Be specific about what changed and why it matters
- Highlight breaking changes prominently
- Provide migration guidance when needed
- Match content to audience needs
- Distribute through appropriate channels

Good release notes build trust through transparency and help users benefit from product improvements.

---

**Next**: [Knowledge Base Articles](knowledge-base.md) covers self-service support content.
