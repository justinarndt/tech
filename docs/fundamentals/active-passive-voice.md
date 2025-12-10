---
title: Active vs. Passive Voice in Technical Writing
description: Learn when to use active and passive voice in technical documentation, with examples and guidelines for making effective voice choices.
---

# Active vs. Passive Voice

Voice determines who does what in a sentence. Active voice emphasizes the actor; passive voice emphasizes the action or recipient. Both have legitimate uses in technical writing, but knowing when to use each makes documentation clearer and more effective.

## Understanding Voice

### Active Voice

In active voice, the subject performs the action.

> The administrator **configures** the firewall.

Structure: Subject (actor) → Verb → Object

The actor is clear. The sentence flows naturally from doer to action to recipient.

### Passive Voice

In passive voice, the subject receives the action.

> The firewall **is configured** by the administrator.

Structure: Subject (recipient) → Verb → (by Actor, often omitted)

The recipient comes first. The actor may be included or omitted.

### Identifying Passive Voice

Passive voice typically includes:

- A form of "to be" (is, was, were, been, being)
- A past participle (configured, deleted, created)
- Optionally, "by" followed by the actor

| Passive | Active |
|---------|--------|
| The file was deleted | Someone deleted the file |
| Errors are logged automatically | The system logs errors automatically |
| The report is generated nightly | A scheduled job generates the report nightly |

Not every "is" indicates passive voice. "The server is running" is active (the server performs the running). "The server is restarted" is passive (something restarts the server).

## Why Active Voice Is Usually Better

For most technical documentation, active voice works better.

### Clarity

Active voice makes actors explicit.

**Passive (unclear actor):**
> The configuration file must be updated.

Who updates it? The administrator? The user? The system?

**Active (clear actor):**
> The administrator must update the configuration file.

When users need to do something, tell them directly.

### Directness

Active voice uses fewer words.

**Passive:**
> The password can be reset by clicking the "Forgot Password" link.

**Active:**
> Click "Forgot Password" to reset your password.

The active version is shorter and tells users what to do.

### Engagement

Active voice speaks to users directly.

**Passive:**
> The form should be completed before submission is attempted.

**Active:**
> Complete the form before submitting it.

Direct address ("you" implied) engages users and clarifies responsibility.

### Procedural Clarity

Procedures work better in active voice.

**Passive:**
> 1. The Settings menu should be opened.
> 2. The Security option must be selected.
> 3. The new password should be entered.

**Active:**
> 1. Open the Settings menu.
> 2. Select Security.
> 3. Enter your new password.

Imperative active voice (commands) is the clearest form for instructions.

## When Passive Voice Works Better

Despite the general preference for active voice, passive voice serves specific purposes in technical writing.

### When the Actor Is Unknown or Irrelevant

Sometimes who performed an action does not matter.

**Passive (appropriate):**
> The logs are rotated every 24 hours.

Users care about the rotation schedule, not which system component rotates them.

**Passive (appropriate):**
> Requests are authenticated before processing.

The authentication mechanism matters less than the fact that authentication occurs.

### When the Action or Recipient Matters More

Emphasize what matters most.

**Active (emphasis on actor):**
> The cron job deletes temporary files.

**Passive (emphasis on files):**
> Temporary files are deleted after 24 hours.

If the page is about temporary files, the passive version correctly emphasizes them.

### When Avoiding Blame

Error messages and sensitive contexts sometimes warrant passive voice.

**Active (accusatory):**
> You entered an invalid password.

**Passive (neutral):**
> The password entered is invalid.

The passive version avoids blame while communicating the problem.

### In Scientific and Regulatory Writing

Some domains traditionally use passive voice.

**Scientific convention:**
> The samples were analyzed using mass spectrometry.

**Regulatory language:**
> The device shall be inspected before each use.

Following domain conventions improves credibility with specialist audiences.

### When Maintaining Parallel Structure

Consistency sometimes favors passive voice.

> The data is collected from sensors, processed by the analytics engine, and stored in the database.

Mixing active and passive in a series can feel awkward. Maintain parallel structure even if it means using passive voice.

## Guidelines for Choosing Voice

### Default to Active

Start with active voice. Switch to passive only when it serves a specific purpose.

Ask: "Does this sentence clearly communicate who does what?"

If yes, active voice is probably correct. If the actor is irrelevant or unknown, consider passive.

### Use Active for Instructions

Procedures should use active imperative voice:

> Save the file before closing the application.
>
> Click **Submit** to complete the process.
>
> Verify that all dependencies are installed.

Direct commands are unambiguous about who acts (the reader) and what to do.

### Use Passive for System Descriptions

When describing what systems do automatically, passive voice can work well:

> User sessions are terminated after 30 minutes of inactivity.
>
> Failed login attempts are logged for security review.
>
> Data is encrypted in transit and at rest.

The focus is on what happens, not which component makes it happen.

### Match Emphasis to Content

Choose voice based on what matters:

| Focus | Voice | Example |
|-------|-------|---------|
| User action | Active | You configure the settings |
| System behavior | Either | The system validates input / Input is validated |
| What happens to data | Passive | Data is encrypted |
| Who is responsible | Active | The administrator approves requests |

### Avoid Passive in Procedures

Procedural steps should almost always be active:

**Avoid:**
> The file should be opened in a text editor.

**Prefer:**
> Open the file in a text editor.

The passive version is longer and less clear about who acts.

## Mixing Voice Effectively

Documents can use both voices appropriately.

### Example: Feature Description

> The backup system automatically archives files every night. **(Active: describes what the system does)**
>
> Files are compressed before storage to reduce disk usage. **(Passive: emphasizes files and compression)**
>
> To restore a file, open the Backup Manager and select the file you want to recover. **(Active: instructs the user)**

Each sentence uses the voice that best serves its purpose.

### Example: Troubleshooting

> **Error: Connection refused**
>
> This error occurs when the server is unreachable. **(Passive: focus on the condition)**
>
> Check that the server is running and that your firewall allows connections on port 443. **(Active: instructs the user)**

The passive sentence describes the situation; the active sentence tells users what to do.

## Common Problems

### Unnecessary Passive

Passive voice without purpose makes writing weak:

**Weak:**
> It was decided that the feature would be implemented.

**Strong:**
> The team decided to implement the feature.

Or simply:

> We will implement the feature.

If you can name the actor and doing so adds clarity, use active voice.

### Hidden Actors

Passive voice can hide important information:

**Missing information:**
> The API keys must be rotated regularly.

By whom? The user? An administrator? An automated system? If the reader needs to know, say so:

**Complete:**
> Administrators must rotate API keys every 90 days.

### Passive Imperatives

Passive commands sound awkward:

**Awkward:**
> The button should be clicked.

**Clear:**
> Click the button.

Instructions should tell people what to do, not describe what should happen.

## Practice

Rewrite these passive sentences in active voice where appropriate:

1. The system should be restarted after the update is installed.
2. Errors encountered during processing are logged to the console.
3. The report can be generated by selecting Export from the File menu.
4. User data is protected by encryption.

Consider which sentences might legitimately remain passive and why.

## Summary

Active voice clearly identifies who does what. It works best for instructions, procedures, and user-directed content. Passive voice emphasizes actions or recipients over actors. It works when actors are unknown, irrelevant, or when the action itself matters most.

Default to active voice. Use passive voice deliberately when it serves clarity or emphasis. Match voice to purpose, and documentation becomes clearer for everyone.

---

**Next**: [Document Structure](document-structure.md) covers organizing information for findability and usability.
