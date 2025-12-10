
Requirements for requirements.txt
mkdocs-material[imaging]>=9.5.0
mkdocs-minify-plugin>=0.8.0
mkdocs-git-revision-date-localized-plugin>=1.2.0



# -----------------------------------------------------------------------------
# MASTER CONFIGURATION
# -----------------------------------------------------------------------------
site_name: Tech Writer Portfolio
site_url: https://yourusername.github.io/my-docs-portfolio/ # CHANGE THIS
site_author: Your Name
site_description: >-
  Professional technical writing portfolio and documentation hub.
  Specializing in API documentation, user guides, and system architecture.

# Repository info (Edit this to point to your actual repo)
repo_name: GitHub
repo_url: https://github.com/yourusername/my-docs-portfolio
edit_uri: edit/main/docs/

# -----------------------------------------------------------------------------
# THEME CONFIGURATION (Material for MkDocs)
# -----------------------------------------------------------------------------
theme:
  name: material
  language: en
  
  # Branding (Place these images in docs/assets/)
  # If you don't have them yet, comment these lines out to prevent build errors
  # logo: assets/logo.png
  # favicon: assets/favicon.png

  # Mobile-First & UX Features
  features:
    - navigation.tabs        # Top-level tabs for sections
    - navigation.tabs.sticky # Tabs remain visible on scroll
    - navigation.top         # Back-to-top button
    - navigation.tracking    # URL updates as you scroll
    - navigation.indexes     # Section headers are clickable pages
    - navigation.instant     # SPA-like loading (Instant navigation)
    - toc.follow             # Table of Contents follows scroll
    - content.code.copy      # Copy button on code blocks
    - content.tooltips       # Hover tooltips

  # Color Palette (System preference detection + Toggle)
  palette:
    # Palette toggle for automatic mode
    - media: "(prefers-color-scheme)"
      toggle:
        icon: material/brightness-auto
        name: Switch to light mode

    # Palette toggle for light mode
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: indigo 
      accent: indigo
      toggle:
        icon: material/brightness-7
        name: Switch to dark mode

    # Palette toggle for dark mode
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      primary: indigo
      accent: indigo
      toggle:
        icon: material/brightness-4
        name: Switch to light mode

  # Footer Social Links
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/yourusername
    - icon: fontawesome/brands/linkedin
      link: https://linkedin.com/in/yourname
    - icon: fontawesome/solid/paper-plane
      link: mailto:youremail@example.com

# -----------------------------------------------------------------------------
# PLUGINS (SEO & Performance)
# -----------------------------------------------------------------------------
plugins:
  - search:
      separator: '[\s\-\.]+'
  
  # Auto-generate Social Media Preview Cards
  - social:
      cards_layout_options:
        background_color: "#1f2022"
  
  # HTML/JS Minification for Speed
  - minify:
      minify_html: true
  
  # "Last Updated" Date on pages
  - git-revision-date-localized:
      type: date
      fallback_to_build_date: true

# -----------------------------------------------------------------------------
# MARKDOWN EXTENSIONS
# -----------------------------------------------------------------------------
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.inlinehilite
  - pymdownx.tabbed:
      alternate_style: true
  - pymdownx.tasklist:
      custom_checkbox: true
  - toc:
      permalink: true
  - attr_list
  - md_in_html

# -----------------------------------------------------------------------------
# CUSTOM CSS
# -----------------------------------------------------------------------------
extra_css:
  - stylesheets/extra.css

copyright: Copyright &copy; 2025 Your Name


hide:navigationWelcome to My Documentation Hub<div class="hero-section"><p class="hero-text">I bridge the gap between complex code and human understanding.</p><a href="portfolio/" class="md-button md-button--primary">View Portfolio</a><a href="about/" class="md-button">About Me</a></div>!!! quote """Documentation is a love letter that you write to your future self." — Damian ConwayWhat I Do<div class="grid cards" markdown>:material-api: API DocumentationREST, GraphQL, and gRPC documentation using OpenAPI/Swagger and slate-style layouts.:material-book-open-page-variant: User GuidesComprehensive manuals focusing on user adoption, clarity, and task-based learning.:material-sitemap: Information ArchitectureStructuring knowledge bases for discoverability and logical flow.</div>Latest UpdatesDocumentCategoryLast UpdatedGetting Started with DockerGuides2025-01-15Authentication API v2API2025-01-10Cloud Security Best PracticesWhitepaper2024-12-20


/* Subtle styling tweaks for a more "Product" feel 
   rather than a default "Wiki" feel.
*/

/* Center the Hero section on the homepage */
.hero-section {
    text-align: center;
    padding: 4rem 0;
}

.hero-text {
    font-size: 1.5rem;
    font-weight: 300;
    margin-bottom: 2rem;
    color: var(--md-default-fg-color--light);
}

/* Make the cards on the homepage look clickable and interactive */
.md-typeset .grid.cards > ul > li {
    border: 1px solid var(--md-default-fg-color--lightest);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.md-typeset .grid.cards > ul > li:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

/* Hide the "Made with Material for MkDocs" footer for a cleaner look */
.md-footer-meta .md-footer-copyright {
    margin-top: 0;
}
.md-footer-meta .md-copyright__highlight {
    display: none;
}




name: Publish Docs
on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0 # Required for git-revision-date-localized-plugin

      - name: Configure Git Credentials
        run: |
          git config user.name github-actions[bot]
          git config user.email 41898282+github-actions[bot]@users.noreply.github.com

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: 3.x
          cache: pip

      - name: Install dependencies
        run: pip install -r requirements.txt

      # The imaging plugin requires Cairo/GTK system libraries
      - name: Install system dependencies (for social cards)
        run: |
          sudo apt-get update
          sudo apt-get install -y libcairo2-dev libfreetype6-dev libffi-dev libjpeg-dev libpng-dev

      - name: Build and Deploy
        run: mkdocs gh-deploy --force
		
		
	