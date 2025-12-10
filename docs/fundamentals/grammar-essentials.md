---
title: Grammar Essentials for Technical Writing
description: Master the grammar rules most important for technical documentation, including punctuation, sentence structure, and common error patterns.
---

# Grammar Essentials

Grammar matters in technical writing because it affects comprehension. Errors distract readers, create ambiguity, and undermine credibility. Perfect grammar is not the goal—clear communication is. But grammar errors often obstruct clarity.

This guide covers the grammar issues most relevant to technical documentation, not comprehensive grammar instruction.

## Sentence Structure

### Complete Sentences

Technical writing generally uses complete sentences with subject and verb:

**Fragment:**
> Important for security.

**Complete:**
> This setting is important for security.

Fragments work in lists and headings. In running text, use complete sentences.

### Sentence Length

Long sentences create comprehension problems:

**Too long:**
> When the system detects an authentication failure, which can occur due to expired credentials, incorrect passwords, or disabled accounts, it logs the attempt, increments the failure counter, and if the counter exceeds the threshold configured in the security settings, which defaults to five attempts, the account is locked for the period specified in the lockout duration setting.

**Better:**
> When the system detects an authentication failure, it logs the attempt and increments the failure counter. Failures can occur due to expired credentials, incorrect passwords, or disabled accounts. If the counter exceeds the threshold (default: 5 attempts), the account is locked for the configured lockout duration.

Aim for 15-25 words per sentence on average. Vary length for rhythm, but break up complex sentences.

### Parallel Structure

Items in a series should follow the same grammatical pattern:

**Not parallel:**
> The system can:
> - Monitor server health
> - To generate reports
> - Sending alerts

**Parallel:**
> The system can:
> - Monitor server health
> - Generate reports
> - Send alerts

Parallelism applies to lists, comparisons, and paired elements.

## Punctuation

### Commas

**Serial comma (Oxford comma)**: Use a comma before "and" in a series:

> The system logs errors, warnings, and info messages.

The serial comma prevents ambiguity:

- Without: "I thanked my parents, Batman and Wonder Woman" (suggests parents are superheroes)
- With: "I thanked my parents, Batman, and Wonder Woman" (three separate entities)

**Comma after introductory elements:**

> After the installation completes, restart the server.
>
> However, this approach has limitations.

**Commas around nonessential clauses:**

> The configuration file, which is stored in the root directory, controls authentication.

If the clause is essential to meaning, do not use commas:

> Files that are larger than 10MB are rejected.

### Semicolons

Semicolons join related independent clauses:

> The server handles authentication; the database stores user records.

Semicolons also separate complex list items:

> The team includes developers from New York, USA; London, UK; and Tokyo, Japan.

Use semicolons sparingly. Often, separate sentences work better.

### Colons

Colons introduce lists, explanations, or examples:

> The API supports three methods: GET, POST, and DELETE.
>
> The error has one cause: insufficient permissions.

The text before a colon should be a complete clause:

**Incorrect:**
> The supported methods are: GET, POST, and DELETE.

**Correct:**
> The supported methods are GET, POST, and DELETE.

Or:

> The API supports three methods: GET, POST, and DELETE.

### Hyphens and Dashes

**Hyphens** join compound modifiers before nouns:

> A well-documented API
> User-friendly interface
> Real-time processing

No hyphen after the noun:

> The API is well documented.

**En dashes** (–) indicate ranges:

> Pages 10–15
> 2020–2024

**Em dashes** (—) set off parenthetical elements:

> The configuration file—located in the root directory—controls authentication.

### Apostrophes

**Possessives:**

> The server's response
> The users' permissions (multiple users)

**Contractions** (use sparingly in technical writing):

> Don't use the deprecated method.

For more formal documentation, avoid contractions:

> Do not use the deprecated method.

**Not plurals:**

> ❌ API's are useful
> ✓ APIs are useful

Apostrophes do not form plurals, including for acronyms.

## Common Errors

### Subject-Verb Agreement

Subjects and verbs must agree in number:

**Incorrect:**
> The list of errors are displayed.

**Correct:**
> The list of errors is displayed.

The subject is "list" (singular), not "errors."

**Watch for:**

