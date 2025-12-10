---
title: Terminology Management for Technical Documentation
description: Learn how to create and maintain consistent terminology across documentation, including glossaries, term bases, and terminology governance processes.
---

# Terminology Management

Consistent terminology helps users understand documentation. Inconsistent terminology confuses them. When the same concept appears as "login," "log in," "sign in," and "sign-in" across different pages, users waste time wondering if these mean different things.

Terminology management establishes and maintains consistent vocabulary across documentation.

## Why Terminology Matters

### User Impact

Inconsistent terminology causes problems:

- Users search for terms that do not appear in documentation
- Users wonder if different terms mean different things
- Users lose confidence in documentation accuracy
- Non-native speakers struggle more with variations

### Business Impact

Poor terminology affects business:

- Translation costs increase (each variation needs translation)
- Support burden grows (users confused by inconsistency)
- Search effectiveness decreases
- Brand consistency suffers

### Scale of the Problem

Terminology inconsistency grows with:

- Documentation volume
- Number of writers
- Product complexity
- Time (terms drift over time)
- Organization size

Without active management, inconsistency compounds.

## Terminology Inventory

Start with understanding current state.

### Identifying Key Terms

Document terms that require consistency:

**Product terms:**
- Product names and versions
- Feature names
- UI element names
- Technical concepts

**Action terms:**
- Click, tap, select, choose
- Sign in, log in
- Start, begin, initiate

**Technical terms:**
- Domain-specific vocabulary
- Industry standard terms
- Acronyms and abbreviations

### Auditing Current Usage

Review existing documentation for variations:

1. Search for known problem terms
2. Note all variations found
3. Identify which variation is most common
4. Identify which variation aligns with product UI

Tools like grep or documentation search can find variations:

```bash
# Find variations of "sign in"
grep -ri "sign in\|signin\|sign-in\|log in\|login" docs/
```

### Prioritizing Terms

Not all terms need equal attention. Prioritize:

- **High frequency**: Terms appearing throughout documentation
- **User-facing**: Terms users see in the product
- **Confusion-prone**: Terms with common variations
- **Translatability**: Terms that affect translation quality

## Creating Term Standards

### Term Entries

Document each standard term:

**Term**: sign in (verb)

**Definition**: To access an account by providing credentials

**Usage notes**: Two words as a verb. Use "sign-in" as a noun or adjective (e.g., "the sign-in page").

**Do not use**: log in, login, signin

**Examples**:
- Correct: "Sign in to your account."
- Correct: "Visit the sign-in page."
- Incorrect: "Login to your account."

### Decision Criteria

Base terminology decisions on:

1. **Product UI**: Match what users see in the interface
2. **Industry standards**: Use established terms when they exist
3. **User research**: Use terms users naturally use
4. **Style guide**: Follow your adopted style guide
5. **Consistency**: Prefer terms already used consistently

### Documenting Decisions

Record why terms were chosen:

> **Decision**: Use "sign in" not "log in"
>
> **Rationale**: "Sign in" matches our product UI. Microsoft and Google style guides prefer "sign in" for user-facing content.
>
> **Date**: 2024-01-15
>
> **Decided by**: Documentation team

Rationale helps future writers understand and maintain decisions.

## Glossaries

Glossaries provide term definitions for users and writers.

### User Glossaries

Public glossaries help users:

```markdown
## Glossary

**API key**: A unique identifier used to authenticate requests to the API.

**Workspace**: A container for organizing related projects and settings.

**Webhook**: An automated notification sent to a specified URL when events occur.
```

### Writer Glossaries

Internal glossaries include usage guidance:

```markdown
## Terminology Guide

### data center (noun)
Two words, lowercase unless starting a sentence.
- Correct: "Our data center is located in Virginia."
- Incorrect: "Our datacenter is located in Virginia."
- Incorrect: "Our Data Center is located in Virginia."

### set up / setup
- "set up" (verb): "Set up your account."
- "setup" (noun/adjective): "Complete the setup process."
```

### Glossary Maintenance

Glossaries require maintenance:

- Add new terms as products evolve
- Update definitions when meanings change
- Remove obsolete terms
- Review periodically for accuracy

Stale glossaries lose credibility and usefulness.

## Term Bases

Term bases are structured databases for terminology, especially useful for translation.

### Term Base Structure

Typical term base fields:

| Field | Purpose |
|-------|---------|
| Term | The approved term |
| Definition | What the term means |
| Context | Usage examples |
| Domain | Product area or subject |
| Status | Approved, deprecated, proposed |
| Notes | Usage guidance |
| Do not use | Rejected alternatives |

### Term Base Tools

Tools for managing term bases:

- **Spreadsheets**: Simple, accessible, limited features
- **SDL MultiTerm**: Professional terminology management
- **MemoQ**: Translation-focused term management
- **Custom databases**: Flexible, requires development

### Integration with Workflows

Effective term bases integrate with:

- Writing tools (autocomplete, validation)
- Translation tools (term matching)
- Review processes (terminology checking)
- Documentation platforms (automated glossaries)

## Terminology Governance

Managing terminology requires governance processes.

### Ownership

Define who owns terminology:

- Who can approve new terms?
- Who resolves disagreements?
- Who maintains the term base?

Clear ownership prevents drift and conflict.

### Proposal Process

Process for new terms:

1. Writer encounters need for new term
2. Writer checks existing terms
3. Writer proposes new term with rationale
4. Owner reviews and decides
5. Term added to standards
6. Writers notified of new standard

### Change Process

Process for changing established terms:

1. Need for change identified
2. Impact assessment (how much documentation affected?)
3. Decision on change
4. Communication to writers
5. Update plan for existing documentation
6. Term base updated

Changes should be rare—consistency depends on stability.

### Enforcement

How are standards enforced?

**Manual review:**
Editors check terminology during review.

**Automated checking:**
Linting tools flag non-standard terms.

```yaml
# Example Vale style for terminology
extends: substitution
message: Use '%s' instead of '%s'
level: error
swap:
  log in: sign in
  login: sign in
  signin: sign in
```

**Training:**
Writers learn standards during onboarding.

## Terminology in Translation

Terminology is critical for translation quality.

### Translation Impact

Good terminology management:

- Reduces translation costs (consistent source text)
- Improves translation quality (clear terms to translate)
- Speeds translation (term bases provide approved translations)
- Maintains consistency across languages

### Term Translation

For each term, document:

- Source term (English)
- Target term (each language)
- Definition in target language
- Usage notes for translators

### Untranslatable Terms

Some terms should not be translated:

- Product names
- Feature names (often)
- Technical standards (sometimes)

Document which terms remain in English across languages.

## Common Terminology Problems

### Synonym Proliferation

Multiple terms for the same concept:

> "Click the Save button."
> "Press the Save button."
> "Select Save."
> "Choose Save."

Solution: Pick one term and use it consistently.

### Inconsistent Capitalization

> "Click the save button."
> "Click the Save button."
> "Click the Save Button."

Solution: Define capitalization rules for UI elements.

### Ambiguous Terms

Terms with multiple meanings:

> "Enter your data in the form."

Is "data" information or a specific data object?

Solution: Use specific terms; define ambiguous terms clearly.

### Jargon Creep

Internal jargon leaking into user documentation:

> "Configure the widget's hydration settings."

Solution: Use user-facing terminology; define necessary technical terms.

### Term Drift

Terms changing meaning over time:

> Originally: "Workspace" meant a set of files.
> Now: "Workspace" means a team environment.

Solution: Regular terminology audits; update definitions.

## Building Terminology Culture

Terminology consistency requires cultural support.

### Writer Buy-In

Help writers understand why terminology matters:

- Show impact on users and translation
- Make standards easy to follow
- Respond to feedback about standards
- Acknowledge terminology is not glamorous but is important

### Making Standards Accessible

Standards only work if writers can find them:

- Single source of truth for terminology
- Searchable format
- Integration with writing tools
- Quick reference guides

### Continuous Improvement

Improve terminology management over time:

- Track common errors
- Streamline proposal process
- Improve tooling
- Expand coverage gradually

## Summary

Terminology management ensures consistent vocabulary:

- **Audit** current terminology usage
- **Create standards** with clear guidance
- **Build glossaries** for users and writers
- **Manage term bases** for structured terminology
- **Govern** through clear ownership and processes
- **Support translation** with consistent source terms
- **Build culture** that values consistency

Consistent terminology seems minor but significantly impacts user experience and documentation quality.

---

**Next**: [Content Reuse](content-reuse.md) covers writing modular content that works in multiple contexts.
