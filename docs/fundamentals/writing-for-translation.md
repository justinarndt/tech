---
title: Writing for Translation and Localization
description: Learn how to write technical documentation that translates well, reducing costs and improving quality for international audiences.
---

# Writing for Translation

Documentation written for translation is easier to translate accurately, costs less to localize, and serves international users better. Good source content is the foundation of good translations.

## Translation Fundamentals

### Translation vs. Localization

**Translation** converts text from one language to another.

**Localization** adapts content for a specific locale, including:

- Language translation
- Cultural adaptation
- Date, time, and number formats
- Currency and measurements
- Images and examples
- Legal and regulatory considerations

Documentation often requires localization, not just translation.

### How Translation Works

Modern translation workflows typically involve:

1. **Source content** prepared in original language
2. **Translation memory** matches with previously translated content
3. **Machine translation** provides initial translations
4. **Human review** corrects and improves translations
5. **Quality assurance** verifies accuracy and consistency

Source content quality affects every step of this process.

### Translation Costs

Translation costs depend on:

- **Word count**: More words = higher cost
- **Repetition**: Repeated content translates once with translation memory
- **Complexity**: Unclear content requires more translator time
- **Terminology**: Inconsistent terms increase effort
- **Formatting**: Complex formatting adds overhead

Writing for translation reduces costs across all these factors.

## Writing Principles

### Clarity

Clear source content produces clear translations:

**Unclear:**
> You can get started by setting this up first.

**Clear:**
> Before using the application, complete the initial configuration.

Vague language creates ambiguity translators must resolve, often incorrectly.

### Consistency

Consistent language enables translation memory:

**Inconsistent:**
> Click **Save** to save changes.
> Press **Save** to store your modifications.
> Select **Save** to preserve updates.

**Consistent:**
> Click **Save** to save changes.
> Click **Save** to save changes.
> Click **Save** to save changes.

Translation memory matches identical segments. Variations require separate translations.

### Simplicity

Simple sentences translate more accurately:

**Complex:**
> When the system, which monitors all incoming requests that are authenticated using the methods described in section 3, detects an anomaly, it triggers the alert system.

**Simple:**
> The system monitors authenticated incoming requests. When it detects an anomaly, it triggers an alert.

Complex sentences increase translation errors and costs.

## Specific Techniques

### Complete Sentences

Write complete sentences that translate independently:

**Incomplete:**
> To save, click **Save**. To cancel, **Cancel**.

**Complete:**
> To save your changes, click **Save**. To cancel your changes, click **Cancel**.

Complete sentences provide context translators need.

### Avoid Sentence Fragments in UI

UI strings need complete context:

**Fragment:**
> "are required"

Required for what? In what context? Translators cannot know.

**Complete:**
> "These fields are required."

Complete sentences translate accurately.

### Avoid Placeholder Grammar Issues

Placeholders can create grammar problems:

**Problematic:**
> "Delete {item}?"

In some languages, the word for "delete" changes based on the gender or case of the item being deleted.

**Better:**
> "Do you want to delete {item}?"

Full sentences provide grammatical context.

### Control Sentence Length

Long sentences cause problems:

- More opportunities for translation errors
- Difficult to match with translation memory
- Harder for translators to understand

Target: 20-25 words maximum per sentence.

### Avoid Idioms and Colloquialisms

Idiomatic expressions often do not translate:

**Idiomatic:**
> This feature is a piece of cake to use.
> Let's hit the ground running.
> The ball is in your court.

**Direct:**
> This feature is easy to use.
> Let's start immediately.
> You need to take action.

### Avoid Humor

Humor rarely translates well:

- Puns do not work across languages
- Cultural references may not be understood
- Sarcasm can be misinterpreted

Keep technical documentation straightforward.

### Avoid Culturally Specific References

References may not translate:

**Culturally specific:**
> As easy as apple pie
> A Super Bowl of data
> Like finding a needle in a haystack

**Universal:**
> Very easy
> A large amount of data
> Very difficult to find

### Use Articles Consistently

Articles (a, an, the) affect translation:

**Missing articles:**
> Click button to continue.

