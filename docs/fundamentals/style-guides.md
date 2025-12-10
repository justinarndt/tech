---
title: Style Guides for Technical Writing
description: Learn how to use existing style guides and create custom style guides to ensure consistency across technical documentation.
---

# Style Guides

Consistency builds trust and reduces cognitive load. When documentation follows predictable patterns, readers focus on content rather than adapting to variations. Style guides establish these patterns.

A style guide documents decisions about writing style, terminology, formatting, and voice. It ensures that documentation produced by different writers, at different times, reads as a coherent whole.

## Why Style Guides Matter

### Consistency Benefits

**For readers:**

- Predictable structure aids navigation
- Consistent terminology prevents confusion
- Uniform formatting supports scanning

**For writers:**

- Decisions do not need to be remade for each document
- Reviews focus on content rather than style debates
- New writers can produce on-brand content quickly

**For organizations:**

- Documentation reflects unified brand voice
- Maintenance becomes manageable
- Quality standards are documented and measurable

### Without Style Guides

Without style guides, inconsistency accumulates:

- One page says "login," another says "log in," another says "sign in"
- Some procedures use numbered lists, others use bullets
- Capitalization varies by author
- Tone shifts from formal to casual

Readers notice this inconsistency even if they cannot articulate it. It signals disorganization and undermines confidence.

## Established Style Guides

Do not create a style guide from scratch. Start with an established guide and customize as needed.

### General Purpose

**Google Developer Documentation Style Guide**

Comprehensive guide for developer-focused documentation. Covers everything from word choice to code samples. Free and publicly available.

Best for: Software documentation, API references, developer tutorials.

**Microsoft Writing Style Guide**

Focuses on clarity and accessibility. Regularly updated. Available online.

Best for: Product documentation, user guides, enterprise software.

**Apple Style Guide**

Emphasizes clarity and precision. Strong focus on UI terminology.

Best for: Consumer software, mobile applications.

### Academic and Publishing

**Chicago Manual of Style**

Comprehensive reference for publishing standards. Detailed guidance on citations, punctuation, and formatting.

Best for: White papers, formal reports, academic documentation.

**Associated Press (AP) Stylebook**

Journalism standard. Concise, practical guidance.

Best for: Press releases, marketing documentation, blog content.

### Domain-Specific

**AMA Manual of Style**

Medical and scientific writing standards.

**IEEE Editorial Style Manual**

Engineering and technical standards.

**PLAIN Language Guidelines**

US government plain language requirements.

## Using a Style Guide

Adopting a style guide requires more than downloading a document.

### Selection

Choose a style guide based on:

- Your audience (developers, consumers, specialists)
- Your industry (software, medical, finance)
- Your existing documentation (what style does it approximate?)
- Your team's familiarity (easier to adopt something people know)

### Customization

No published guide covers every situation. Create supplements for:

- Company-specific terminology
- Product names and branding
- Topics the base guide does not address
- Decisions where you differ from the base guide

### Documentation

Document your style decisions in an accessible location:

- Internal wiki or documentation site
- Style guide document with searchable index
- Linting configuration that enforces rules

### Training

Style guides only work if writers use them:

- Introduce the guide to all documentation contributors
- Provide quick reference cards for common decisions
- Include style review in documentation feedback
- Update training when the guide changes

## Creating a Custom Style Guide

For topics not covered by established guides, create custom guidance.

### What to Include

**Voice and Tone**

- How formal or casual?
- Direct or friendly?
- First person, second person, or third person?

**Terminology**

- Product and feature names
- Technical terms and their usage
- Avoided terms (and alternatives)

**Formatting**

- Heading capitalization (sentence case vs. title case)
- List formatting (punctuation, capitalization)
- Code formatting (inline vs. block, syntax highlighting)

**UI and Interaction**

- How to refer to UI elements
- How to format menu paths
- Click vs. select vs. choose

**Numbers and Measurements**

- When to spell out numbers
- Units and abbreviations
- Date and time formats

**Punctuation**

- Serial comma usage
- Apostrophes in plurals
- Quotation marks vs. code formatting

