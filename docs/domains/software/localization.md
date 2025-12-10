---
title: Localization and Internationalization
description: Writing documentation that works across languages and cultures.
---

# Localization and Internationalization

Internationalization (i18n) prepares documentation for translation. Localization (l10n) adapts it for specific markets. Together, they help your documentation reach global audiences.

## Understanding i18n and l10n

### Internationalization (i18n)

Preparing content for translation:

- Writing translation-friendly content
- Separating text from code
- Supporting multiple character sets
- Designing flexible layouts

### Localization (l10n)

Adapting for specific locales:

- Translating text
- Adapting formats (dates, numbers, currency)
- Adjusting cultural references
- Modifying images and examples

## Writing for Translation

### Use Simple, Clear Language

Complex sentences are hard to translate:

```markdown
# Hard to Translate
Notwithstanding the aforementioned considerations,
users should endeavor to utilize the primary interface.

# Easy to Translate
Use the main interface for best results.
```

### Avoid Idioms and Slang

Idioms don't translate:

| Avoid | Use Instead |
|-------|-------------|
| Hit the ground running | Start quickly |
| Out of the box | By default |
| Bells and whistles | Extra features |
| Up and running | Working |
| Piece of cake | Easy |

### Keep Sentences Short

Short sentences translate better:

```markdown
# Too Long
When you click the submit button, which is located at
the bottom of the form, the system will process your
request and send you a confirmation email within a
few minutes.

# Better
Click Submit at the bottom of the form.
You'll receive a confirmation email within a few minutes.
```

### Avoid Ambiguous Words

Words with multiple meanings cause problems:

| Ambiguous | Clear |
|-----------|-------|
| Set (noun or verb?) | Configure / Collection |
| Right (correct or direction?) | Correct / Right side |
| Table (furniture or chart?) | Chart / Data table |

### Don't Embed Text in Images

Screenshots with text require recreation:

```markdown
# Bad
[Screenshot with English button labels]

# Better
[Screenshot with numbered callouts]

1. Settings button
2. Save option
3. Cancel option
```

## Structuring Translatable Content

### Separate Text from Code

Keep strings in resource files:

```yaml
# strings.yml
en:
  welcome: "Welcome to the app"
  login: "Sign in"
  logout: "Sign out"

es:
  welcome: "Bienvenido a la aplicación"
  login: "Iniciar sesión"
  logout: "Cerrar sesión"
```

### Use Variables Carefully

Account for word order changes:

```markdown
# Problematic
"Hello " + username + ", you have " + count + " messages"

# Better
"Hello {username}, you have {count} messages"
# Translators can reorder: "{count} mensajes para {username}"
```

### Handle Plurals

Different languages have different plural rules:

```yaml
# English: singular/plural
messages:
  one: "You have 1 message"
  other: "You have {count} messages"

# Russian: singular/few/many
messages:
  one: "У вас 1 сообщение"
  few: "У вас {count} сообщения"
  many: "У вас {count} сообщений"
```

## Locale-Specific Formatting

### Dates and Times

Formats vary by region:

| Locale | Date Format | Time Format |
|--------|-------------|-------------|
| US | MM/DD/YYYY | 12-hour (AM/PM) |
| UK | DD/MM/YYYY | 24-hour |
| Germany | DD.MM.YYYY | 24-hour |
| Japan | YYYY/MM/DD | 24-hour |

```markdown
# Bad
The meeting is on 01/02/2024 at 3:00 PM.

# Better
The meeting is on January 2, 2024 at 3:00 PM (UTC).
```

### Numbers and Currency

Number formats differ:

| Locale | Number | Currency |
|--------|--------|----------|
| US | 1,234.56 | $1,234.56 |
| Germany | 1.234,56 | 1.234,56 € |
| France | 1 234,56 | 1 234,56 € |

### Units of Measurement

Use appropriate units:

| Region | Length | Temperature | Weight |
|--------|--------|-------------|--------|
| US | Inches, feet | Fahrenheit | Pounds |
| Most others | Centimeters, meters | Celsius | Kilograms |

```markdown
# For Global Audience
The maximum file size is 100 MB (100 megabytes).
```

## Translation Workflow

### Content Preparation

1. Write in source language (usually English)
2. Review for translation friendliness
3. Extract translatable strings
4. Create glossary of key terms
5. Prepare style guide for translators

### Translation Process

1. Send content to translators
2. Translators work with translation memory
3. Review translations for accuracy
4. Perform linguistic testing
5. Publish localized content

### Translation Memory

Reuse previous translations:

```markdown
# Benefits
- Consistency across documents
- Faster translation
- Lower costs
- Maintained terminology
```

## Documentation Structure

### Localized Documentation

Options for organizing translated content:

**Subdirectories:**
```
docs/
├── en/
│   ├── getting-started.md
│   └── api.md
├── es/
│   ├── getting-started.md
│   └── api.md
└── ja/
    ├── getting-started.md
    └── api.md
```

**Subdomains:**
```
docs.example.com
es.docs.example.com
ja.docs.example.com
```

**Language Selector:**
```
docs.example.com?lang=en
docs.example.com?lang=es
```

### Handling Untranslated Content

Options when translations aren't ready:

- Show source language with "not yet translated" notice
- Link to source language version
- Machine translate with disclaimer
- Hide untranslated sections

## Tools and Platforms

### Translation Management

- **Crowdin**: Developer-focused translation platform
- **Lokalise**: Translation management for teams
- **Transifex**: Continuous localization platform
- **Phrase**: Localization for software

### Static Site Generators

Built-in i18n support:

- **Docusaurus**: Native i18n support
- **MkDocs**: i18n plugin available
- **Hugo**: Built-in multilingual support

### Quality Assurance

- **Linting**: Check for i18n issues
- **Pseudo-localization**: Test layout with fake translations
- **Linguistic testing**: Verify translations in context

## Common Challenges

### Text Expansion

Translated text is often longer:

| Language | Expansion from English |
|----------|----------------------|
| German | +30% |
| French | +20% |
| Spanish | +25% |
| Chinese | -50% (but wider characters) |

Design UI with expansion room.

### Right-to-Left Languages

Arabic, Hebrew, and others read right to left:

- Mirror layouts
- Adjust navigation
- Test thoroughly

### Character Support

Ensure your system supports:

- Extended Latin characters (é, ñ, ü)
- Non-Latin scripts (日本語, العربية, 中文)
- Special characters and symbols

## Summary

Effective internationalization:

- Writes clear, simple content
- Avoids idioms and cultural assumptions
- Structures content for translation
- Uses appropriate formatting for each locale
- Supports efficient translation workflows

Good i18n practices help your documentation reach global audiences effectively.
