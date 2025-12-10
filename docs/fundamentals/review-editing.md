---
title: Review and Editing for Technical Documentation
description: Master self-editing techniques and learn how to manage feedback from technical reviewers, editors, and users effectively.
---

# Review and Editing

First drafts are never final drafts. Review and editing transform rough content into polished documentation. This process catches errors, improves clarity, and ensures documentation serves users effectively.

## The Editing Mindset

Editing requires distance from your own writing. When you write, you know what you meant. Editing requires seeing what you actually wrote.

### Creating Distance

Strategies for objective self-review:

- **Time gap**: Set drafts aside before editing. Even a few hours helps.
- **Format change**: Print drafts or change fonts. Visual difference aids fresh reading.
- **Read aloud**: Hearing words reveals problems silent reading misses.
- **Read backward**: Sentence by sentence, from end to beginning. Breaks flow that glosses over errors.

### Editing vs. Writing

Do not edit while writing first drafts:

- Drafting requires flow and forward progress
- Editing requires analysis and revision
- Switching between modes wastes mental energy
- Draft first, then edit in separate passes

## Self-Editing Techniques

### Multiple Passes

Edit in focused passes, each addressing different concerns:

**Pass 1: Content and Structure**

- Is all necessary information present?
- Is anything unnecessary included?
- Does the structure support user tasks?
- Are sections in logical order?

**Pass 2: Clarity and Accuracy**

- Is each sentence clear?
- Is technical information accurate?
- Are procedures correct and complete?
- Can any sentences be simplified?

**Pass 3: Style and Consistency**

- Does the content follow the style guide?
- Is terminology consistent?
- Is formatting consistent?
- Is voice appropriate?

**Pass 4: Mechanics**

- Are there grammar errors?
- Are there spelling errors?
- Is punctuation correct?
- Are there typos?

Single-pass editing misses problems. Multiple focused passes catch more issues.

### Reading Aloud

Reading aloud catches problems:

- Awkward phrasing that reads poorly
- Run-on sentences that leave you breathless
- Missing words your eye skips
- Unclear instructions that sound wrong

Read slowly. Notice where you stumble.

### Checklist Review

Use checklists to ensure completeness:

**Content Checklist**

- [ ] All procedures tested
- [ ] Prerequisites stated
- [ ] Expected outcomes described
- [ ] Error cases addressed
- [ ] Links verified

**Style Checklist**

- [ ] Headings in correct case
- [ ] Lists formatted consistently
- [ ] UI elements styled correctly
- [ ] Code formatted properly

**Accessibility Checklist**

- [ ] Alt text for images
- [ ] Heading hierarchy correct
- [ ] Link text descriptive
- [ ] Color not sole information carrier

### Common Error Patterns

Watch for patterns in your own writing:

- Specific words you frequently misuse
- Punctuation habits that create errors
- Sentence structures that become unclear
- Formatting inconsistencies you tend toward

Track your patterns and check for them specifically.

## Technical Review

Technical review verifies accuracy with subject matter experts.

### Preparing for Review

Make review easy for busy SMEs:

- **Clean document**: No obvious errors or placeholders
- **Specific questions**: Highlight areas of uncertainty
- **Clear format**: Easy to read and comment
- **Reasonable length**: Break large documents into reviewable chunks

### Requesting Review

Effective review requests:

- State what you need (accuracy check, completeness review)
- Provide deadline with rationale
- Estimate time required
- Offer to meet if easier than written feedback

**Example request:**

> "Could you review the authentication API documentation for accuracy? I've highlighted three areas where I'm uncertain about error handling behavior. This should take about 30 minutes. I need feedback by Thursday to meet the release deadline."

### Review Questions

Guide reviewers with specific questions:

- "Is this procedure complete, or are there steps I'm missing?"
- "Are these error codes and their descriptions accurate?"
- "Would developers need any additional context here?"

Specific questions yield better feedback than "let me know what you think."

### Handling SME Feedback

SME feedback may be:

- **Accurate corrections**: Accept and implement
- **Terminology preferences**: Evaluate against style guide
- **Scope expansion**: Evaluate against project scope
- **Conflicting with other feedback**: Escalate for resolution

Thank reviewers. Follow up on unclear feedback. Close the loop on how you used their input.

## Editorial Review

