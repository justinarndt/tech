---
title: Writing Troubleshooting Guides
description: Learn how to create troubleshooting documentation that helps users diagnose and solve problems systematically.
---

# Troubleshooting Guides

Troubleshooting guides help users diagnose and solve problems. When something goes wrong, users need to quickly identify the issue and find a solution. Effective troubleshooting documentation reduces support burden and user frustration.

## Troubleshooting Document Types

### Symptom-Based Articles

Organized by what users experience:

```markdown
# Screen Goes Blank After Login

## Symptoms

After entering credentials and clicking Sign In, the screen
goes blank or shows a white page.

## Causes

This issue can occur due to:
- Browser cache conflicts
- JavaScript errors
- Network connectivity problems
- Account permission issues

## Solutions

Try these solutions in order:

### 1. Clear Browser Cache

1. Press Ctrl+Shift+Delete (Cmd+Shift+Delete on Mac)
2. Select "Cached images and files"
3. Click "Clear data"
4. Refresh the page and try signing in again

### 2. Try a Different Browser

If clearing cache doesn't help:
1. Try signing in using a different browser
2. If it works, the issue is browser-specific

### 3. Disable Browser Extensions

Extensions can interfere with the application:
1. Open browser in incognito/private mode
2. Try signing in
3. If it works, an extension is causing the issue

### 4. Check Network Connectivity

Verify you can reach our servers:
```bash
ping api.example.com
```

If ping fails, check your network connection or firewall settings.

## Still Not Working?

[Contact support](../support.md) with:
- Your browser and version
- Screenshot of any error messages
- Whether the issue occurs in incognito mode
```

### Error Code Reference

Organized by error codes:

```markdown
# Error Code Reference

## 400 Series - Client Errors

### E400: Bad Request

**Meaning**: The request format is invalid.

**Common causes**:
- Missing required fields
- Invalid field values
- Malformed JSON

**Solution**: Check your request against the API documentation.

### E401: Unauthorized

**Meaning**: Authentication failed.

**Common causes**:
- Missing API key
- Expired API key
- Invalid credentials

**Solution**: Verify your API key is correct and active.

### E403: Forbidden

**Meaning**: You don't have permission for this action.

**Common causes**:
- Insufficient account permissions
- API key lacks required scopes
- Resource belongs to different account

**Solution**: Check your account permissions or contact your administrator.

## 500 Series - Server Errors

### E500: Internal Server Error

**Meaning**: Something went wrong on our servers.

**What to do**:
1. Wait a few minutes and retry
2. Check [status page](https://status.example.com)
3. If persistent, contact support with the request ID
```

### Decision Tree Troubleshooting

Guide users through diagnostic questions:

```markdown
# Troubleshooting Connection Issues

Use this guide to diagnose connection problems.

## Start Here

**Can you load other websites?**

- **Yes** → [Check Application Status](#check-application-status)
- **No** → [Check Network Connection](#check-network-connection)

## Check Network Connection

1. Check your Wi-Fi or ethernet connection
2. Try restarting your router
3. Contact your network administrator if on corporate network

**Does your network work now?**

- **Yes** → [Check Application Status](#check-application-status)
- **No** → The issue is with your network, not our application

## Check Application Status

Visit our [status page](https://status.example.com).

**Are all systems operational?**

- **Yes** → [Check Firewall Settings](#check-firewall-settings)
- **No** → Wait for the issue to be resolved

## Check Firewall Settings

Our application requires access to:
- api.example.com (port 443)
- cdn.example.com (port 443)

**Can you access these addresses?**

```bash
curl https://api.example.com/health
```

- **Yes** → [Check Authentication](#check-authentication)
- **No** → Configure your firewall to allow these connections

## Check Authentication

Your credentials may have expired.

1. Try signing out and signing back in
2. Reset your password if sign-in fails
3. Check if your account is still active

**Resolved?**

- **Yes** → Done!
- **No** → [Contact support](../support.md)
```

## Writing Effective Troubleshooting Content

### Start with Symptoms

Begin with what users experience:

**Starting with cause:**
> # Database Connection Pool Exhausted

**Starting with symptom:**
> # Application Becomes Slow or Unresponsive

Users search for symptoms, not causes.

### Provide Context

Help users confirm they have the right issue:

```markdown
## Symptoms

You may be experiencing this issue if:
- The application takes more than 10 seconds to respond
- You see "Request timeout" errors
- Performance degrades over time but improves after restart
```

### Order Solutions by Likelihood

Put most common solutions first:

