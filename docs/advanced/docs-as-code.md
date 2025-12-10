---
title: Docs as Code
description: Managing documentation using software development practices.
---

# Docs as Code

Docs as code applies software development practices to documentation. By treating docs like code, teams gain version control, automation, and integration with development workflows.

## Core Principles

### What Docs as Code Means

**Store in version control:**
Documentation lives in Git alongside code.

**Write in plain text:**
Use Markdown, AsciiDoc, or reStructuredText.

**Build with tools:**
Generate sites from source files.

**Review through pull requests:**
Same workflow as code changes.

**Deploy automatically:**
CI/CD publishes documentation.

### Benefits

| Benefit | Description |
|---------|-------------|
| Version control | Track changes, blame, history |
| Collaboration | Pull requests, branches |
| Automation | CI/CD, testing, deployment |
| Integration | Lives with the code |
| Quality | Review process, linting |
| Portability | Plain text, standard formats |

## Setting Up Docs as Code

### Repository Structure

```
project/
├── docs/
│   ├── index.md
│   ├── getting-started/
│   │   ├── index.md
│   │   ├── installation.md
│   │   └── quick-start.md
│   ├── guides/
│   │   └── ...
│   └── reference/
│       └── ...
├── src/                  # Application code
├── mkdocs.yml           # Documentation config
├── .github/
│   └── workflows/
│       └── docs.yml     # CI/CD workflow
└── README.md
```

### Tool Selection

Choose your stack:

**Static Site Generator:**
- MkDocs (Python)
- Docusaurus (JavaScript)
- Hugo (Go)
- Sphinx (Python)

**Markup Format:**
- Markdown (most common)
- AsciiDoc (more features)
- reStructuredText (Sphinx)

**Hosting:**
- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages

### Basic Configuration

```yaml
# mkdocs.yml
site_name: My Project Docs
site_url: https://docs.example.com

nav:
  - Home: index.md
  - Getting Started:
    - Installation: getting-started/installation.md
    - Quick Start: getting-started/quick-start.md
  - API Reference: reference/api.md

theme:
  name: material

plugins:
  - search
  - git-revision-date
```

## Git Workflow for Docs

### Branching Strategy

```markdown
## Branch Naming

feature/add-api-docs       # New documentation
fix/typo-installation      # Small fixes
update/v2-migration        # Updates for new version

## Workflow

1. Create branch from main
2. Make changes
3. Open pull request
4. Get review
5. Merge to main
6. Auto-deploy
```

### Commit Messages

Write clear commit messages:

```markdown
# Good commit messages

docs: add installation guide for macOS
docs: fix broken link in API reference
docs: update screenshots for new UI
docs: reorganize getting started section

# Conventional commits format
docs(api): add authentication examples
docs(install): clarify system requirements
fix(docs): correct code sample in tutorial
```

### Pull Request Process

```markdown
## Documentation PR Template

## Description
Brief description of documentation changes.

## Type of Change
- [ ] New documentation
- [ ] Update existing documentation
- [ ] Fix error or typo
- [ ] Restructure/reorganize

## Checklist
- [ ] Follows style guide
- [ ] Links verified
- [ ] Code samples tested
- [ ] Screenshots current
- [ ] Spell check passed

## Related Issues
Closes #123
```

## Automation

### CI/CD Pipeline

```yaml
# .github/workflows/docs.yml
name: Documentation

on:
  push:
    branches: [main]
    paths:
      - 'docs/**'
      - 'mkdocs.yml'
  pull_request:
    paths:
      - 'docs/**'
      - 'mkdocs.yml'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - uses: actions/setup-python@v5
        with:
          python-version: '3.12'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Build docs
        run: mkdocs build --strict

      - name: Deploy
        if: github.ref == 'refs/heads/main'
        run: mkdocs gh-deploy --force
```

### Quality Checks

Automate quality assurance:

```yaml
# Add to CI pipeline

- name: Lint Markdown
  run: |
    npm install -g markdownlint-cli
    markdownlint 'docs/**/*.md'

- name: Check links
  run: |
    npm install -g markdown-link-check
    find docs -name '*.md' -exec markdown-link-check {} \;

- name: Spell check
  run: |
    npm install -g cspell
    cspell 'docs/**/*.md'

- name: Vale linting
  uses: errata-ai/vale-action@v2
  with:
    files: docs/
```