- Collective nouns (team, data, staff)
- Subjects separated from verbs by phrases
- Compound subjects with "or" or "nor"

### Pronoun Reference

Pronouns must clearly refer to their antecedents:

**Unclear:**
> When the server sends data to the client, it may fail.

What may fail—the server, the client, or the transmission?

**Clear:**
> When the server sends data to the client, the transmission may fail.

When a pronoun could refer to multiple things, use the specific noun instead.

### Dangling Modifiers

Modifiers must connect to what they modify:

**Dangling:**
> After clicking Submit, the form is processed.

The form did not click Submit. The user did.

**Correct:**
> After you click Submit, the system processes the form.

Or:

> After clicking Submit, you see a confirmation message.

### Misplaced Modifiers

Keep modifiers close to what they modify:

**Misplaced:**
> The engineer fixed the bug in the meeting room that crashed the server.

The meeting room did not crash the server.

**Clear:**
> In the meeting room, the engineer fixed the bug that crashed the server.

### Run-on Sentences

Run-on sentences join independent clauses without proper punctuation:

**Run-on:**
> The server crashed we need to restart it.

**Correct:**
> The server crashed. We need to restart it.

Or:

> The server crashed, so we need to restart it.

### Comma Splices

Comma splices join independent clauses with only a comma:

**Comma splice:**
> The server crashed, we need to restart it.

**Correct:**
> The server crashed; we need to restart it.

Or use a conjunction:

> The server crashed, and we need to restart it.

## Technical Writing Grammar Conventions

### Second Person

Technical documentation typically uses second person ("you"):

> You can configure authentication in the Settings panel.

Second person directly addresses the reader and clarifies who performs actions.

### Imperative Mood for Instructions

Procedures use imperative mood (commands):

> Open the configuration file.
> Enter your credentials.
> Click **Submit**.

Imperative mood is direct and clear for instructions.

### Present Tense for Descriptions

Describe systems in present tense:

> The API returns a JSON response.
> The system validates user input.

Use future tense for consequences:

> If validation fails, the system will reject the request.

### Numbers

Conventions for numbers vary by style guide. Common practices:

- Spell out numbers one through nine; use numerals for 10 and above
- Always use numerals with units: 5 MB, 3 seconds
- Use numerals in technical contexts: port 8080, version 2.0
- Spell out numbers that begin sentences

### Capitalization

**Capitalize:**

- Product names: Microsoft Windows, PostgreSQL
- Proper nouns: Internet (when referring to the global network)
- UI elements as they appear: click **Save**, select **File** > **Export**

**Do not capitalize:**

- Generic references: the database, the server
- Common terms: email, website

Follow your style guide for specific conventions.

## Editing for Grammar

### Reading Aloud

Reading text aloud catches errors silent reading misses:

- Awkward phrasing becomes obvious
- Missing words surface
- Run-on sentences become breathless

If it sounds wrong, it probably reads wrong.

### Backward Reading

Reading sentences in reverse order helps catch errors:

- Breaks the flow that lets you skip over mistakes
- Forces attention to each sentence independently
- Effective for catching typos and grammatical errors

### Grammar Tools

Tools can assist but not replace careful review:

- **Grammarly**: Catches common errors
- **Hemingway Editor**: Identifies complex sentences
- **Microsoft Editor**: Built into Word and Edge
- **LanguageTool**: Open-source grammar checker

Tools miss context-dependent errors and may suggest incorrect changes. Use them as aids, not authorities.

### Checklist Review

Check for common issues systematically:

- [ ] Subject-verb agreement
- [ ] Pronoun references clear
- [ ] Modifiers properly placed
- [ ] Parallel structure in lists
- [ ] Comma usage correct
- [ ] Complete sentences (except where fragments are intentional)

## Summary

Grammar in technical writing serves clarity. Focus on the errors that affect comprehension:

- Complete, reasonably sized sentences
- Proper punctuation for clear meaning
- Clear pronoun references
- Correct modifier placement
- Parallel structure for lists and series

Perfect grammar is less important than clear communication, but grammar errors obstruct clarity. Edit carefully, use tools to assist, and maintain the grammar standards your style guide specifies.

---

**Next**: [Style Guides](style-guides.md) covers using and creating style guides for consistent documentation.
