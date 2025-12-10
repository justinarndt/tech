---
title: API Documentation
description: Best practices for documenting REST, GraphQL, and other APIs.
---

# API Documentation

API documentation enables developers to integrate with your service. Clear, accurate API docs reduce support burden and accelerate adoption.

## API Documentation Components

### Overview

Introduce your API:

- What the API does
- Authentication method
- Base URL
- Rate limits
- Versioning approach

### Authentication

Explain how to authenticate:

```markdown
# Authentication

All API requests require an API key in the header:

Authorization: Bearer YOUR_API_KEY

Get your API key from the [dashboard](/dashboard).
```

### Endpoints

Document each endpoint completely:

```markdown
## Create User

Creates a new user account.

POST /v1/users

### Request Body

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| email | string | Yes | User's email address |
| name | string | Yes | User's display name |
| role | string | No | User role. Default: "member" |

### Response

Returns the created user object.

{
  "id": "usr_123",
  "email": "user@example.com",
  "name": "Jane Doe",
  "role": "member",
  "created_at": "2024-01-15T10:30:00Z"
}

### Errors

| Status | Code | Description |
|--------|------|-------------|
| 400 | invalid_email | Email format is invalid |
| 409 | email_exists | Email already registered |
```

### Error Reference

Document all possible errors:

```markdown
# Errors

The API returns standard HTTP status codes.

## Error Response Format

{
  "error": {
    "code": "error_code",
    "message": "Human-readable description",
    "details": {}
  }
}

## Common Error Codes

| Code | Status | Description |
|------|--------|-------------|
| unauthorized | 401 | Invalid or missing API key |
| forbidden | 403 | Insufficient permissions |
| not_found | 404 | Resource doesn't exist |
| rate_limited | 429 | Too many requests |
```

## REST API Documentation

### Endpoint Structure

Follow consistent patterns:

```
GET    /resources        List resources
POST   /resources        Create resource
GET    /resources/{id}   Get single resource
PUT    /resources/{id}   Update resource
DELETE /resources/{id}   Delete resource
```

### Request Documentation

Include all details:

- HTTP method
- URL with path parameters
- Query parameters
- Request headers
- Request body schema
- Example request

### Response Documentation

Specify:

- Status codes
- Response body schema
- Example responses
- Pagination details

## GraphQL Documentation

### Schema Documentation

Document types and fields:

```graphql
"""
A user account in the system.
"""
type User {
  """
  Unique identifier for the user.
  """
  id: ID!

  """
  User's email address. Must be unique.
  """
  email: String!

  """
  User's display name.
  """
  name: String!
}
```

### Query Documentation

```markdown
## users Query

Retrieves a paginated list of users.

query {
  users(first: 10, after: "cursor") {
    edges {
      node {
        id
        email
        name
      }
    }
    pageInfo {
      hasNextPage
      endCursor
    }
  }
}
```

## API Documentation Tools

### OpenAPI (Swagger)

Industry standard for REST APIs:

```yaml
openapi: 3.0.0
info:
  title: My API
  version: 1.0.0
paths:
  /users:
    post:
      summary: Create user
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateUser'
      responses:
        '201':
          description: User created
```

### Documentation Generators

- **Swagger UI**: Interactive API explorer
- **Redoc**: Clean reference documentation
- **Stoplight**: Full documentation platform
- **ReadMe**: Developer hub with analytics

## Interactive Documentation

### Try It Features

Let developers test endpoints:

- Pre-filled examples
- Authentication helper
- Response preview
- Code generation

### Code Samples

Provide examples in popular languages:

```markdown
=== "cURL"

    curl -X POST https://api.example.com/v1/users \
      -H "Authorization: Bearer $API_KEY" \
      -H "Content-Type: application/json" \
      -d '{"email": "user@example.com", "name": "Jane"}'

=== "Python"

    import requests

    response = requests.post(
        "https://api.example.com/v1/users",
        headers={"Authorization": f"Bearer {api_key}"},
        json={"email": "user@example.com", "name": "Jane"}
    )

=== "JavaScript"

    const response = await fetch('https://api.example.com/v1/users', {
      method: 'POST',
      headers: {
        'Authorization': `Bearer ${apiKey}`,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({ email: 'user@example.com', name: 'Jane' })
    });
```

## Maintaining API Docs

### Versioning

- Document all supported versions
- Highlight differences between versions
- Provide migration guides
- Mark deprecated endpoints

### Changelog

Track all changes:

```markdown
# Changelog

## 2024-01-15
- Added `role` field to User object
- Deprecated `type` field (use `role` instead)

## 2024-01-01
- Increased rate limit to 1000 req/min
- Added pagination to list endpoints
```

## Summary

Effective API documentation:

- Documents every endpoint completely
- Provides working code examples
- Explains errors clearly
- Offers interactive testing
- Stays synchronized with the API

Good API docs are often the deciding factor when developers choose between competing services.
