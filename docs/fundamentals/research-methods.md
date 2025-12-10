---
title: Research Methods for Technical Writers
description: Learn effective techniques for gathering accurate technical information through interviews, product exploration, documentation review, and user research.
---

# Research Methods

Technical writers rarely possess complete knowledge of the subjects they document. Research bridges the gap between what writers know and what documentation requires. Effective research skills distinguish writers who produce accurate, valuable documentation from those who produce superficial content.

## Research Challenges

Technical writing research presents unique challenges:

- **Subject matter experts (SMEs) are busy** and may not prioritize documentation
- **Products change rapidly**, sometimes faster than documentation cycles
- **Information is scattered** across code, tickets, wikis, and people's heads
- **Writers lack domain expertise** in specialized technical areas
- **Tacit knowledge** often goes undocumented

Effective research methods address these challenges systematically.

## Preparation

Research effectiveness depends on preparation.

### Define What You Need

Before starting research, clarify what you need to learn:

- What specific information is missing?
- What questions does the documentation need to answer?
- What level of detail is required?
- Who is the audience and what do they need to accomplish?

Vague research goals produce vague results.

### Review Existing Sources

Gather what already exists before asking people:

- Existing documentation (even if outdated)
- Product specifications and requirements
- Code comments and README files
- Ticket history and release notes
- Internal wikis and knowledge bases
- Recorded presentations or demos

This background prevents wasting SME time on information already available.

### Prepare Questions

Convert information gaps into specific questions:

**Vague:**
> "Tell me about authentication."

**Specific:**
> "What authentication methods does the API support?"
>
> "What happens when a token expires mid-request?"
>
> "Are there rate limits on authentication attempts?"

Specific questions yield useful answers. Vague questions yield unfocused discussions.

## Interviewing Subject Matter Experts

SME interviews are often the primary research method for technical writers.

### Scheduling

- Request specific time blocks (30-60 minutes)
- Send questions in advance so SMEs can prepare
- Respect their time constraints
- Offer flexibility on meeting format (in-person, video, async)

### Conducting Interviews

**Start with context:**
> "I'm documenting the authentication API for developers integrating with our platform. I want to make sure they can get started quickly and handle edge cases."

Context helps SMEs tailor their explanations appropriately.

**Ask open questions first:**
> "Walk me through how authentication works from the user's perspective."

Open questions reveal information you did not know to ask about.

**Follow with specific questions:**
> "What error does the API return when credentials are invalid?"
>
> "What's the token expiration time?"

Specific questions fill gaps and clarify details.

**Clarify understanding:**
> "So if I understand correctly, the refresh token is only valid for 24 hours, but the access token expires after 15 minutes?"

Restating information confirms your understanding and catches errors.

**Ask for examples:**
> "Can you show me an example request and response?"

Concrete examples are often clearer than abstract explanations.

### Recording and Notes

- Ask permission before recording
- Take notes even when recording (recording may fail)
- Note follow-up questions as they arise
- Mark areas of uncertainty for later verification

### Follow-Up

- Send summary notes for SME review
- Follow up on unanswered questions
- Thank SMEs for their time
- Share the resulting documentation with them

## Hands-On Exploration

Using the product yourself provides information no interview can match.

### Benefits of Direct Experience

- Understanding actual user workflows
- Discovering undocumented behaviors
- Finding gaps in your understanding
- Generating questions for SME follow-up

### Exploration Techniques

**Follow the happy path:**
Complete the basic use case from start to finish. Document each step.

**Break things intentionally:**
Enter invalid data. Disconnect from the network. Use incorrect credentials. Observe error messages and behaviors.

**Explore edge cases:**
What happens with maximum values? Empty inputs? Special characters? Concurrent operations?

**Note friction points:**
Where did you get confused? Where did you need to guess? These are often documentation opportunities.

### Documentation While Exploring

- Screenshot important screens
- Copy exact error messages
- Note your questions and confusion points
- Document steps you took and results you observed

## Code and Specification Review

For technical documentation, source code and specifications are primary sources.

### Reading Code

You do not need to write code to extract documentation-relevant information from it:

**Function signatures** reveal parameters, types, and return values:

```python
def create_user(email: str, role: str = "viewer") -> User:
    """Create a new user account."""
```

This tells you: email is required, role is optional with default "viewer", returns a User object.

**Error handling** reveals possible failures:

```python
if not valid_email(email):
    raise ValidationError("Invalid email format")
if User.exists(email):
    raise ConflictError("User already exists")
```

**Configuration files** reveal options and defaults:

```yaml
server:
  timeout: 30  # seconds
  max_connections: 100
```

### API Specifications

OpenAPI, Swagger, and similar specifications provide structured information:

- Endpoints and methods
- Request and response formats
- Required vs. optional parameters
- Possible response codes

These specifications may be incomplete or outdated, but they provide a starting point.

### Reading Specifications

Product requirements and design documents contain context:

- Why features were built
- Intended use cases
- Known limitations
- Future plans

This context helps writers explain not just how, but why.

## User Research

Understanding users improves documentation relevance.

### Analytics

Documentation analytics reveal user behavior:

- **Popular pages**: What do users seek most?
- **Search queries**: What terms do users use?
- **Failed searches**: What cannot users find?
- **Time on page**: Are users finding what they need?
- **Exit points**: Where do users give up?

### Support Data

Support interactions reveal documentation gaps:

- Frequent support questions indicate documentation needs
- User confusion points suggest areas for clarification
- User terminology reveals vocabulary preferences

### Direct User Feedback

User feedback provides qualitative insight:

- Feedback widgets ("Was this helpful?")
- User surveys about documentation quality
- Usability testing of documentation
- Community forum discussions

## Verifying Information

Research produces raw information that requires verification.

### Cross-Reference Sources

Verify information across multiple sources:

- Does the code match the specification?
- Does the behavior match the documentation?
- Do different SMEs give consistent information?

Discrepancies indicate errors or changes requiring clarification.

### Test Procedures

Execute your own procedures before publishing:

- Follow documented steps exactly
- Verify each step produces expected results
- Note where instructions are unclear or incorrect

### Technical Review

Have SMEs review documentation for accuracy:

- Provide specific questions about uncertain areas
- Ask them to flag errors rather than just approve
- Make review easy with clear formatting and tracked changes

### Continuous Verification

Products change. Verification is ongoing:

- Review documentation when products update
- Test procedures periodically
- Monitor for user-reported errors
- Track changes that might affect accuracy

## Documenting Your Research

Research produces artifacts that support documentation work.

### Research Notes

Maintain organized research notes:

- Date and source of information
- Direct quotes vs. your interpretations
- Questions still unanswered
- Confidence level in information

### Information Tracking

Track what information exists and where:

- What topics are well-documented
- What topics need more research
- Which SMEs know what
- Which sources are authoritative

### Knowledge Sharing

Share research findings with your team:

- Research notes accessible to other writers
- Lessons learned from research process
- SME contact information and expertise areas

## Common Research Problems

### SME Unavailability

When SMEs are unavailable:

- Use async communication (email, chat)
- Maximize research through other sources first
- Batch questions to minimize SME time
- Build relationships over time for better access

### Conflicting Information

When sources disagree:

- Identify which source is authoritative
- Determine if information is outdated
- Escalate to someone who can resolve the conflict
- Document the correct information and its source

### Incomplete Information

When you cannot get complete answers:

- Document what you know with appropriate caveats
- Mark uncertain information for follow-up
- Publish partial documentation rather than none
- Track gaps for future completion

### Rapidly Changing Products

When products change faster than documentation:

- Focus on stable fundamentals
- Build relationships for early change notification
- Automate where possible
- Accept some lag and prioritize updates

## Summary

Effective research makes accurate documentation possible:

- **Prepare** by defining needs and reviewing existing sources
- **Interview SMEs** with specific questions and respect for their time
- **Explore products** directly to understand user experience
- **Review code and specifications** as primary sources
- **Understand users** through analytics and feedback
- **Verify information** through cross-referencing and testing
- **Document research** for ongoing reference

Research skills develop with practice. Each project builds knowledge of sources, SMEs, and effective techniques for your specific context.

---

**Next**: [Information Architecture](information-architecture.md) covers organizing large documentation sets for usability.
