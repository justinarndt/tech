---
title: SME Interviews
description: Extracting information effectively from subject matter experts.
---

# SME Interviews

Subject matter experts (SMEs) hold the knowledge you need to write accurate documentation. Effective interviewing extracts that knowledge efficiently while building productive relationships.

## Understanding SMEs

### Who SMEs Are

**Engineers:**
- Build the product
- Know implementation details
- Often time-constrained
- May assume prior knowledge

**Product Managers:**
- Define requirements
- Understand user needs
- Know business context
- May lack technical depth

**Support Staff:**
- Know user problems
- Understand common questions
- See real-world usage
- Have practical knowledge

**Domain Experts:**
- Deep subject knowledge
- May not know the product
- Provide context and accuracy
- Often external consultants

### SME Challenges

Why interviews can be difficult:

| Challenge | How to Address |
|-----------|---------------|
| Busy schedules | Prepare thoroughly, respect time |
| Knowledge gaps | Don't know what you don't know |
| Assumed knowledge | Ask "beginner" questions |
| Imprecise answers | Follow up for specifics |
| Over-explanation | Guide to key points |
| Under-explanation | Probe for details |

## Interview Preparation

### Before the Interview

```markdown
## Pre-Interview Checklist

### Research
- [ ] Review existing documentation
- [ ] Read specs/design docs
- [ ] Try the feature yourself
- [ ] Note specific questions

### Logistics
- [ ] Schedule meeting
- [ ] Send agenda in advance
- [ ] Prepare recording (if permitted)
- [ ] Have note-taking system ready

### Questions
- [ ] Draft questions (prioritized)
- [ ] Include context for each
- [ ] Plan follow-up probes
- [ ] Identify must-have vs nice-to-have
```

### Question Types

**Open-ended questions:**
Get broad information.
- "Walk me through how this works."
- "What problem does this solve?"
- "What should users understand first?"

**Specific questions:**
Get precise details.
- "What's the maximum file size?"
- "What error appears when X happens?"
- "What permissions are required?"

**Clarifying questions:**
Ensure understanding.
- "When you say X, do you mean Y?"
- "Can you give me an example?"
- "What happens if the user does Z?"

**Verification questions:**
Confirm accuracy.
- "So if I understand correctly..."
- "Let me repeat that back..."
- "Is this the same as when...?"

### Question Framework

Structure questions around content needs:

```markdown
## Question Categories

### Overview/Conceptual
- What is this feature/system?
- Why was it built?
- Who should use it?
- When should they use it?

### Procedural
- How do users set this up?
- What are the steps to do X?
- What comes first/next/last?
- Are there variations?

### Reference
- What are all the options?
- What does each parameter do?
- What are the valid values?
- What are the defaults?

### Troubleshooting
- What can go wrong?
- How do users fix common problems?
- What errors might they see?
- When should they contact support?

### Edge Cases
- What limitations exist?
- What's not supported?
- What should users avoid?
- What's changing in the future?
```

## Conducting the Interview

### Setting the Stage

Start interviews well:

```markdown
## Interview Opening

"Thanks for taking the time to meet with me. I'm working
on documentation for [feature] and have some questions.

I'll take notes as we talk. Is it okay if I record this
for my reference? The recording is just for me.

I have about [X] questions, which should take [Y] minutes.
Feel free to tell me if I'm going in the wrong direction
or if there's something important I'm missing.

Let's start with [first question]..."
```

### Active Listening

**Techniques:**

- Make eye contact (video or in-person)
- Nod and provide verbal acknowledgments
- Take notes visibly
- Paraphrase to confirm understanding
- Ask follow-up questions

**Avoid:**

- Interrupting
- Jumping ahead
- Making assumptions
- Getting distracted
- Rushing

### Managing the Conversation

**Keep on track:**
"That's helpful. Let me note that. Can we circle back to X?"

**Dig deeper:**
"You mentioned Y. Can you tell me more about that?"

**Move on:**
"I think I have what I need here. Let's talk about Z."

**Handle tangents:**
"That's interesting context. For the documentation, should
users know about that, or is it more background?"

### Note-Taking

```markdown
## Note-Taking Format

Topic: [Feature/Topic]
Date: [Date]
SME: [Name]

## Key Points
- [Main fact 1]
- [Main fact 2]
- [Main fact 3]

## Quotes (exact wording)
- "[Direct quote worth keeping]"
- "[Another important quote]"

## Questions Answered
Q: [Question]
A: [Answer summary]

## Still Unclear
- [Item needing clarification]
- [Topic to follow up on]

## Action Items
- [ ] Confirm X with SME
- [ ] Test Y in staging
- [ ] Get screenshot of Z
```

## Post-Interview

### Processing Notes

Immediately after the interview:

1. **Review and expand notes** while fresh
2. **Highlight key information**
3. **Note gaps** requiring follow-up
4. **Send summary** to SME for verification

### Follow-Up Email

```markdown
Subject: Notes from our discussion about [Feature]

Hi [Name],

Thanks for meeting with me about [Feature]. Here's my
summary of what I learned:

**Key Points:**
- [Point 1]
- [Point 2]
- [Point 3]

**I'm still unclear on:**
- [Question 1]
- [Question 2]

**Next steps:**
- I'll draft the documentation and share for your review
- Expected completion: [Date]

Please let me know if I misunderstood anything above.

Thanks,
[Your name]
```

### Following Up

When you need more:

```markdown
## Follow-Up Request Template

Subject: Quick clarification on [Feature]

Hi [Name],

While writing the documentation for [Feature], I realized
I need clarification on a few points:

1. [Specific question]
2. [Specific question]

Would you prefer to:
- Reply via email
- Quick 15-minute call
- Slack thread

Thanks for your help!
```

## Difficult Situations

### Unresponsive SMEs

```markdown
## Escalation Path

1. Direct request with clear deadline
2. Follow-up after 2-3 days
3. Offer alternative formats (async, shorter meeting)
4. Escalate to their manager with impact statement
5. Escalate to your manager for help
```

### SME Doesn't Know

When SMEs don't have answers:

- "Who else might know about this?"
- "Is there documentation I could read?"
- "Can I observe someone using this?"
- "Can I test this myself and follow up with questions?"

### Conflicting Information

When SMEs disagree:

1. **Document both perspectives**
2. **Ask each to clarify** their reasoning
3. **Find authoritative source** (code, specs)
4. **Escalate to decision-maker** if needed

### Technical Overload

When explanations are too complex:

- "Can you explain that as if I'm a new user?"
- "What's the simplest way to describe this?"
- "If a user just needs to do X, what do they need to know?"
- "Can we walk through a specific example?"

## Building Relationships

### Being a Good Partner

Make working with you easy:

- **Be prepared** - Don't waste their time
- **Be respectful** - Acknowledge their expertise
- **Be efficient** - Get to the point
- **Be grateful** - Thank them sincerely
- **Be helpful** - Offer value in return

### Long-Term Relationships

Build ongoing partnerships:

- Share positive feedback about their help
- Credit them appropriately
- Keep them informed about doc progress
- Ask for their input on improvements
- Remember personal details

## Summary

Effective SME interviews require:

- Thorough preparation before meetings
- Active listening and good questions
- Efficient use of SME time
- Clear follow-up and verification
- Strong ongoing relationships

Good interviewing skills make you more effective and make SMEs more willing to help.
