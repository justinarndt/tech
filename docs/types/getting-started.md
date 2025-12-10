---
title: Writing Getting Started Guides
description: Learn how to create effective getting started guides that help users achieve first success quickly with your product.
---

# Getting Started Guides

Getting started guides help new users achieve their first success with your product. They focus on the fastest path to value, cutting through complexity to deliver a meaningful win. A great getting started guide turns curious visitors into engaged users.

## Getting Started Purpose

Getting started guides:

- Provide the fastest path to first value
- Reduce time-to-productivity
- Build confidence in the product
- Create positive first impressions
- Reduce early churn

## Design Principles

### Speed to Value

Minimize time between starting and succeeding:

- Skip non-essential configuration
- Use smart defaults
- Defer complexity to later
- Focus on one clear outcome

### Achievable Scope

Set realistic goals users can complete:

**Too ambitious:**
> Build a complete application with authentication, database,
> and deployment in this guide.

**Achievable:**
> Create your first project and see live results in 5 minutes.

### Clear Success

Users should know when they have succeeded:

```markdown
## Verify It's Working

Open http://localhost:3000 in your browser. You should see:

![Welcome screen showing "Hello, World!"](../images/hello-world.png)

Congratulations! Your application is running.
```

## Getting Started Structure

### Overview Section

Set expectations immediately:

```markdown
# Getting Started

Get your first project running in under 5 minutes.

## What You'll Accomplish

By the end of this guide, you'll have:
- Created an Acme account
- Set up your first project
- Made your first API call

## Requirements

- A web browser
- 5 minutes
```

### Quick Path

Present the fastest route:

```markdown
## Quick Start

### 1. Create Your Account

[Sign up for free](https://app.example.com/signup) and verify your email.

### 2. Create a Project

1. Click **New Project**
2. Enter a project name
3. Click **Create**

### 3. Get Your API Key

1. Go to **Settings > API Keys**
2. Click **Create Key**
3. Copy your key

### 4. Make Your First Request

```bash
curl https://api.example.com/v2/me \
  -H "Authorization: Bearer YOUR_API_KEY"
```

You should see your account information:

```json
{
  "id": "usr_123",
  "email": "you@example.com"
}
```

That's it! You're ready to build.
```

### Next Steps

Guide users forward:

```markdown
## Next Steps

Now that you're set up:

- **[Tutorial: Build Your First Integration](../tutorials/first-integration.md)**
  Learn how API integration works by building a simple app.

- **[Core Concepts](../concepts/overview.md)**
  Understand the key concepts behind Acme.

- **[API Reference](../api/reference.md)**
  Explore all available API endpoints.
```

## Platform-Specific Quick Starts

### Multiple Platforms

Offer platform-specific paths:

```markdown
# Getting Started

Choose your platform:

<div class="feature-grid" markdown>

<div class="feature-card" markdown>
### JavaScript
Get started with Node.js or browser JavaScript.
[Start with JavaScript](javascript.md){ .md-button }
</div>

<div class="feature-card" markdown>
### Python
Get started with Python 3.8+.
[Start with Python](python.md){ .md-button }
</div>

<div class="feature-card" markdown>
### Ruby
Get started with Ruby 3.0+.
[Start with Ruby](ruby.md){ .md-button }
</div>

</div>
```

### SDK Quick Starts

Each platform has tailored instructions:

=== "JavaScript"

    ```bash
    npm install acme-sdk
    ```

    ```javascript
    import { Acme } from 'acme-sdk';

    const client = new Acme({ apiKey: 'YOUR_KEY' });
    const me = await client.users.me();
    console.log(me);
    ```

=== "Python"

    ```bash
    pip install acme-sdk
    ```

    ```python
    from acme import Client

    client = Client(api_key='YOUR_KEY')
    me = client.users.me()
    print(me)
    ```

=== "Ruby"

    ```bash
    gem install acme-sdk
    ```

    ```ruby
    require 'acme'

    client = Acme::Client.new(api_key: 'YOUR_KEY')
    me = client.users.me
    puts me
    ```

## Writing Guidelines

### Cut Ruthlessly

Remove everything non-essential:

**Too much setup:**
> First, let's configure your development environment. You'll need
> to install the SDK, configure your IDE, set up linting, and...

**Minimal setup:**
> Install the SDK:
> ```bash
> npm install acme-sdk
> ```

### Use Defaults

Skip configuration that can wait:

**Configuring everything:**
> Before creating your project, you need to configure region,
> language settings, timezone, notification preferences...

**Using defaults:**
> Create your project with default settings. You can customize
> these later in Settings.

### Show, Don't Tell

Demonstrate rather than explain:

**Explaining:**
> The API returns JSON data containing user information including
> the user's ID, email address, and other profile fields.

**Showing:**
> ```json
> {
>   "id": "usr_123",
>   "email": "you@example.com",
>   "name": "Your Name"
> }
> ```

### Make It Copy-Paste Ready

Code should work immediately:

```markdown
Run this command (replace YOUR_API_KEY with your actual key):

```bash
curl https://api.example.com/v2/me \
  -H "Authorization: Bearer YOUR_API_KEY"
```
```

## Handling Prerequisites

### Minimal Prerequisites

Keep requirements minimal:

**Ideal:** "A web browser"
**Acceptable:** "Node.js 18+ installed"
**Problematic:** "Docker, Kubernetes, and Terraform configured"

### Clear Prerequisites

State requirements clearly:

```markdown
## Before You Begin

You'll need:
- [ ] Node.js 18 or later ([download](https://nodejs.org))
- [ ] A text editor
- [ ] Terminal access

Don't have Node.js? [Use our web playground instead](../playground.md)
```

### Handle Missing Prerequisites

Provide alternatives:

```markdown
**Don't have Python installed?**
- [Install Python](https://python.org/downloads)
- Or try our [interactive tutorial](../playground.md) that runs
  in your browser
```

## Common Patterns

### Hello World

The simplest possible example:

```markdown
## Hello World

Create `hello.py`:

```python
from acme import Client

client = Client()
print(client.hello())
```

Run it:

```bash
python hello.py
```

Output:
```
Hello from Acme!
```
```

### First Real Result

Beyond hello world, something meaningful:

```markdown
## Your First Project

Let's create something real: a project that tracks tasks.

1. Create the project:
   ```bash
   acme project create "My Tasks"
   ```

2. Add a task:
   ```bash
   acme task add "Learn Acme"
   ```

3. View your tasks:
   ```bash
   acme task list
   ```

   Output:
   ```
   ☐ Learn Acme
   ```

You've created your first project with real data!
```

## Measuring Success

### Time to First Value

Measure how long users take:

- Time from signup to first success
- Completion rates for getting started
- Drop-off points in the flow

### User Feedback

Gather feedback on the experience:

- Was anything confusing?
- What was missing?
- How long did it take?

### Iterate

Improve based on data:

- Remove steps that cause drop-off
- Clarify confusing instructions
- Update for product changes

## Summary

Getting started guides create first success:

- Minimize time to value
- Focus on achievable outcomes
- Cut everything non-essential
- Show working examples
- Provide clear success criteria
- Guide to next steps

A great getting started experience builds confidence and engagement that carries through the user's entire journey with your product.

---

**Next**: [Migration Guides](migration-guides.md) covers transition documentation.