### Terminology Decisions

Document specific terminology decisions:

| Use | Do Not Use | Notes |
|-----|------------|-------|
| sign in | log in, login | Consistent with product UI |
| email | e-mail | No hyphen |
| set up (verb) | setup | "Set up the server" |
| setup (noun) | set up | "Complete the setup" |
| data center | datacenter | Two words |
| web page | webpage | Two words |

Include rationale when helpful. Writers follow rules better when they understand the reasoning.

### Voice Guidelines

Define your documentation voice:

**Example voice definition:**

> Our documentation is professional but approachable. We write directly, using "you" to address the reader. We avoid jargon when simpler terms work, but we use precise technical terms when accuracy requires them.
>
> We are helpful, not condescending. We assume readers are intelligent but may not have our specific domain knowledge. We explain concepts but do not over-explain basics.
>
> We are confident, not arrogant. We state things directly without hedging unnecessarily, but we acknowledge limitations and uncertainties when they exist.

### Example-Based Guidance

Rules are clearer with examples:

**Do not write:**

> It is recommended that the configuration file be updated prior to initialization of the server.

**Write:**

> Update the configuration file before starting the server.

Show both the problematic pattern and the correct alternative.

## Enforcing Style

Style guides only matter if they are followed.

### Review Processes

Include style review in documentation workflows:

- Editors check for style compliance
- Peer reviews include style considerations
- Checklists reference key style points

### Automated Enforcement

Tools can enforce some style rules automatically:

**Vale**: Prose linter with customizable rules

```yaml
# .vale.ini
StylesPath = styles
MinAlertLevel = warning

[*.md]
BasedOnStyles = Google, Microsoft
```

**Alex**: Catches insensitive language

**Textlint**: Pluggable linting for text

Automated tools catch mechanical issues. Human review catches nuance.

### Practical Enforcement

Perfect compliance is not the goal. Prioritize:

- Issues that affect comprehension
- Terminology consistency
- Major voice and tone violations

Let minor variations go when they do not affect quality.

## Maintaining Style Guides

Style guides require maintenance to remain useful.

### Regular Review

Schedule periodic style guide reviews:

- Are rules still appropriate?
- Have new situations arisen?
- Are rules being followed?
- Do rules conflict with each other?

### Updating Process

Define how style guide changes happen:

1. Propose change with rationale
2. Discuss with documentation team
3. Decide (someone must have authority)
4. Update the guide
5. Communicate the change
6. Update existing documentation (or not, for minor changes)

### Version Control

Track style guide changes:

- Version the style guide document
- Document when rules changed
- Note which documentation follows which version

### Handling Exceptions

Sometimes rules do not apply. Define how to handle exceptions:

- When are exceptions allowed?
- Who can approve exceptions?
- How are exceptions documented?

Exceptions should be rare. If a rule has many exceptions, the rule may need revision.

## Quick Reference

Create quick reference materials for common decisions:

### Sample Quick Reference Card

**Voice**

- Use second person ("you")
- Use active voice
- Use imperative mood for instructions

**Terminology**

- sign in (not log in)
- email (not e-mail)
- data center (two words)
- set up (verb), setup (noun)

**Formatting**

- Sentence case for headings
- Serial comma (a, b, and c)
- Bold for UI elements: Click **Submit**
- Code font for inline code: `filename.txt`

**Numbers**

- Spell out one through nine
- Use numerals for 10 and above
- Always use numerals with units: 5 MB

Quick reference cards help writers make decisions without consulting the full guide.

## Summary

Style guides ensure consistency across documentation:

- Start with an established guide (Google, Microsoft, Chicago)
- Customize for your specific needs
- Document terminology, voice, formatting, and special cases
- Train writers on style expectations
- Enforce through review and automated tools
- Maintain the guide over time

Consistency is not about rigid rules—it is about reducing cognitive load for readers and making documentation feel like a unified resource rather than a collection of disconnected pages.

---

**Next**: [Research Methods](research-methods.md) covers techniques for gathering accurate technical information.
