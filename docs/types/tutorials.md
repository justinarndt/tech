---
title: Writing Tutorials
description: Learn how to create effective tutorials that teach users new skills through guided, hands-on learning experiences.
---

# Tutorials

Tutorials guide users through learning experiences. Unlike how-to guides that help users accomplish specific tasks, tutorials help users develop skills and understanding. They teach through doing, building knowledge progressively toward competence.

## Tutorial vs. How-To Guide

| Aspect | Tutorial | How-To Guide |
|--------|----------|--------------|
| **Goal** | Learning | Accomplishing |
| **Focus** | Building skills | Completing task |
| **Structure** | Progressive | Task-focused |
| **Audience** | Learners | Users with tasks |
| **Outcome** | Understanding | Completed work |

Both are valuable; they serve different needs.

## Tutorial Design Principles

### Learning-Oriented

Focus on what users will learn:

**Task-focused (how-to):**
> This guide shows you how to deploy an application.

**Learning-focused (tutorial):**
> In this tutorial, you'll learn how deployment works by
> deploying your first application step by step.

### Progressive Complexity

Build skills incrementally:

1. Start with simplest concepts
2. Add complexity gradually
3. Reinforce earlier learning
4. End with integrated understanding

### Hands-On Experience

Users learn by doing:

- Every concept includes practice
- Users follow along with real examples
- Each section produces tangible results
- Errors are learning opportunities

### Safe Environment

Create conditions for experimentation:

- Use sandbox or test data
- Make mistakes reversible
- Provide checkpoints
- Offer recovery paths

## Tutorial Structure

### Introduction

Set up the learning experience:

```markdown
# Building Your First API Integration

In this tutorial, you'll learn how to integrate with the
Acme API by building a simple application that retrieves
and displays user data.

## What You'll Learn

- How API authentication works
- Making API requests
- Handling responses and errors
- Displaying data in your application

## Prerequisites

Before starting, you should:
- Have basic JavaScript knowledge
- Have Node.js 18+ installed
- Have a text editor ready

## Time Required

About 30 minutes

## What You'll Build

A command-line application that fetches and displays your
Acme account information.
```

### Step-by-Step Content

Guide through each learning milestone:

```markdown
## Step 1: Set Up Your Project

First, let's create a new project and install dependencies.

### Create the Project Folder

```bash
mkdir acme-integration
cd acme-integration
npm init -y
```

### Install Dependencies

We'll use `node-fetch` to make HTTP requests:

```bash
npm install node-fetch
```

### Create Your Main File

Create a file called `index.js`:

```bash
touch index.js
```

**Checkpoint**: Your project folder should contain:
- `package.json`
- `package-lock.json`
- `node_modules/`
- `index.js` (empty)

## Step 2: Understand API Authentication

Before making API calls, you need to understand how
authentication works.

### How API Keys Work

API keys identify your application to the server. Think of
them like a password that proves you're authorized to access
the API.

When you make a request, you include your API key in the
headers. The server checks this key and either allows or
denies your request.

### Get Your API Key

1. Log in to your Acme account
2. Go to Settings > API Keys
3. Click "Create New Key"
4. Copy the key (you won't see it again!)

### Keep Keys Secure

Never put API keys directly in code that gets committed to
version control. Instead, use environment variables:

```bash
export ACME_API_KEY="your-key-here"
```

**Try it**: Set your API key as an environment variable now.
We'll use it in the next step.
```

### Explanations with Practice

Connect concepts to hands-on work:

```markdown
## Step 3: Make Your First API Request

Now let's write code to call the API.

### Understanding the Request

Every API request has:
- **URL**: Where to send the request
- **Method**: What type of request (GET, POST, etc.)
- **Headers**: Metadata including authentication
- **Body**: Data to send (for POST/PUT requests)

For our first request, we'll GET our account information:
- URL: `https://api.acme.com/v2/me`
- Method: GET
- Headers: Authorization with our API key

### Write the Code

Open `index.js` and add:

```javascript
// Import the fetch function
const fetch = require('node-fetch');

// Get API key from environment variable
const apiKey = process.env.ACME_API_KEY;

// Make the request
async function getMyAccount() {
  const response = await fetch('https://api.acme.com/v2/me', {
    method: 'GET',
    headers: {
      'Authorization': `Bearer ${apiKey}`
    }
  });

  const data = await response.json();
  console.log(data);
}

// Run the function
getMyAccount();
```

### Run Your Code

```bash
node index.js
```

You should see your account information printed:

```json
{
  "id": "usr_123abc",
  "email": "you@example.com",
  "name": "Your Name"
}
```

**Troubleshooting**:
- If you see "Unauthorized", check that your API key is set correctly
- If you see a network error, check your internet connection

**What you learned**: You made an authenticated API request and
received a JSON response. This is the foundation of all API integrations.
```

### Build Toward Completion

Each step builds on previous learning:

```markdown
## Step 4: Handle Errors Gracefully

Real applications need to handle errors. Let's improve our code.

### Why Error Handling Matters

APIs can fail for many reasons:
- Invalid credentials
- Network problems
- Rate limiting
- Server issues

Without error handling, your application crashes. With it,
your application can respond appropriately.

### Add Error Handling

Update your code:

```javascript
async function getMyAccount() {
  try {
    const response = await fetch('https://api.acme.com/v2/me', {
      method: 'GET',
      headers: {
        'Authorization': `Bearer ${apiKey}`
      }
    });

    // Check if request was successful
    if (!response.ok) {
      throw new Error(`API error: ${response.status}`);
    }

    const data = await response.json();
    console.log('Success:', data);

  } catch (error) {
    console.error('Error fetching account:', error.message);
  }
}
```

### Test Error Handling

Try running with an invalid API key:

```bash
ACME_API_KEY="invalid" node index.js
```

You should see:
```
Error fetching account: API error: 401
```

Instead of crashing, your application handles the error gracefully.
```

### Conclusion and Next Steps

Summarize learning and point forward:

```markdown
## Conclusion

Congratulations! You've built your first API integration.

### What You Learned

- How API authentication works with API keys
- Making GET requests with the fetch API
- Handling JSON responses
- Implementing error handling

### Your Complete Code

```javascript
const fetch = require('node-fetch');

const apiKey = process.env.ACME_API_KEY;

async function getMyAccount() {
  try {
    const response = await fetch('https://api.acme.com/v2/me', {
      method: 'GET',
      headers: {
        'Authorization': `Bearer ${apiKey}`
      }
    });

    if (!response.ok) {
      throw new Error(`API error: ${response.status}`);
    }

    const data = await response.json();
    console.log('Success:', data);

  } catch (error) {
    console.error('Error fetching account:', error.message);
  }
}

getMyAccount();
```

### Next Steps

Now that you understand the basics:

- [Tutorial: Creating and Updating Resources](creating-resources.md)
- [Tutorial: Building a Full Application](full-application.md)
- [API Reference Documentation](../api/reference.md)
```

## Tutorial Best Practices

### Provide Working Examples

Every code sample should work:

- Test all examples before publishing
- Use realistic but simple data
- Avoid dependencies on external state

### Offer Checkpoints

Help users verify progress:

```markdown
**Checkpoint**: At this point, your project should have:
- [ ] `package.json` with express dependency
- [ ] `index.js` with basic server code
- [ ] Server running on port 3000
```

### Anticipate Problems

Address common issues:

```markdown
**Common Problems**:

**Port already in use**: Another process is using port 3000.
Try changing to a different port or stop the other process.

**Module not found**: Run `npm install` to install dependencies.
```

### Use Realistic Scenarios

Connect to real use cases:

**Abstract:**
> Create a function that processes data.

**Realistic:**
> Create a function that formats user names for display,
> handling missing first or last names gracefully.

## Summary

Tutorials teach through guided practice:

- Focus on learning, not just task completion
- Build skills progressively
- Provide hands-on experience throughout
- Create safe environments for experimentation
- Include checkpoints and troubleshooting
- Connect to realistic scenarios

Effective tutorials transform beginners into competent users.

---

**Next**: [Getting Started Guides](getting-started.md) covers first-experience documentation.
