---
title: Cheat Sheets
description: Quick reference guides for technical writing tools and practices.
---

# Cheat Sheets

Quick reference guides for common tools, formats, and practices. Print these or keep them open while you work.

## Markdown Quick Reference

### Basic Syntax

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold text**
*italic text*
~~strikethrough~~

- Unordered list item
- Another item
  - Nested item

1. Ordered list item
2. Another item

[Link text](https://example.com)
![Alt text](image.jpg)

> Blockquote

`inline code`

​```language
code block
​```

---  (horizontal rule)
```

### Extended Syntax

```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |

- [x] Completed task
- [ ] Incomplete task

Term
: Definition

Footnote reference[^1]
[^1]: Footnote content

==highlighted text== (some parsers)

H~2~O (subscript, some parsers)
X^2^ (superscript, some parsers)
```

---

## Git Commands

### Daily Workflow

```bash
# Check status
git status

# Stage changes
git add filename           # Single file
git add .                  # All changes

# Commit
git commit -m "Message"

# Push to remote
git push origin branch-name

# Pull latest changes
git pull origin branch-name
```

### Branching

```bash
# Create and switch to new branch
git checkout -b branch-name

# Switch branches
git checkout branch-name

# List branches
git branch

# Delete branch
git branch -d branch-name
```

### Common Operations

```bash
# View commit history
git log --oneline

# Discard changes to file
git checkout -- filename

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Stash changes
git stash
git stash pop

# View differences
git diff
git diff --staged
```

---

## MkDocs Configuration

### Basic mkdocs.yml

```yaml
site_name: My Documentation
site_url: https://example.com
theme:
  name: material
  palette:
    primary: blue
nav:
  - Home: index.md
  - Guide: guide.md
plugins:
  - search
```

### Common Commands

```bash
# Serve locally
mkdocs serve

# Build static site
mkdocs build

# Deploy to GitHub Pages
mkdocs gh-deploy
```

---

## Style Quick Reference

### Word Choices

| Instead of | Use |
|------------|-----|
| utilize | use |
| in order to | to |
| due to the fact that | because |
| at this point in time | now |
| in the event that | if |
| prior to | before |
| subsequent to | after |
| a large number of | many |
| is able to | can |
| in spite of the fact that | although |

### Sentence Improvements

| Weak | Strong |
|------|--------|
| There are many users who... | Many users... |
| It is important to note that... | Note that... |
| The system is used for processing... | The system processes... |
| Clicking the button will cause... | Click the button to... |
| Users should make sure to... | Users should... |

### Voice and Tone

| Passive (avoid) | Active (prefer) |
|-----------------|-----------------|
| The file is saved by the system | The system saves the file |
| Errors are displayed to the user | The app displays errors |
| The button should be clicked | Click the button |

---

## API Documentation

### REST Endpoint Structure

```markdown
## Endpoint Name

Brief description of what this endpoint does.

### Request

`POST /api/v1/resource`

### Headers

| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token |
| Content-Type | Yes | application/json |

### Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| id | string | Yes | Resource ID |

### Request Body

​```json
{
  "field": "value"
}
​```

### Response

​```json
{
  "id": "123",
  "status": "success"
}
​```

### Error Codes

| Code | Description |
|------|-------------|
| 400 | Bad request |
| 401 | Unauthorized |
| 404 | Not found |
```

---

## Document Structure

### Tutorial Template

```
1. Title (what they'll learn)
2. Prerequisites
3. What you'll build (goal)
4. Steps (numbered, clear outcomes)
5. Verification (confirm success)
6. Next steps
7. Troubleshooting
```

### How-To Template

```
1. Title (How to [verb] [noun])
2. Brief intro (1 sentence)
3. Prerequisites
4. Steps (numbered)
5. Result
6. Related tasks
```

### Reference Template

```
1. Name/Title
2. Brief description
3. Syntax/Usage
4. Parameters/Options
5. Return values
6. Examples
7. Related items
```

---

## Punctuation Quick Reference

### Comma Rules

- Use before coordinating conjunctions in compound sentences
- Use after introductory phrases
- Use between items in a series (Oxford comma recommended)
- Use around non-essential clauses

### Colon Rules

- Use before a list when preceded by a complete sentence
- Use before an explanation or elaboration
- Capitalize after colons only if followed by a complete sentence

### Semicolon Rules

- Use between independent clauses without a conjunction
- Use between items in a series when items contain commas

### Hyphen Rules

- Use in compound modifiers before nouns (user-friendly interface)
- Use with prefixes before proper nouns (pre-Windows)
- Use to avoid confusion (re-create vs recreate)

---

## Number Guidelines

| Situation | Format | Example |
|-----------|--------|---------|
| 1-9 | Spell out | three users |
| 10+ | Numerals | 15 files |
| Starting sentence | Spell out | Twenty users logged in |
| Technical values | Numerals | 8 GB, 3.14 |
| Ranges | Numerals | 5-10 minutes |
| Percentages | Numerals | 25% |
| Large numbers | Numerals with commas | 1,000,000 |

---

## Keyboard Shortcuts

### VS Code

| Action | Windows/Linux | Mac |
|--------|---------------|-----|
| Find | Ctrl+F | Cmd+F |
| Replace | Ctrl+H | Cmd+Option+F |
| Save | Ctrl+S | Cmd+S |
| Toggle comment | Ctrl+/ | Cmd+/ |
| Go to line | Ctrl+G | Cmd+G |
| Quick open | Ctrl+P | Cmd+P |
| Command palette | Ctrl+Shift+P | Cmd+Shift+P |

### Common Applications

| Action | Windows | Mac |
|--------|---------|-----|
| Cut | Ctrl+X | Cmd+X |
| Copy | Ctrl+C | Cmd+C |
| Paste | Ctrl+V | Cmd+V |
| Undo | Ctrl+Z | Cmd+Z |
| Redo | Ctrl+Y | Cmd+Shift+Z |
| Select all | Ctrl+A | Cmd+A |

---

## Documentation Review Checklist

### Content

- [ ] Accurate and current information
- [ ] Appropriate for target audience
- [ ] Complete coverage of topic
- [ ] Clear purpose and scope

### Structure

- [ ] Logical organization
- [ ] Appropriate headings
- [ ] Scannable format
- [ ] Helpful navigation

### Writing

- [ ] Clear and concise
- [ ] Active voice
- [ ] Consistent terminology
- [ ] Correct grammar and spelling

### Technical

- [ ] Working code samples
- [ ] Accurate screenshots
- [ ] Valid links
- [ ] Correct formatting

---

## Print and Reference

Save these cheat sheets for quick reference during your work. Consider printing the sections most relevant to your daily tasks or keeping this page bookmarked for easy access.