**With articles:**
> Click the button to continue.

Articles clarify meaning and help translators.

### Avoid Ambiguous Words

Some words have multiple meanings:

| Word | Possible meanings |
|------|-------------------|
| free | no cost, unrestricted, available |
| set | configure, collection, place |
| right | correct, direction, permission |
| table | furniture, data structure, postpone |

Use specific words to reduce ambiguity.

### Subject-Verb-Object Order

Maintain clear grammatical structure:

**Unclear:**
> Into the configuration file enter your settings.

**Clear:**
> Enter your settings into the configuration file.

Standard word order translates more reliably.

## Terminology Management

### Consistent Terms

Use identical terms for identical concepts:

- Create a glossary of key terms
- Use terms consistently throughout documentation
- Provide approved translations for each term

See [Terminology Management](terminology-management.md) for detailed guidance.

### Translatable Terms

Some terms should not be translated:

- Product names
- Feature names (usually)
- Technical standards
- Code identifiers

Document which terms remain in English.

### Avoid Acronyms When Possible

Acronyms may not be meaningful in other languages:

**Acronym-heavy:**
> Configure the DNS settings in the UI via the API or CLI.

**Expanded:**
> Configure the Domain Name System settings in the user interface using the application programming interface or command-line interface.

**Balanced:**
> Configure DNS (Domain Name System) settings using the user interface, API, or command line.

Expand acronyms on first use.

## Formatting Considerations

### Text Expansion

Translated text is often longer than English:

| Language | Typical expansion |
|----------|-------------------|
| German | +30% |
| French | +20% |
| Spanish | +25% |
| Russian | +30% |
| Japanese | -10% to +20% |
| Chinese | -20% to +10% |

Design layouts that accommodate expansion.

### Text in Images

Avoid embedding text in images:

- Text cannot be extracted for translation
- Images must be recreated for each language
- Increases cost and maintenance burden

Use captions, callouts, or overlays instead.

### Concatenated Strings

Do not build sentences from parts:

**Problematic:**
```javascript
message = "You have " + count + " items in your " + location;
```

Word order differs across languages. The translated pieces may not form a valid sentence.

**Better:**
```javascript
message = "You have {count} items in your {location}.";
// Translators receive the complete sentence with placeholders
```

### Date and Time Formats

Use locale-appropriate formats:

| Format | US | UK | Germany | Japan |
|--------|----|----|---------|-------|
| Date | 12/31/2024 | 31/12/2024 | 31.12.2024 | 2024/12/31 |
| Time | 3:00 PM | 15:00 | 15:00 | 15:00 |

Use localization libraries rather than hardcoded formats.

### Numbers and Currency

Format appropriately:

| Element | US | Germany | India |
|---------|----| --------|-------|
| Thousands | 1,000 | 1.000 | 1,000 |
| Decimal | 1.5 | 1,5 | 1.5 |
| Currency | $100 | 100 € | ₹100 |

## Working with Translators

### Provide Context

Help translators understand content:

- Screenshots showing where text appears
- Explanations of technical concepts
- Description of the target audience
- Style and tone guidance

### Translation Notes

Add notes for translators:

```html
<!-- TRANSLATOR NOTE: "Cloud" here refers to cloud computing, not weather -->
<p>Store your data in the Cloud.</p>
```

### Review Process

Include native speakers in review:

- Technical accuracy review
- Linguistic quality review
- Cultural appropriateness review

### Feedback Loop

Learn from translation issues:

- Track questions translators ask
- Update source content to prevent recurring problems
- Improve glossaries based on translation experience

## Summary

Writing for translation improves source content and reduces localization costs:

- **Write clearly** with complete, simple sentences
- **Be consistent** in terminology and phrasing
- **Avoid idioms** and culturally specific references
- **Manage terminology** with glossaries and approved terms
- **Consider formatting** including text expansion and images
- **Support translators** with context and feedback

Good source content is the foundation of good translations. Invest in translation-friendly writing to serve international users effectively.

---

**Next**: [Quality Assurance](quality-assurance.md) covers processes for maintaining documentation quality.