Editorial review focuses on writing quality.

### Self-Editing Before Editorial Review

Do not waste editor time on issues you can catch:

- Run spell check
- Verify style guide basics
- Check formatting consistency
- Review your known error patterns

### Working with Editors

Editors are allies, not critics:

- Explain context they may not have
- Ask about changes you do not understand
- Learn from patterns in their feedback
- Accept that you are too close to your own writing

### Types of Editorial Feedback

**Substantive editing**: Structure, organization, content
**Copyediting**: Grammar, style, consistency
**Proofreading**: Typos, formatting, final errors

Different review stages catch different issues.

## User Review

User review tests documentation effectiveness.

### User Testing Methods

**Task completion testing:**
Can users accomplish tasks using the documentation?

**Comprehension testing:**
Do users understand what they read?

**Findability testing:**
Can users locate information?

### Observing Users

Watch users interact with documentation:

- Where do they pause or struggle?
- What questions do they ask?
- What do they skip?
- What confuses them?

Observation reveals problems users might not articulate.

### Acting on User Feedback

User feedback is authoritative about user experience:

- If users cannot find information, improve findability
- If users misunderstand content, improve clarity
- If users cannot complete tasks, fix procedures

Users may not know the solution, but they know the problem.

## Managing Feedback

Multiple reviewers generate significant feedback requiring management.

### Tracking Feedback

Track all feedback systematically:

- Source of feedback
- Specific issue raised
- Your decision (accept, reject, modify)
- Implementation status

Spreadsheets or issue trackers work well for complex projects.

### Evaluating Feedback

Not all feedback should be accepted:

**Accept when:**

- Feedback identifies genuine errors
- Feedback improves clarity
- Feedback aligns with documentation goals
- Multiple reviewers agree

**Question when:**

- Feedback conflicts with style guide
- Feedback reflects individual preference
- Feedback expands scope inappropriately
- Feedback introduces new errors

**Discuss when:**

- Feedback conflicts with other feedback
- You are uncertain about correctness
- Changes have significant implications

### Resolving Conflicts

When reviewers disagree:

- Clarify what each reviewer actually means
- Identify the underlying concern
- Consult style guide or standards
- Escalate to decision maker if needed
- Document the resolution

### Feedback Communication

Close the loop with reviewers:

- Acknowledge receipt of feedback
- Ask clarifying questions promptly
- Explain decisions to reject feedback (briefly)
- Share final documentation with reviewers

Reviewers who feel heard continue providing good feedback.

## Quality Assurance

Beyond individual review, systematic QA ensures consistent quality.

### Quality Standards

Define what quality means:

- Accuracy (factually correct)
- Completeness (nothing missing)
- Clarity (understandable by audience)
- Consistency (follows patterns and standards)
- Currency (reflects current product state)

### Quality Metrics

Measure quality through:

- Error rates found in review
- User-reported documentation bugs
- Support escalations due to documentation
- User satisfaction ratings

### Quality Improvement

Use metrics to improve:

- Identify recurring error types
- Address root causes (training, process, tools)
- Track improvement over time

## Editing Tools

Tools assist but do not replace human judgment.

### Spell Checkers

Catch obvious typos. Add technical terms to custom dictionaries.

Limitations: Homophones (their/there), correctly spelled wrong words (from/form).

### Grammar Checkers

Flag potential issues. Review each suggestion critically.

Limitations: Technical writing patterns may trigger false positives.

### Style Checkers

Tools like Vale enforce style guide rules automatically.

```yaml
# Example Vale configuration
StylesPath = styles
MinAlertLevel = suggestion

[*.md]
BasedOnStyles = Google
```

Limitations: Cannot catch all style issues; mechanical not contextual.

### Readability Tools

Hemingway Editor and similar tools measure complexity.

Limitations: Readability scores do not guarantee comprehension.

## Summary

Review and editing ensure documentation quality:

- **Self-edit** in multiple focused passes
- **Technical review** verifies accuracy
- **Editorial review** improves writing quality
- **User review** tests effectiveness
- **Manage feedback** systematically
- **Use tools** as aids, not authorities

First drafts need work. Review and editing transform them into documentation users can rely on.

---

**Next**: [Terminology Management](terminology-management.md) covers maintaining consistent vocabulary across documentation.
