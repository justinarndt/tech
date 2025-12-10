---
title: UX Writing
description: Writing effective interface copy and microcopy for software products.
---

# UX Writing

UX writing creates the words users see in software interfaces. Every button, error message, and tooltip shapes the user experience. Good UX writing guides users, reduces confusion, and builds trust.

## What UX Writers Do

### Interface Copy

Words throughout the product:

- Button labels
- Navigation items
- Form labels and hints
- Empty states
- Loading messages

### Microcopy

Small but critical text:

- Error messages
- Success confirmations
- Tooltips
- Placeholder text
- Helper text

### Content Strategy

Planning content across the product:

- Voice and tone guidelines
- Content patterns
- Terminology standards
- Writing documentation

## UX Writing Principles

### Clarity Over Cleverness

Users need to understand immediately:

| Clever | Clear |
|--------|-------|
| Oops! Something went sideways | Your file couldn't be saved |
| Let's get this party started | Create your account |
| Boom! You're in | Sign-in successful |

### Concise and Scannable

Users scan, they don't read:

```markdown
# Too Long
Please click the button below to submit your form and
complete the registration process for your new account.

# Better
Click Submit to create your account.

# Best
[Submit]  (button)
```

### Action-Oriented

Tell users what to do:

```markdown
# Passive
The form can be submitted by clicking the button.

# Active
Click Submit to continue.

# Button labels
Submit  ✓
Do Submission  ✗
```

### Helpful, Not Blaming

Errors should help, not shame:

```markdown
# Blaming
You entered an invalid email address.

# Helpful
Enter a valid email address (example: name@company.com).

# Blaming
Your password is wrong.

# Helpful
That password doesn't match our records. Try again or reset your password.
```

## Writing Interface Elements

### Buttons

Clear, action-oriented labels:

| Context | Good | Avoid |
|---------|------|-------|
| Submit form | Save | Submit |
| Delete item | Delete | Remove |
| Cancel action | Cancel | Nevermind |
| Confirmation | Confirm | OK |
| Navigation | View Details | Click Here |

### Form Labels and Hints

Help users complete forms:

```markdown
# Label
Email address

# Placeholder (example format)
name@company.com

# Helper text (requirements)
We'll send a confirmation to this address.

# Error state
Enter a valid email address.
```

### Error Messages

Structure: What happened + How to fix it

```markdown
# Structure
[What went wrong]. [How to fix it].

# Examples
This email is already registered. Sign in or use a different email.

Your session expired. Sign in again to continue.

That file is too large. Choose a file under 10 MB.
```

### Empty States

Guide users when there's no content:

```markdown
# No projects yet

You haven't created any projects.

[Create your first project]

---

# No search results

No results for "search term"

Try different keywords or check your spelling.
```

### Loading States

Keep users informed:

```markdown
# Brief operations
Saving...

# Longer operations
Uploading your file (45%)...

# Unknown duration
Loading your dashboard. This may take a moment...
```

### Success Messages

Confirm actions clearly:

```markdown
# Brief confirmation
Saved

# Action confirmation
Your changes have been saved.

# Next step suggestion
Profile updated. View your profile.
```

## Voice and Tone

### Establishing Voice

Voice is your product's personality:

| Voice Attribute | Description | Example |
|----------------|-------------|---------|
| Professional | Competent, trustworthy | "Your data is secure." |
| Friendly | Approachable, warm | "Welcome back!" |
| Direct | Clear, efficient | "File deleted." |
| Helpful | Supportive, guiding | "Need help? We're here." |

### Adapting Tone

Tone shifts based on context:

**Successful actions**: Positive, confirming
```
Your payment was successful.
```

**Errors**: Helpful, not alarming
```
We couldn't process your payment. Check your card details and try again.
```

**Destructive actions**: Clear, careful
```
Delete this project? This can't be undone.
```

**Empty states**: Encouraging, guiding
```
Your inbox is empty. Nice work!
```

## UX Writing Patterns

### Onboarding

Guide new users step by step:

```markdown
# Step 1 of 3: Create your account

Enter your email and create a password.

[Email field]
[Password field]

[Continue]

Already have an account? Sign in
```

### Confirmation Dialogs

Make consequences clear:

```markdown
# Delete "Project Alpha"?

This will permanently delete the project and all its contents.
This action can't be undone.

[Cancel]  [Delete Project]
```

### Permission Requests

Explain why you need access:

```markdown
# Allow notifications?

Get updates when team members comment on your work.

[Not Now]  [Allow]
```

## Accessibility in UX Writing

### Screen Reader Considerations

- Write descriptive link text ("View order details" not "Click here")
- Include alt text for images
- Label form fields clearly
- Announce state changes

### Cognitive Accessibility

- Use simple, common words
- Keep sentences short
- Provide clear instructions
- Avoid idioms and jargon

## Testing UX Copy

### Methods

- A/B testing different versions
- User testing with prototypes
- Analytics (click rates, completion rates)
- Support ticket analysis

### Questions to Ask

- Do users understand what to do?
- Can they complete tasks without help?
- Do error messages lead to recovery?
- Is the tone appropriate?

## Working with Teams

### Collaboration

UX writers work with:

- **Designers**: Integrate copy into designs
- **Developers**: Ensure copy is implemented correctly
- **Product managers**: Align on user goals
- **Support teams**: Learn from user issues

### Documentation

Maintain:

- Content style guide
- Terminology glossary
- UI text patterns
- Copy review checklist

## Summary

Effective UX writing:

- Guides users clearly
- Keeps text concise and scannable
- Helps users recover from errors
- Maintains consistent voice and tone
- Works for all users, including those using assistive technology

Good UX copy is invisible—users accomplish their goals without noticing the words that helped them.
