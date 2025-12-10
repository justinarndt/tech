---
title: API Documentation Best Practices
description: Learn how to create excellent API documentation that helps developers integrate successfully, covering reference docs, guides, and developer experience.
---

# API Documentation

API documentation helps developers integrate with your services. It is often the primary interface between your product and technical users. Good API docs accelerate adoption; poor API docs drive developers to competitors.

## Why API Docs Matter

Developers evaluate APIs partly through documentation:

- Can they understand what the API does?
- Can they get started quickly?
- Can they find answers to their questions?
- Can they trust the documentation is accurate?

API documentation directly affects developer adoption and satisfaction.

## Types of API Documentation

### Reference Documentation

Complete technical specification of the API:

- Endpoints and methods
- Request and response formats
- Parameters and data types
- Authentication
- Error codes

Reference docs answer: "What exactly does this endpoint do?"

### Guides and Tutorials

Conceptual and task-oriented content:

- Getting started
- Authentication setup
- Common workflows
- Best practices

Guides answer: "How do I accomplish this goal?"

### Code Examples

Working code developers can use:

- Request examples in multiple languages
- Full workflow examples
- SDK usage examples
- Copy-paste ready snippets

Examples answer: "What does the code look like?"

## Reference Documentation Structure

### Endpoint Documentation

Each endpoint needs complete documentation:

```markdown
## Create User

Create a new user account.

### Endpoint

```
POST /api/v2/users
```

### Authentication

Requires API key with `users:write` scope.

### Request Body

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| email | string | Yes | User's email address |
| name | string | Yes | User's display name |
| role | string | No | User role. Default: "viewer" |

### Example Request

```bash
curl -X POST https://api.example.com/v2/users \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "name": "Jane Smith",
    "role": "editor"
  }'
```

### Response

Returns the created user object.

```json
{
  "id": "usr_123abc",
  "email": "user@example.com",
  "name": "Jane Smith",
  "role": "editor",
  "created_at": "2024-01-15T10:30:00Z"
}
```

### Error Responses

| Status | Code | Description |
|--------|------|-------------|
| 400 | invalid_email | Email format is invalid |
| 409 | email_exists | Email already registered |
| 403 | insufficient_permissions | API key lacks required scope |
```

### Authentication Documentation

Explain how to authenticate:

```markdown
## Authentication

All API requests require authentication using an API key.

### Getting an API Key

1. Log in to your account
2. Go to **Settings > API Keys**
3. Click **Create New Key**
4. Select the required scopes
5. Copy the key (it won't be shown again)

### Using Your API Key

Include the key in the Authorization header:

```bash
curl https://api.example.com/v2/users \
  -H "Authorization: Bearer YOUR_API_KEY"
```

### API Key Scopes

| Scope | Description |
|-------|-------------|
| `read` | Read-only access to resources |
| `users:write` | Create and modify users |
| `admin` | Full administrative access |

### Security Best Practices

- Never commit API keys to version control
- Use environment variables for key storage
- Rotate keys regularly
- Use minimum required scopes
```

### Error Documentation

Document error handling:

```markdown
## Errors

The API uses standard HTTP status codes and returns detailed error objects.

### Error Response Format

```json
{
  "error": {
    "code": "invalid_request",
    "message": "The request body is missing required field: email",
    "details": {
      "field": "email",
      "reason": "required"
    }
  }
}
```

### Common Error Codes

| HTTP Status | Error Code | Description |
|-------------|------------|-------------|
| 400 | invalid_request | Request validation failed |
| 401 | unauthorized | Invalid or missing API key |
| 403 | forbidden | Valid key but insufficient permissions |
| 404 | not_found | Resource does not exist |
| 429 | rate_limited | Too many requests |
| 500 | internal_error | Server error (contact support) |

### Rate Limiting

API requests are limited to 100 requests per minute per API key.

When rate limited, responses include:

```
HTTP/1.1 429 Too Many Requests
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 0
X-RateLimit-Reset: 1642089600
```

Wait until the reset timestamp before retrying.
```

## Getting Started Content

### Quick Start Guide

Get developers to first successful request:

```markdown
## Quick Start

Make your first API call in under 5 minutes.

### 1. Get Your API Key

[Create an API key](#getting-an-api-key) in your account settings.

### 2. Make Your First Request

```bash
curl https://api.example.com/v2/me \
  -H "Authorization: Bearer YOUR_API_KEY"
```

### 3. View the Response

```json
{
  "id": "usr_123abc",
  "email": "you@example.com",
  "name": "Your Name"
}
```

Congratulations! You've made your first API call.

### Next Steps

- [Create a user](./users/create.md)
- [List all users](./users/list.md)
- [Explore webhooks](./webhooks/overview.md)
```

### SDK Quick Starts

Provide language-specific getting started:

=== "Python"

    ```python
    from acme import Client

    client = Client(api_key="YOUR_API_KEY")

    # Get current user
    me = client.users.me()
    print(f"Logged in as {me.name}")
    ```

=== "JavaScript"

    ```javascript
    import { AcmeClient } from '@acme/sdk';

    const client = new AcmeClient({ apiKey: 'YOUR_API_KEY' });

    // Get current user
    const me = await client.users.me();
    console.log(`Logged in as ${me.name}`);
    ```

=== "Go"

    ```go
    client := acme.NewClient("YOUR_API_KEY")

    // Get current user
    me, err := client.Users.Me(ctx)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Printf("Logged in as %s\n", me.Name)
    ```

## Code Examples

### Example Quality

Good examples are:

- **Complete**: Can be copied and run
- **Realistic**: Show actual use cases
- **Correct**: Tested and working
- **Commented**: Explain non-obvious parts

### Example Types

**Basic examples** show single operations:

```python
# Create a user
user = client.users.create(
    email="user@example.com",
    name="Jane Smith"
)
```

**Complete examples** show full workflows:

```python
# Complete user onboarding workflow
import acme

client = acme.Client(api_key=os.environ["ACME_API_KEY"])

# Create the user
user = client.users.create(
    email="user@example.com",
    name="Jane Smith",
    role="editor"
)

# Add to a team
client.teams.add_member(
    team_id="team_456",
    user_id=user.id
)

# Send welcome email
client.emails.send(
    template="welcome",
    to=user.email,
    data={"name": user.name}
)

print(f"Created user {user.id} and added to team")
```

## Interactive Documentation

### API Explorers

Allow developers to try requests:

- Pre-filled with their API key
- Editable request parameters
- Live responses
- Copy-ready curl commands

Tools: Swagger UI, Redoc, ReadMe

### Code Generation

Generate code from examples:

- Select endpoint
- Configure parameters
- Get code in preferred language

## OpenAPI Specification

### Specification-Driven Docs

Use OpenAPI (Swagger) as documentation source:

```yaml
openapi: 3.0.0
info:
  title: Acme API
  version: 2.0.0
paths:
  /users:
    post:
      summary: Create a user
      description: Creates a new user account
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateUserRequest'
      responses:
        '201':
          description: User created
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/User'
```

### Benefits

- Single source of truth
- Generated documentation
- Generated client libraries
- Request validation
- Testing support

## Maintenance

### Version Documentation

Document API versions clearly:

- Current version
- Deprecated versions
- Breaking changes
- Migration guides

### Change Documentation

Communicate changes effectively:

- Changelog for all changes
- Migration guides for breaking changes
- Advance notice for deprecations
- Clear timelines

### Accuracy Verification

Keep docs accurate:

- Automated testing against examples
- CI/CD integration
- Regular review cycles
- User feedback integration

## Developer Experience

### Discoverability

Help developers find information:

- Clear navigation
- Effective search
- Related content links
- Index of endpoints

### Consistency

Maintain consistent patterns:

- Same structure for all endpoints
- Consistent terminology
- Predictable locations

### Completeness

Cover everything developers need:

- All endpoints documented
- All parameters explained
- All errors listed
- All edge cases addressed

## Summary

API documentation determines developer success with your platform:

- **Reference docs** provide complete technical specification
- **Guides** explain concepts and workflows
- **Examples** show working code
- **Interactive tools** let developers experiment

Invest in API documentation as a critical part of developer experience.

---

**Next**: [Release Notes](release-notes.md) covers documenting product changes.