```markdown
## Solutions

### Most Likely: Clear Your Cache

80% of users resolve this by clearing their browser cache.

[steps]

### If That Didn't Work: Check Extensions

Browser extensions sometimes cause conflicts.

[steps]

### Rare: Corporate Firewall Issues

If you're on a corporate network with strict security...

[steps]
```

### Make Solutions Actionable

Provide specific steps, not vague guidance:

**Vague:**
> Check your network settings.

**Actionable:**
> 1. Open Network Settings
> 2. Click "Network Diagnostics"
> 3. Look for "DNS Configuration"
> 4. Verify DNS servers are responding

### Include Verification

Help users confirm the problem is solved:

```markdown
### Verify the Fix

After clearing your cache:
1. Close and reopen your browser
2. Navigate to the application
3. Sign in
4. Verify the page loads completely within 5 seconds
```

## Troubleshooting for Different Audiences

### End Users

- Use non-technical language
- Provide step-by-step instructions
- Include screenshots for UI steps
- Offer to escalate if self-service fails

### Administrators

- Include log file locations
- Provide diagnostic commands
- Document configuration options
- Explain underlying causes

### Developers

- Include API error details
- Provide code examples
- Reference technical documentation
- Document debugging approaches

## Diagnostic Information

### What to Collect

Guide users on gathering diagnostic info:

```markdown
## Before Contacting Support

Collect this information to help us resolve your issue faster:

### Basic Information
- Your username or account ID
- Browser and version (e.g., Chrome 120)
- Operating system (e.g., Windows 11)
- When the issue started

### Error Details
- Exact error message (screenshot if possible)
- Error codes displayed
- Request ID (shown in error messages)

### Steps to Reproduce
1. What were you trying to do?
2. What steps did you take?
3. What happened instead of expected result?

### System Information

Run this diagnostic and copy the output:
```bash
acme diagnostic --output
```
```

### Log Files

Tell users where to find logs:

```markdown
## Log File Locations

| Platform | Location |
|----------|----------|
| Windows | `%APPDATA%\Acme\logs\` |
| macOS | `~/Library/Logs/Acme/` |
| Linux | `~/.local/share/acme/logs/` |

### Relevant Log Files

- `app.log` - General application logs
- `error.log` - Errors and exceptions
- `network.log` - Network requests and responses

### Reading Logs

Look for entries around the time the error occurred:
```
2024-01-15 10:30:45 ERROR Connection failed: timeout after 30s
2024-01-15 10:30:45 DEBUG Retry attempt 1 of 3
```
```

## Organizing Troubleshooting Content

### By Symptom Category

```
troubleshooting/
├── index.md
├── installation-issues.md
├── login-problems.md
├── performance-issues.md
├── sync-errors.md
└── error-codes.md
```

### By User Task

```
troubleshooting/
├── index.md
├── cannot-sign-in.md
├── cannot-upload-files.md
├── cannot-generate-reports.md
└── cannot-invite-users.md
```

### Searchable Index

Create an index of common problems:

```markdown
# Troubleshooting Index

## Sign-In Issues
- [Cannot sign in](login-problems.md#cannot-sign-in)
- [Forgot password](login-problems.md#forgot-password)
- [Account locked](login-problems.md#account-locked)

## Performance
- [Slow loading](performance-issues.md#slow-loading)
- [Timeouts](performance-issues.md#timeouts)
- [Memory errors](performance-issues.md#memory-errors)

## Data
- [Missing data](sync-errors.md#missing-data)
- [Sync failures](sync-errors.md#sync-failures)
- [Export problems](sync-errors.md#export-problems)
```

## Maintenance

### Track Common Issues

Monitor support tickets to identify:
- Most frequent issues (need prominent documentation)
- Issues without documentation (need new articles)
- Documentation that doesn't resolve issues (needs improvement)

### Update for Product Changes

When products change:
- Verify existing troubleshooting still applies
- Update screenshots and steps
- Add troubleshooting for new features
- Remove troubleshooting for removed features

### Gather Feedback

Ask users if troubleshooting helped:
- "Did this solve your problem?"
- Track resolution rates
- Update based on feedback

## Summary

Troubleshooting guides help users solve problems independently:

- Organize by symptoms, what users actually experience
- Provide step-by-step solutions ordered by likelihood
- Include verification steps to confirm resolution
- Collect diagnostic information systematically
- Tailor detail level to audience
- Maintain based on support patterns

Good troubleshooting documentation reduces support costs and improves user satisfaction.

---

**Next**: [Standard Operating Procedures](standard-operating-procedures.md) covers process documentation.