### Preview Deployments

Preview changes before merging:

```yaml
# Deploy preview for PRs
- name: Deploy Preview
  if: github.event_name == 'pull_request'
  uses: netlify/actions/cli@master
  with:
    args: deploy --dir=site --alias=pr-${{ github.event.number }}
  env:
    NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_TOKEN }}
    NETLIFY_SITE_ID: ${{ secrets.NETLIFY_SITE_ID }}
```

## Writing Workflow

### Local Development

Set up local preview:

```bash
# Install dependencies
pip install mkdocs-material

# Start local server
mkdocs serve

# Preview at http://localhost:8000
```

### Content Development

```markdown
## Writing Process

1. Create branch
   git checkout -b feature/new-tutorial

2. Start local server
   mkdocs serve

3. Write content
   - Create/edit Markdown files
   - Preview changes live

4. Commit frequently
   git add docs/tutorials/new-feature.md
   git commit -m "docs: add new feature tutorial"

5. Push and create PR
   git push origin feature/new-tutorial
   # Create PR on GitHub

6. Address review feedback
   # Make changes, push, repeat

7. Merge when approved
```

### Editor Setup

Configure your editor for docs:

```json
// VS Code settings.json
{
  "editor.wordWrap": "on",
  "editor.rulers": [80],
  "markdownlint.config": {
    "MD013": false,
    "MD033": false
  },
  "cSpell.words": [
    "mkdocs",
    "docusaurus"
  ]
}
```

## Code Sample Management

### Testable Code Samples

Keep code samples working:

```markdown
## Approaches

### Inline with testing
Include samples in test suite that also appear in docs.

### External includes
Reference code files that are tested separately.

### Extraction scripts
Extract samples from tested code into docs.
```

### Code Extraction

```python
# scripts/extract_examples.py
import re

def extract_examples(source_file, output_dir):
    """Extract code between # docs:start and # docs:end markers."""
    with open(source_file) as f:
        content = f.read()

    pattern = r'# docs:start:(\w+)\n(.+?)# docs:end:\1'
    matches = re.findall(pattern, content, re.DOTALL)

    for name, code in matches:
        with open(f'{output_dir}/{name}.py', 'w') as f:
            f.write(code.strip())
```

## Collaboration Patterns

### Developer Contributions

Make it easy for developers to contribute:

```markdown
## Contributing to Documentation

### Quick Fixes
1. Click "Edit this page" link
2. Make your change on GitHub
3. Submit pull request

### Larger Changes
1. Clone the repository
2. Create a branch
3. Make changes locally
4. Test with `mkdocs serve`
5. Submit pull request

### What We Need Help With
- Fixing typos and errors
- Improving explanations
- Adding examples
- Updating screenshots
```

### Review Guidelines

```markdown
## Documentation Review Checklist

### Content
- [ ] Technically accurate
- [ ] Complete (covers the topic)
- [ ] Clear and understandable
- [ ] Appropriate for audience

### Style
- [ ] Follows style guide
- [ ] Consistent terminology
- [ ] Proper formatting

### Technical
- [ ] Code samples work
- [ ] Links valid
- [ ] Images display correctly
- [ ] Build succeeds
```

## Versioning Documentation

### Version Strategies

```markdown
## Approaches

### Latest only
- Single version of docs
- Matches latest product release
- Simplest to maintain

### Multiple versions
- Docs per major version
- Users select version
- More complex

### Branch per version
docs-v1 branch → v1.example.com
docs-v2 branch → v2.example.com
main branch → latest.example.com
```

### Implementation

```yaml
# mkdocs.yml with mike for versioning
plugins:
  - mike

# Deploy commands
mike deploy --push --update-aliases 2.0 latest
mike deploy --push 1.0
mike set-default --push latest
```

## Summary

Docs as code provides:

- Version control and history
- Collaboration through pull requests
- Automated testing and deployment
- Integration with development workflows
- Quality through automation

By treating documentation like code, teams can maintain higher quality with less manual effort.
