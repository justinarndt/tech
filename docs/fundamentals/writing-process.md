---
title: The Technical Writing Process
description: Learn the complete technical writing workflow from planning and research through drafting, review, and publication.
---

# Writing Process

Technical writing follows a process from initial assignment through published documentation. Understanding this process helps writers work efficiently and produce better results.

The process is iterative rather than strictly linear. Writers move between stages as new information emerges or requirements change.

## Process Overview

The technical writing process includes:

1. **Planning**: Define scope, audience, and approach
2. **Research**: Gather information
3. **Outlining**: Organize content structure
4. **Drafting**: Write initial content
5. **Review**: Get feedback and verify accuracy
6. **Revision**: Incorporate feedback and improve
7. **Publication**: Release documentation
8. **Maintenance**: Keep documentation current

## Planning

Planning establishes what you will write, for whom, and how.

### Define the Scope

Clarify what the documentation should cover:

- What topics are included?
- What topics are explicitly excluded?
- What level of detail is required?
- What format will be used?

Document scope decisions to prevent scope creep.

### Identify the Audience

Determine who will use this documentation:

- What roles will read this?
- What do they already know?
- What do they need to accomplish?
- How will they access the documentation?

See [Audience Analysis](audience-analysis.md) for detailed guidance.

### Establish Constraints

Identify practical constraints:

- Deadline for delivery
- Resources available
- Dependencies on other work
- Review requirements

Constraints shape realistic planning.

### Create a Plan

Document your approach:

- Outline of content structure
- Research needed
- Review and approval process
- Timeline with milestones

Plans can be simple or detailed depending on project size.

## Research

Research gathers the information you need to write.

### Identify Sources

Determine where information will come from:

- Subject matter experts
- Existing documentation
- Product specifications
- Code and system exploration
- User feedback and support data

See [Research Methods](research-methods.md) for detailed guidance.

### Conduct Research

Execute your research plan:

- Schedule SME interviews
- Review existing materials
- Explore the product
- Document findings

### Organize Findings

Structure research for writing:

- Note which findings apply to which sections
- Identify gaps requiring additional research
- Flag uncertain information for verification

## Outlining

Outlining organizes content before writing.

### Benefits of Outlining

- Reveals structural problems early
- Ensures complete coverage
- Facilitates review of approach before writing
- Makes drafting faster

### Outline Approaches

**Topic-based outline:**
```
1. Introduction
   - What is X?
   - Why use X?
2. Getting Started
   - Prerequisites
   - Installation
   - Configuration
3. Basic Usage
   - First task
   - Second task
```

**Question-based outline:**
```
1. What is this feature?
2. When would I use it?
3. How do I set it up?
4. How do I use it?
5. What if something goes wrong?
```

### Outline Review

Share outlines for early feedback:

- Does the structure make sense?
- Is anything missing?
- Is the order logical?
- Does the depth match requirements?

Fixing structural problems in outlines is cheaper than fixing them in drafts.

## Drafting

Drafting converts outlines into written content.

### Drafting Strategies

**Sequential drafting:**
Write from beginning to end. Works well for linear content.

**Section-by-section:**
Complete one section before moving to the next. Allows focus and progress measurement.

**Easiest first:**
Start with sections you understand best. Builds momentum and reveals questions for harder sections.

**Hardest first:**
Tackle difficult sections while energy is highest. Prevents deadline crunch on challenging content.

### Writing the First Draft

First drafts do not need to be perfect:

- Focus on getting content down
- Leave placeholders for missing information
- Note questions and uncertainties
- Do not over-edit while drafting

Perfectionism during drafting slows progress without improving final quality.

### Handling Gaps

When you encounter missing information:

- Mark the gap clearly: [TODO: add error codes]
- Continue drafting other content
- Batch research questions for efficient follow-up
- Do not let gaps block progress on other sections

## Review

Review ensures documentation accuracy and quality.

### Self-Review

Review your own work first:

- Check for completeness against outline
- Verify accuracy of technical information
- Assess clarity and readability
- Confirm style guide compliance

