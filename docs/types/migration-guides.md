---
title: Writing Migration Guides
description: Learn how to create migration guides that help users transition between product versions, platforms, or systems safely and successfully.
---

# Migration Guides

Migration guides help users transition from one state to another—between product versions, from competitors, or across platforms. They must be clear, complete, and cautious, as migrations often involve risk to user data and workflows.

## Migration Types

### Version Migrations

Upgrading between product versions:

- Major version upgrades (v1 to v2)
- Breaking change migrations
- Deprecation transitions

### Platform Migrations

Moving between platforms:

- From competitor products
- Between deployment methods
- Across infrastructure providers

### Data Migrations

Moving data between systems:

- Database schema changes
- Format conversions
- System integrations

## Migration Guide Structure

### Standard Format

```markdown
# Migrating from [Source] to [Target]

## Overview

Brief description of the migration and why users should do it.

## Before You Begin

### Prerequisites
What users need before starting

### Backup
How to protect existing data

### Time Estimate
How long the migration takes

## Breaking Changes

What will no longer work after migration

## Migration Steps

Step-by-step instructions

## Verification

How to confirm migration succeeded

## Rollback

How to undo the migration if needed

## Troubleshooting

Common problems and solutions

## Getting Help

Where to get support
```

### Example Migration Guide

```markdown
# Migrating from API v1 to v2

## Overview

API v2 introduces improved performance, better error handling,
and new features. v1 will be deprecated on June 30, 2025.

This guide walks you through updating your integration from v1 to v2.

**Estimated time**: 1-2 hours depending on integration complexity

## Before You Begin

### Prerequisites

- Access to your application's source code
- Ability to deploy changes
- Test environment for validation

### Backup Your Configuration

Save your current API configuration:

```bash
# Export current settings
curl https://api.example.com/v1/settings \
  -H "Authorization: Bearer YOUR_KEY" \
  > v1-settings-backup.json
```

### Timeline

| Milestone | Date |
|-----------|------|
| v2 available | January 1, 2025 |
| v1 deprecated | March 1, 2025 |
| v1 removed | June 30, 2025 |

## Breaking Changes

### Authentication

| v1 | v2 |
|----|-----|
| API key in query string | API key in header |
| `?api_key=xxx` | `Authorization: Bearer xxx` |

### Endpoints

| v1 Endpoint | v2 Endpoint |
|-------------|-------------|
| `/v1/users` | `/v2/users` |
| `/v1/account` | `/v2/me` |
| `/v1/items/list` | `/v2/items` |

### Response Format

Error responses changed:

**v1:**
```json
{"error": "Not found"}
```

**v2:**
```json
{
  "error": {
    "code": "not_found",
    "message": "Resource not found"
  }
}
```

## Migration Steps

### Step 1: Update Base URL

Change your API base URL:

```diff
- const BASE_URL = 'https://api.example.com/v1';
+ const BASE_URL = 'https://api.example.com/v2';
```

### Step 2: Update Authentication

Move API key from query string to header:

```diff
- const response = await fetch(`${BASE_URL}/users?api_key=${apiKey}`);
+ const response = await fetch(`${BASE_URL}/users`, {
+   headers: { 'Authorization': `Bearer ${apiKey}` }
+ });
```

### Step 3: Update Endpoint Paths

Update any renamed endpoints:

```diff
- const accountUrl = `${BASE_URL}/account`;
+ const accountUrl = `${BASE_URL}/me`;
```

### Step 4: Update Error Handling

Adjust error parsing for new format:

```diff
  if (!response.ok) {
-   const error = await response.json();
-   throw new Error(error.error);
+   const { error } = await response.json();
+   throw new Error(`${error.code}: ${error.message}`);
  }
```

### Step 5: Test Your Changes

Run your test suite and verify:
- Authentication works
- All endpoints return expected data
- Error handling works correctly

## Verification

After migration, verify everything works:

### Quick Check

```bash
curl https://api.example.com/v2/me \
  -H "Authorization: Bearer YOUR_KEY"
