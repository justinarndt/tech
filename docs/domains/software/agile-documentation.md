---
title: Agile Documentation
description: Documentation practices that work within agile development workflows.
---

# Agile Documentation

Agile development emphasizes working software over comprehensive documentation. But "minimal documentation" doesn't mean "no documentation." Agile documentation is focused, useful, and maintained as the product evolves.

## Agile Documentation Philosophy

### Principles

From the Agile Manifesto:

> Working software over comprehensive documentation

This means:

- Document what's needed, not everything possible
- Keep documentation current and useful
- Prioritize documentation that helps users
- Update docs as part of the development process

### What Agile Documentation Is Not

- Not an excuse to skip documentation
- Not documentation written at the end
- Not static documents that never change
- Not separate from the development process

## Documentation in Sprints

### Including Docs in Sprint Work

Treat documentation as part of "done":

```markdown
## Definition of Done

- [ ] Code complete and reviewed
- [ ] Tests written and passing
- [ ] Documentation updated
- [ ] Release notes drafted
```

### Sizing Documentation Work

Estimate docs like other work:

| Feature Size | Doc Effort |
|--------------|-----------|
| Small bug fix | Update if behavior changes |
| Minor feature | Quick reference update |
| Major feature | Full documentation |
| API change | API docs + migration guide |

### Sprint Planning

Include doc tasks in planning:

```markdown
## Sprint 15 Documentation Tasks

- [ ] Update user guide for new dashboard (3 points)
- [ ] Document new API endpoints (5 points)
- [ ] Fix broken links reported in #234 (1 point)
- [ ] Review and update screenshots (2 points)
```

## Minimal Viable Documentation

### Start with Essentials

Focus on high-impact documentation:

1. **Installation/setup**: How to get started
2. **Core workflows**: Most common tasks
3. **API reference**: For developer products
4. **Troubleshooting**: Common problems and solutions

### Expand Based on Need

Add documentation when:

- Users ask the same questions repeatedly
- Support tickets indicate confusion
- Features are complex or non-obvious
- Compliance requires it

### The 80/20 Rule

Document the 20% of features used 80% of the time:

```markdown
## Priority Matrix

High Use + Complex = Document thoroughly
High Use + Simple = Quick reference
Low Use + Complex = Document when needed
Low Use + Simple = Skip or minimal
```

## Living Documentation

### Documentation as Code

Treat docs like code:

- Store in version control
- Review changes
- Test automatically
- Deploy continuously

### Continuous Updates

Update docs with each release:

```yaml
# Definition of Done includes documentation
definition_of_done:
  - code_complete: true
  - tests_passing: true
  - docs_updated: true
  - changelog_entry: true
```

### Review Cycles

Regularly review documentation:

- Sprint review: Check new feature docs
- Monthly: Review analytics for gaps
- Quarterly: Audit for accuracy
- Release: Full documentation review

## Documentation Types in Agile

### Just-in-Time Documentation

Write documentation when it's needed:

```markdown
## Feature Release Process

1. Feature development complete
2. Write user documentation
3. Write release notes
4. Deploy feature + docs together
```

### Just-Enough Documentation

Document what users need, not everything:

```markdown
## API Documentation Levels

Level 1 (MVP):
- Endpoint reference
- Basic examples

Level 2 (Standard):
- Conceptual overview
- Error handling
- Authentication

Level 3 (Comprehensive):
- Tutorials
- Integration guides
- Best practices
```

### Ephemeral vs. Persistent

Know what to keep and what to discard:

**Ephemeral** (discard after use):

- Sprint planning notes
- Design discussions
- Meeting notes

**Persistent** (maintain long-term):

- User documentation
- API reference
- Architecture decisions
- Onboarding guides

## Collaboration Patterns

### Embedded Writers

Technical writers on development teams:

**Benefits:**

- Context on features being built
- Real-time collaboration
- Documentation included in sprint work

**Challenges:**

- May lack perspective across teams
- Need coordination for cross-cutting docs

### Documentation Sprints

Dedicated time for documentation:

```markdown
## Documentation Sprint Goals

- Update all screenshots for new UI
- Complete API reference for v2
- Create migration guide from v1
- Fix all broken links
```

### Pair Writing

Writers and developers create docs together:

1. Developer explains feature
2. Writer asks clarifying questions
3. Together, draft the documentation
4. Writer refines, developer reviews

## Tools for Agile Documentation

### Wiki-Style Tools

Quick, collaborative editing:

- Confluence
- Notion
- GitBook
- Wiki.js

### Docs-as-Code Tools

Version-controlled documentation:

- MkDocs
- Docusaurus
- Sphinx
- Hugo

### Integration Tools

Connect docs to development:

- GitHub/GitLab wikis
- PR templates with doc checkboxes
- CI/CD for doc deployment

## Measuring Documentation

### Useful Metrics

- **Coverage**: Are new features documented?
- **Freshness**: How recently were docs updated?
- **Usage**: Which docs are being read?
- **Feedback**: Are users finding them helpful?

### Feedback Loops

Gather input continuously:

```markdown
## Documentation Feedback Sources

- Page-level ratings
- Support ticket analysis
- User interviews
- Search query analysis
- Sprint retrospectives
```

## Common Challenges

### "We Don't Have Time"

Include docs in definition of done. If there's no time for docs, there's no time for the feature.

### "Documentation Gets Outdated"

Update docs with code changes. Same PR, same sprint.

### "Writers Aren't Available"

Developers can draft, writers can polish. Or use collaborative sessions.

### "Nobody Reads Documentation"

Make docs findable. Put them where users look. Improve based on feedback.

## Summary

Agile documentation:

- Is part of the development process, not separate
- Focuses on what users need most
- Updates continuously with the product
- Treats documentation as code
- Measures effectiveness and improves

Good agile documentation is lean, useful, and always current.