See [Review and Editing](review-editing.md) for self-editing techniques.

### Technical Review

Subject matter experts verify accuracy:

- Provide reviewers with specific questions
- Make review easy with clear formatting
- Allow adequate review time
- Follow up on reviewer silence

### Editorial Review

Editors assess writing quality:

- Clarity and readability
- Style guide compliance
- Consistency across documents
- Grammar and punctuation

### User Review

Representative users test documentation:

- Can they accomplish tasks using the documentation?
- Do they understand explanations?
- Is information findable?

### Managing Feedback

Handle review feedback systematically:

- Track all feedback received
- Evaluate each item (accept, reject, discuss)
- Document decisions on contested feedback
- Confirm changes with reviewers when appropriate

## Revision

Revision incorporates feedback and improves content.

### Prioritizing Changes

Not all feedback is equal. Prioritize:

1. Accuracy errors (incorrect information)
2. Completeness gaps (missing information)
3. Clarity problems (confusing content)
4. Style issues (consistency, formatting)

### Revision Strategies

**Focused passes:**
Address one type of issue per revision pass. Accuracy first, then clarity, then style.

**Section-by-section:**
Complete all revisions for one section before moving to the next.

### Additional Review

Significant revisions may require additional review:

- Major changes need technical re-review
- Substantial rewrites need editorial review
- Changed procedures need user testing

### Knowing When to Stop

Revision can continue indefinitely. Stop when:

- Content is accurate and complete
- Clarity is acceptable for the audience
- Deadline requires publication
- Additional revision yields diminishing returns

Good enough, published, is better than perfect, unpublished.

## Publication

Publication releases documentation to users.

### Publication Checklist

Before publishing:

- [ ] All placeholders resolved
- [ ] Technical review complete
- [ ] Editorial review complete
- [ ] Links verified
- [ ] Images optimized and accessible
- [ ] Metadata complete (titles, descriptions)
- [ ] Navigation updated

### Release Coordination

Coordinate with product releases:

- Documentation available when features ship
- Release notes published alongside updates
- Old documentation updated or deprecated

### Announcement

Communicate new documentation:

- Release notes mention documentation changes
- Team channels notified of major updates
- Search engines notified of new content

## Maintenance

Documentation requires ongoing maintenance.

### Triggers for Updates

Update documentation when:

- Products change (features, UI, behavior)
- Users report errors
- Analytics reveal problems
- New information becomes available

### Maintenance Process

Apply the same process to updates:

- Plan the change scope
- Research current state and new information
- Draft updates
- Review for accuracy
- Publish and verify

### Retirement

Eventually, documentation becomes obsolete:

- Archive rather than delete when possible
- Redirect old URLs to current content
- Mark deprecated content clearly
- Remove from navigation but maintain for links

## Process Adaptation

Adapt the process to context:

### Small Updates

For minor changes:

- Abbreviated planning (know what you are changing)
- Minimal research (verify current state)
- Direct editing (no outline needed)
- Focused review (accuracy check)
- Quick publication

### Large Projects

For major documentation efforts:

- Detailed planning and scheduling
- Comprehensive research phase
- Structured outlines with stakeholder review
- Multiple drafts and review cycles
- Staged publication

### Agile Environments

In agile development:

- Documentation parallels development sprints
- Smaller, more frequent updates
- Continuous integration of documentation changes
- Close collaboration with development team

## Summary

The technical writing process provides structure for creating documentation:

1. **Plan**: Define scope, audience, and approach
2. **Research**: Gather necessary information
3. **Outline**: Organize content structure
4. **Draft**: Write initial content
5. **Review**: Verify accuracy and quality
6. **Revise**: Incorporate feedback
7. **Publish**: Release documentation
8. **Maintain**: Keep documentation current

The process is iterative—writers move between stages as needed. Adapt the process to project size and context.

---

**Next**: [Review and Editing](review-editing.md) covers self-editing techniques and managing review feedback.
