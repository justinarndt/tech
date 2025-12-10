---
title: Linting and Quality Tools
description: Automated tools for maintaining documentation style and quality.
---

# Linting and Quality

Automated linting catches style issues, spelling errors, and formatting problems before they reach readers. Quality tools maintain consistency across documentation.

## Prose Linting

### Vale

Customizable prose linter.

**Features:**
- Style guide enforcement
- Custom rules
- CI/CD integration

**Configuration:**
```yaml
# .vale.ini
StylesPath = styles
MinAlertLevel = warning

[*.md]
BasedOnStyles = Google, write-good
```

### Write-Good

Catches common writing issues:

- Passive voice
- Weasel words
- Clichés

## Markdown Linting

### markdownlint

Enforces Markdown formatting:

```yaml
# .markdownlint.yml
default: true
MD013: false  # Line length
MD033: false  # Inline HTML
```

### remark-lint

Pluggable Markdown linter for Node.js projects.

## Spell Checking

### cSpell

Code-aware spell checker:

```json
{
  "words": ["webhook", "microservice"],
  "ignoreWords": ["yaml", "json"]
}
```

### Aspell/Hunspell

Traditional spell checkers for CI pipelines.

## Link Checking

### linkchecker

Validates all links in documentation:

```bash
linkchecker https://docs.example.com
```

### markdown-link-check

Check links in Markdown files:

```bash
markdown-link-check README.md
```

## CI Integration

Add quality checks to your pipeline:

```yaml
# GitHub Actions example
name: Docs Quality

on: [push, pull_request]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Vale linting
        uses: errata-ai/vale-action@v2
      - name: Link check
        run: |
          npm install -g markdown-link-check
          find docs -name "*.md" -exec markdown-link-check {} \;
```

## Summary

Quality tools ensure consistent documentation:

- Lint prose for style consistency
- Check Markdown formatting
- Validate spelling
- Verify links work
- Automate in CI/CD

Catching issues automatically improves overall documentation quality.
