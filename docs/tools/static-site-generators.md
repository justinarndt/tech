---
title: Static Site Generators for Documentation
description: Build documentation websites from source files with static site generators.
---

# Static Site Generators

Static site generators (SSGs) transform source files into complete websites. They provide the foundation for docs-as-code workflows.

## How SSGs Work

1. **Write content** in Markdown or similar
2. **Configure** the site structure and theme
3. **Build** to generate static HTML
4. **Deploy** to any web server

## Popular Documentation SSGs

### MkDocs

Python-based, simple configuration.

```bash
pip install mkdocs-material
mkdocs new my-docs
mkdocs serve
```

**Best for:** Technical documentation, developer docs

### Docusaurus

React-based, feature-rich.

```bash
npx create-docusaurus@latest my-docs classic
cd my-docs
npm start
```

**Best for:** Open source projects, versioned docs

### Hugo

Go-based, extremely fast.

```bash
hugo new site my-docs
cd my-docs
hugo server
```

**Best for:** Large sites, performance-critical

### Sphinx

Python documentation standard.

```bash
pip install sphinx
sphinx-quickstart
make html
```

**Best for:** Python projects, API documentation

## Comparison

| Feature | MkDocs | Docusaurus | Hugo | Sphinx |
|---------|--------|------------|------|--------|
| Language | Python | JavaScript | Go | Python |
| Speed | Fast | Medium | Fastest | Medium |
| Themes | Many | Many | Many | Many |
| Learning curve | Low | Medium | Medium | Higher |
| Versioning | Plugin | Built-in | Manual | Built-in |

## Deployment Options

### Free Hosting

- **GitHub Pages**: Integrated with GitHub
- **Netlify**: Automatic builds, custom domains
- **Vercel**: Fast global CDN
- **Cloudflare Pages**: Edge deployment

### CI/CD Deployment

```yaml
# GitHub Actions for MkDocs
name: Deploy
on:
  push:
    branches: [main]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.x'
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```

## Summary

Static site generators enable modern documentation workflows:

- Choose based on your stack and needs
- MkDocs for simplicity
- Docusaurus for features
- Hugo for speed
- All deploy easily to free hosting
