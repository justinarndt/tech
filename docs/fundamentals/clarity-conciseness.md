---
title: Clarity and Conciseness in Technical Writing
description: Master techniques for writing clear, concise technical documentation including eliminating wordiness, using plain language, and structuring sentences for comprehension.
---

# Clarity and Conciseness

Clear writing transmits information without distortion. Concise writing does so without waste. Together, they form the core skill of technical writing: communicating accurately in as few words as necessary.

Users read documentation to accomplish tasks. Every unclear sentence, every unnecessary word, every ambiguous phrase creates friction. Reduce that friction, and documentation becomes useful instead of tolerable.

## Why Clarity and Conciseness Matter

Technical documentation has jobs to do. Unclear writing fails at those jobs.

**Clear writing:**

- Reduces misunderstanding and errors
- Speeds comprehension
- Improves accessibility for non-native speakers
- Decreases support burden
- Builds user confidence

**Concise writing:**

- Respects user time
- Improves scanability
- Reduces translation costs
- Focuses attention on essential information
- Makes documents maintainable

Consider the cost of unclear documentation: users make mistakes, contact support, abandon products, or implement systems incorrectly. The time spent writing clearly pays dividends in reduced downstream problems.

## Principles of Clear Writing

### Use Plain Language

Plain language communicates to readers on first reading. It uses familiar words, direct structure, and appropriate detail.

**Instead of:**
> Utilize the authentication mechanism to effectuate user verification prior to accessing system resources.

**Write:**
> Authenticate users before they access system resources.

Plain language does not mean simple ideas. Complex concepts can be expressed clearly. Plain language means removing unnecessary complexity in expression.

### Be Specific

Vague language forces readers to guess. Specific language removes ambiguity.

**Vague:**
> The system processes requests quickly.

**Specific:**
> The system processes requests in under 200 milliseconds.

**Vague:**
> Configure the appropriate settings.

**Specific:**
> Set `max_connections` to 100 and `timeout` to 30 seconds.

Specificity requires more effort but produces documentation that actually helps users.

### Prefer Familiar Words

Technical writing sometimes requires specialized terminology. It never requires unnecessarily complex vocabulary.

| Instead of | Use |
|------------|-----|
| utilize | use |
| commence | start, begin |
| terminate | end, stop |
| facilitate | help, enable |
| leverage | use |
| implement | set up, create |
| subsequently | then, later |
| prior to | before |
| in order to | to |
| due to the fact that | because |

Reserve specialized terms for concepts that require them. Use common words for common concepts.

### One Idea Per Sentence

Sentences that pack multiple ideas force readers to untangle meaning.

**Overloaded:**
> The configuration file, which must be placed in the root directory and formatted as YAML, contains settings that control authentication behavior including timeout values, retry limits, and logging levels, all of which can be overridden by environment variables if necessary.

**Clear:**
> Place the configuration file in the root directory. Format it as YAML. The file controls authentication settings: timeout values, retry limits, and logging levels. Environment variables can override these settings.

Shorter sentences are easier to understand, translate, and maintain.

### Front-Load Important Information

Place key information at the beginning of sentences and paragraphs. Readers scan; put important content where scanners look.

**Buried:**
> In order to ensure that the deployment process completes successfully, you should verify that all dependencies are installed before you begin.

**Front-loaded:**
> Verify all dependencies are installed before beginning deployment.

Lead with the action or the key point. Supporting information can follow.

## Techniques for Conciseness

### Eliminate Filler Words

Filler words add length without meaning.

| Remove | Example |
|--------|---------|
| really, very, quite | "very important" → "important" |
| basically, essentially | "basically a wrapper" → "a wrapper" |
| actually | "actually returns" → "returns" |
| in terms of | "in terms of performance" → "for performance" |
| kind of, sort of | "sort of a cache" → "a cache" |

Every word should earn its place. If removing a word does not change meaning, remove it.

### Cut Redundancy

Redundant phrases repeat meaning unnecessarily.

| Redundant | Concise |
|-----------|---------|
| advance planning | planning |
| past history | history |
| end result | result |
| basic fundamentals | fundamentals |
| completely eliminate | eliminate |
| true fact | fact |
| repeat again | repeat |
| new innovation | innovation |

One word with clear meaning beats two words with the same meaning.

### Replace Wordy Phrases

Many wordy phrases have single-word equivalents.

| Wordy | Concise |
|-------|---------|
| at this point in time | now |
| in the event that | if |
| for the purpose of | to, for |
| with regard to | about |
| in spite of the fact that | although |
| has the ability to | can |
| is able to | can |
| in close proximity to | near |
| a large number of | many |
| the majority of | most |

These substitutions shrink documents and improve readability.

### Convert Nouns Back to Verbs

Nominalizations (verbs turned into nouns) create wordiness.

| Nominalized | Direct |
|-------------|--------|
| make a modification | modify |
| perform an analysis | analyze |
| conduct an investigation | investigate |
| make a decision | decide |
| give consideration to | consider |
| provide a description of | describe |

Verbs are more direct than noun phrases describing actions.