```

Expected: Your account information (not an error)

### Full Verification Checklist

- [ ] Authentication succeeds
- [ ] User endpoints work
- [ ] Item endpoints work
- [ ] Error responses parse correctly
- [ ] Webhooks receive data (if using)
- [ ] Rate limiting headers present

## Rollback

If you need to revert to v1:

1. Restore your v1 code from version control
2. Deploy the previous version
3. Verify v1 functionality works

Note: v1 will continue working until June 30, 2025.

## Troubleshooting

### "Unauthorized" errors after migration

**Cause**: Authentication header format incorrect

**Solution**: Verify header format:
```
Authorization: Bearer YOUR_KEY
```
(Not `Authorization: YOUR_KEY` or `Bearer: YOUR_KEY`)

### Endpoints returning 404

**Cause**: Endpoint path changed in v2

**Solution**: Check the endpoint mapping table above and update paths

### Different response structure

**Cause**: Response format changed in v2

**Solution**: Update your code to handle the new structure

## Getting Help

- [API v2 Reference Documentation](../api/v2/reference.md)
- [Community Forum](https://community.example.com)
- [Support](mailto:support@example.com)
```

## Writing Migration Guides

### Emphasize Safety

Prioritize data protection:

```markdown
## Before You Begin

### ⚠️ Back Up Your Data

**Critical**: Create a full backup before migrating. Migration
cannot be undone without a backup.

```bash
# Create full backup
pg_dump mydb > backup-$(date +%Y%m%d).sql
```

Verify your backup is complete before proceeding.
```

### Be Explicit About Breaking Changes

Clearly state what will break:

```markdown
## Breaking Changes

### ❌ These Will Stop Working

1. **API Key in URL**: Query string authentication is removed
2. **XML Responses**: Only JSON is supported in v2
3. **Legacy Endpoints**: `/v1/legacy/*` endpoints are removed

### ⚠️ These Changed

1. **Error Format**: Error responses have new structure
2. **Pagination**: Now uses cursor-based pagination
3. **Rate Limits**: Reduced from 1000 to 100 requests/minute
```

### Provide Complete Before/After

Show exactly what changes:

```markdown
## Authentication Changes

### Before (v1)

```python
import requests

response = requests.get(
    'https://api.example.com/v1/users',
    params={'api_key': 'YOUR_KEY'}
)
```

### After (v2)

```python
import requests

response = requests.get(
    'https://api.example.com/v2/users',
    headers={'Authorization': 'Bearer YOUR_KEY'}
)
```
```

### Include Verification Steps

Help users confirm success:

```markdown
## Verify the Migration

Run these checks to confirm migration succeeded:

### 1. Basic Connectivity

```bash
curl -I https://api.example.com/v2/health
```

Expected: `HTTP/2 200`

### 2. Authentication

```bash
curl https://api.example.com/v2/me \
  -H "Authorization: Bearer YOUR_KEY"
```

Expected: Your account information

### 3. Feature Check

Test each feature your application uses:

- [ ] List users
- [ ] Create users
- [ ] Update users
- [ ] Delete users
- [ ] Webhooks (if using)
```

### Always Include Rollback

Users need escape routes:

```markdown
## Rollback Procedure

If migration fails, revert to the previous version:

### 1. Stop the New Version

```bash
kubectl rollout undo deployment/myapp
```

### 2. Restore Database (if needed)

```bash
psql mydb < backup-20250115.sql
```

### 3. Verify Rollback

Confirm the old version works correctly before proceeding.

### 4. Report Issues

If you rolled back due to a bug, please report it:
[Submit Issue](https://github.com/example/issues)
```

## Summary

Migration guides help users transition safely:

- Document all breaking changes clearly
- Provide complete before/after examples
- Prioritize backup and safety
- Include verification steps
- Always provide rollback instructions
- Anticipate common problems

Good migration guides reduce risk and build trust.

---

**Next**: [Deprecation Notices](deprecation-notices.md) covers end-of-life documentation.