### Remove Unnecessary Prepositions

Preposition clutter adds words without meaning.

**Cluttered:**
> The system checks on the status of all of the connected devices.

**Clean:**
> The system checks the status of connected devices.

Audit sentences for prepositional phrases that can be removed or shortened.

## Sentence Structure for Clarity

### Active Voice (Usually)

Active voice identifies who does what. Passive voice obscures actors.

**Passive:**
> The configuration file must be edited by the administrator.

**Active:**
> The administrator must edit the configuration file.

Active voice is usually clearer, shorter, and more direct. Passive voice has legitimate uses (see [Active vs. Passive Voice](active-passive-voice.md)), but default to active.

### Parallel Structure

Parallel structure uses consistent grammatical forms for similar items.

**Not parallel:**
> The system provides:
> - User authentication
> - Monitoring of server health
> - To generate reports automatically

**Parallel:**
> The system provides:
> - User authentication
> - Server health monitoring
> - Automatic report generation

Parallelism helps readers process lists and comparisons quickly.

### Place Modifiers Carefully

Misplaced modifiers create confusion or unintended humor.

**Misplaced:**
> The administrator deleted the file using the API accidentally.

What was accidental—the deletion or using the API?

**Clear:**
> The administrator accidentally deleted the file using the API.

Keep modifiers close to what they modify.

### Avoid Ambiguous Pronouns

Pronouns must have clear antecedents.

**Ambiguous:**
> When the server sends a request to the database, it may time out.

What times out—the server or the database?

**Clear:**
> When the server sends a request to the database, the request may time out.

If a pronoun could refer to multiple things, replace it with the specific noun.

## Readability Testing

Measurable metrics help assess clarity, though they do not guarantee it.

### Readability Scores

Common formulas measure text complexity:

**Flesch-Kincaid Grade Level**
Estimates the U.S. grade level needed to understand text. Technical documentation typically targets grades 8-12, depending on audience.

**Flesch Reading Ease**
Scores from 0-100, with higher scores indicating easier reading. Technical content often scores 30-50.

**Hemingway Editor**
Highlights complex sentences, passive voice, and difficult words.

### Using Readability Metrics

These tools help identify problems:

- Long sentences that should be broken up
- Passive voice that should be active
- Complex words that have simpler alternatives

They do not measure accuracy, organization, or whether content actually helps users. Use them as diagnostic tools, not quality measures.

### Human Testing

The best clarity test is human comprehension:

- Can users complete tasks using the documentation?
- Do users understand what they read?
- Do users make errors due to unclear instructions?

User testing reveals problems that metrics miss.

## Common Clarity Problems

### Jargon Overload

Technical writing requires technical terms. It does not require obscuring meaning behind unnecessary jargon.

**Overloaded:**
> Leverage the synergistic capabilities of our cloud-native, API-first architecture to optimize your DevSecOps workflows.

**Clear:**
> Use our cloud platform's API to improve your development and security processes.

Use technical terms when they are the right terms. Avoid jargon that sounds impressive but communicates poorly.

### Abstract Language

Abstract language forces readers to interpret meaning.

**Abstract:**
> Enhance system capabilities through improved data handling mechanisms.

**Concrete:**
> Process files twice as fast by enabling parallel uploads.

Specific, concrete language communicates more effectively than abstract generalities.

### Hedge Words

Hedge words undermine confidence and add length.

| Hedging | Direct |
|---------|--------|
| may possibly | may |
| it seems that | (cut entirely or state directly) |
| tends to | (state what happens) |
| somewhat | (quantify or cut) |
| in some cases | when X, Y happens |

State things directly. If something is uncertain, explain the conditions that create uncertainty.

### Excessive Qualification

Over-qualified statements become difficult to follow.

**Over-qualified:**
> In most typical situations, under normal operating conditions, the system will generally tend to respond within approximately five seconds in the majority of cases.

**Direct:**
> The system typically responds within five seconds.

Include necessary qualifications. Cut unnecessary hedging.

## Practice Exercises

Improving clarity requires practice. Try these exercises:

**Exercise 1: Simplify this sentence**
> The implementation of the new authentication system will necessitate the modification of existing user credentials in order to facilitate compatibility with the updated security protocols.

**Exercise 2: Make this specific**
> Configure the system settings appropriately before deployment.

**Exercise 3: Cut wordiness**
> At this point in time, we are in the process of conducting an investigation into the root cause of the error that has occurred in the system.

Answers vary, but each exercise should produce shorter, clearer sentences.

## Summary

Clear writing transmits information without distortion. Concise writing does so efficiently. Together, they make documentation usable.

Key techniques:

- Use plain language and familiar words
- Be specific rather than vague
- Keep sentences focused on single ideas
- Front-load important information
- Eliminate filler, redundancy, and wordiness
- Use active voice and parallel structure
- Test readability and comprehension

Every sentence should communicate as clearly and briefly as possible. Users read documentation to accomplish tasks, not to admire prose. Serve them well.

---

**Next**: [Active vs. Passive Voice](active-passive-voice.md) explores when to use each voice for maximum clarity.
