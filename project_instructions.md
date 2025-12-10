# Technical Writing Mastery: Project Bible

## 1. Project Overview

### 1.1 Vision and Goals
This Project Bible serves as the definitive blueprint for building **TechWriteExpert.com** (or your GitHub Pages subdomain), a comprehensive MKDocs-powered static website positioning you as the world's foremost authority on technical writing across all domains. Launched in late 2025, the site will cover **every facet** of technical writing with unprecedented depth, blending timeless fundamentals with cutting-edge trends like AI-assisted documentation and quantum-safe software specs.

**Core Objectives**:
- **Expert Positioning**: 100+ pages of original, in-depth content (1,500-4,000 words/page) showcasing your 20+ years of experience in software, medical, finance, and emerging AI domains. Include case studies, anonymized client wins (e.g., "Reduced API doc errors by 40% for a Fortune 500 fintech"), and expert endorsements via embedded testimonials.
- **Organic SEO Dominance**: Target 100+ long-tail keywords to capture 50,000+ annual organic visitors by Q4 2026. Focus on high-intent queries (e.g., "AI prompt engineering for technical docs 2025") for conversions.
- **Monetization**: Every page features a non-intrusive sidebar/footer widget: LinkedIn profile embed (via LinkedIn's official badge code) + "Hire Me" CTA button linking to Calendly/Indeed for consultations ($250/hr freelance rates). Goal: 10-20 leads/month.
- **User Experience**: Ultra-clean, professional design optimized for mobile (80% of tech pros browse on-the-go). Load time <2s via GitHub Pages CDN.
- **Scalability**: GitHub Actions for CI/CD; easy to add pages quarterly (e.g., post-2026 trends like neural doc generation).

**Success Metrics**:
- Traffic: 5K/month initial (via SEO), scaling to 20K+.
- Engagement: Avg. session 3-5 mins; 20% bounce rate.
- Conversions: 5% CTA click-through.
- Ranking: Top 3 for 70% of target keywords within 6 months (track via Google Search Console/Ahrefs).

### 1.2 Target Audience
- Aspiring technical writers (entry-level to mid-career).
- Tech teams (devs, PMs) needing doc overhauls.
- Domain specialists (e.g., AI engineers documenting LLMs).
- Freelance hunters and corporate hiring managers.
- Global: 60% US/EU, 20% Asia, 20% elsewhere; multilingual hooks for future localization.

### 1.3 Timeline and Milestones
- **Week 1-2**: MKDocs setup, theme config, 10 core pages.
- **Week 3-6**: Content creation (20 pages/week); keyword optimization.
- **Week 7**: GitHub Actions deploy; SEO audit.
- **Week 8**: Launch; promote via LinkedIn/X/Write the Docs.
- **Ongoing**: Quarterly updates (e.g., AI ethics addendum in Q1 2026).

## 2. Site Architecture and Navigation

MKDocs with Material for MkDocs theme (v9.5+ as of Dec 2025) for responsive, mobile-first design. Hierarchical nav via `mkdocs.yml` for intuitive browsing. Total: **102 pages** (homepage + 101 content pages) across 10 sections. Use shortcodes for reusables (e.g., CTA widget).

### 2.1 Navigation Structure (YAML Snippet)
```yaml
nav:
  - Home: index.md
  - Introduction: intro/
    - What Is Technical Writing?: intro/what-is.md
    - Role of Technical Writers: intro/role.md
    - vs. Other Writing: intro/comparisons.md
  - Fundamentals: fundamentals/
    - [18 sub-pages, e.g., audience-analysis.md]
  - Document Types: types/
    - [20 sub-pages, e.g., user-manuals.md]
  - Tools & Tech: tools/
    - [12 sub-pages, e.g., markdown-editors.md]
  - Domain-Specific: domains/
    - Software & AI: domains/software-ai/
      - [15 sub-pages, e.g., ai-doc-prompts.md]
    - Medical: domains/medical/ [8 sub-pages]
    - Engineering: domains/engineering/ [8 sub-pages]
    - Finance: domains/finance/ [7 sub-pages]
    - Other Domains: domains/other/ [5 sub-pages]
  - Advanced Skills: advanced/
    - [10 sub-pages, e.g., ai-trends-2026.md]
  - Career Building: career/
    - [8 sub-pages, e.g., freelance-rates.md]
  - Resources: resources/
    - [8 sub-pages, e.g., templates.md]
```
- **Homepage**: Hero section ("Master Technical Writing: Expert Guides for 2025 & Beyond"), featured pages carousel, newsletter signup (via Buttondown embed), CTA widget.
- **Search**: Built-in MKDocs search + Algolia DocSearch for fuzzy, mobile-optimized results.
- **Pagination**: Infinite scroll for section indexes; 404 page with search fallback.

### 2.2 Page Templates
Every page uses a consistent, simple template:
- **Header**: Site logo (minimalist pen+code icon), nav bar (hamburger on mobile).
- **Body**: H1 title, TOC sidebar (collapsible on mobile), main content with admonitions (tips/warnings), code blocks (Syntax highlighting via Pygments), images (optimized WebP, lazy-load).
- **Footer**: Copyright, social links, CTA widget.
- **Length**: 2,000-3,500 words; 40% text, 30% lists/tables, 20% visuals, 10% CTAs.
- **Internal Linking**: 5-10 links/page to related content (e.g., "See AI tools in Software Domain").

## 3. Content Outline: 102 Pages with Insane Detail

Content is original, expert-level: Draw from STC guidelines, Google Developer Docs style, and 2025 trends (e.g., AI hallucinations in docs). Each page includes: Intro hook, step-by-step breakdowns, real-world examples (e.g., "In OpenAI's GPT-4 docs..."), downloadable assets (PDF templates via GitHub releases), and SEO-optimized meta (title/desc with keywords).

### 3.1 Introduction (3 Pages)
1. What Is Technical Writing? (Def: User-focused comms; history from WWII manuals to AI era; 2025 stats: $500B doc market).
2. The Role of a Technical Writer in Modern Teams (Agile integration, ROI calc: 25% faster onboarding).
3. Technical Writing vs. Other Forms (Journalism: Narrative vs. procedural; creative: Emotion vs. precision).

### 3.2 Fundamentals and Best Practices (18 Pages)
4-6. Audience Analysis (Personas, surveys; tools like Hotjar).
7-9. Clarity and Conciseness (Readability scores via Hemingway App; examples: 50-word API summary).
10-12. Active vs. Passive Voice (50+ examples; domain tweaks, e.g., passive in legal).
13-15. Using Visuals (Flowcharts in Mermaid; accessibility: ARIA labels).
16-18. Writing for Accessibility (WCAG 2.2; screen reader tests).
19-21. Grammar and Style Guides (AP vs. tech-specific like Google's; quizzes).

### 3.3 Types of Technical Documents (20 Pages)
22-24. User Manuals and Guides (Structure: TOC, indexing; mobile app example).
25-27. API Documentation (OpenAPI 3.1 specs; interactive Postman embeds).
28-30. Release Notes and Changelogs (Semantic versioning; GitHub template).
31-33. Knowledge Base Articles and FAQs (Zendesk-style; AI chat integration).
34-36. Installation and Setup Instructions (Idempotent steps; Docker examples).
37-39. Troubleshooting Guides (Decision trees; error code databases).
40-41. Standard Operating Procedures (SOPs) (ISO 9001 compliance; flow automation).
42-44. White Papers and Thought Leadership (Structure: Problem-Solution-Proof; AI ethics whitepaper sample).
45-46. Case Studies and Success Stories (Metrics: NPS scores; anonymized fintech case).
47-48. Press Releases and Marketing Collateral (SEO press kits).
49-51. Proposals and RFPs (Win rates; AI-generated drafts).
52-53. Policies and Compliance Documents (GDPR checklists).
54-57. API Rate Limiting Docs, Migration Guides, Onboarding Playbooks, Deprecation Notices (Software-specific expansions).
58-59. Safety Data Sheets, Batch Records (Medical/manufacturing).
60-61. Risk Assessments, Audit Trails (Finance/engineering).

### 3.4 Tools and Technologies (12 Pages)
62-64. Essential Software (VS Code extensions; MadCap vs. Paligo CCMS).
65-66. Version Control for Writers (Git branching for docs; GitHub Pages workflow).
67-68. Collaboration Tools (Notion AI blocks; Slack integrations).
69-70. Diagramming (Excalidraw for quick sketches; PlantUML for code-gen).
71-72. Automation (GitHub Actions YAML for PDF gen; CI for linting).
73-74. AI in Technical Writing (Prompt engineering; tools like Claude for outlines—2025 focus).

### 3.5 Domain-Specific Technical Writing (43 Pages)
#### 3.5.1 Software & AI (15 Pages – Expanded for Specificity)
75. Documenting Codebases (JSDoc/RST; linting with Vale).
76. SaaS User Guides (Intercom-style; A/B testing docs).
77. Mobile App Documentation (Swift/Objective-C specs).
78. Cloud Infrastructure Docs (Terraform modules; AWS Well-Architected).
79. DevOps Pipelines (Jenkinsfile annotations).
80. AI Model Documentation (Hugging Face cards; bias disclosure).
81. Prompt Engineering for Docs (Chain-of-thought examples; fine-tuning LLMs for SOPs).
82. AI Ethics in Technical Writing (Hallucination mitigations; EU AI Act compliance).
83. Documenting LLMs (Input/output schemas; RAG pipelines).
84. Generative AI Tools for Writers (GitHub Copilot for Markdown; 2025 benchmarks).
85. Quantum Software Specs (Qiskit docs; error correction notes).
86. Blockchain Smart Contract Audits (Solidity comments).
87. VR/AR Interface Guides (Unity docs).
88. IoT Device Manuals (Firmware flashing; security certs).
89. Cybersecurity Threat Models (STRIDE framework).

#### 3.5.2 Medical and Healthcare (8 Pages)
90. Regulatory Writing (FDA 21 CFR Part 11; eCTD formats).
91. Clinical Trial Protocols (CONSORT checklists).
92. Device User Manuals (IFU; risk classifications).
93. Pharma Batch Records (GMP compliance).
94. Telemedicine Guides (HIPAA annotations).
95. AI in Med Docs (FDA SaMD guidelines).
96. Patient-Facing Explainers (Plain language summaries).
97. Adverse Event Reporting (MedDRA coding).

#### 3.5.3 Engineering (8 Pages)
98. Hardware Specs (CAD drawings; BOMs).
99. Mechanical Process Docs (FEA simulations).
100. Electrical Schematics (KiCad annotations).
101. Civil Infrastructure Manuals (ASCE standards).
102. Automotive ECU Programming (CAN bus protocols).
103. Aerospace Avionics Guides (DO-178C certification).
104. Renewable Energy SOPs (Solar inverter installs).
105. Robotics Kinematics Docs (ROS packages).

#### 3.5.4 Finance (7 Pages)
106. Compliance Reports (SOX 404; RegTech tools).
107. FinTech API Guides (Plaid integrations).
108. Investment Prospectuses (SEC EDGAR filing).
109. Risk Management Policies (VaR models).
110. Crypto Wallet Security Docs (Multi-sig setups).
111. ESG Reporting (GRI standards; AI analytics).
112. Banking Onboarding Flows (KYC/AML checklists).

#### 3.5.5 Other Domains (5 Pages)
113. Manufacturing Quality Manuals (Six Sigma).
114. Environmental Impact Assessments (EIA templates).
115. Legal Tech Contracts (Smart contract legalese).
116. Education LMS Guides (Moodle custom plugins).
117. Gaming Dev Kits (Unity/Unreal blueprints).

### 3.6 Advanced Skills and Processes (10 Pages)
118. SEO for Technical Documentation (Schema markup; Core Web Vitals).
119. Localization and Translation (PO files; DeepL API).
120. Agile Documentation (Jira tickets for docs).
121. Measuring Doc Success (Google Analytics events; CSAT surveys).
122. Ethical Considerations (Inclusive language audits).
123. Future Trends: AI/VR (Neural rendering for diagrams; 2026 predictions).
124. Single-Sourcing (DITA XML; conditional content).
125. Versioning Strategies (Semantic doc releases).
126. Collaborative Review Workflows (GitHub PRs with suggestions).
127. Crisis Documentation (Incident post-mortems).

### 3.7 Career and Expertise Building (8 Pages)
128. Becoming a Technical Writer (Bootcamps; Google certs).
129. Freelance Technical Writing (Upwork strategies; 2025 rates: $0.20/word).
130. Building a Portfolio (Notion showcases; PDF exports).
131. Networking (Write the Docs 2026 agenda).
132. Certifications (STC CPTC; AI Writing Specialist).
133. Job Hunting Tips (Resume keywords; Indeed ATS hacks).
134. Mentorship Programs (Pair-writing sessions).
135. Scaling to Consultancy (Agency models).

### 3.8 Resources and Templates (8 Pages)
136. Free Templates (50+ Markdown skeletons; e.g., AI prompt library).
137. Glossary (500+ terms; searchable).
138. Recommended Reading (2025 editions: "Docs Like Code 2.0").
139. Tool Cheat Sheets (Keyboard shortcuts).
140. Case Study Archives (10+ deep dives).
141. Webinar Recordings (Embedded YouTube).
142. Community Forums (Discord invite).
143. Update Log (Changelog for site).

## 4. Design and User Experience: Clean, Professional, Mobile-Friendly

**Theme**: Material for MkDocs (Insiders edition for 2025 features like dark mode toggle). Custom CSS overrides for "insane detail" polish.

### 4.1 Visual Style Guide
- **Color Palette**: Primary: #1E3A8A (deep blue for trust); Secondary: #10B981 (emerald accents); Neutral: #F9FAFB white, #111827 gray. High contrast (AA compliant).
- **Typography**: Roboto (sans-serif, 16px base on desktop, 18px on mobile for readability). H1: 2.5rem bold; Line height: 1.6.
- **Icons**: Heroicons (SVG, 24px); e.g., book-open for pages.
- **Spacing**: 1.5rem gutters; 4rem sections; mobile: 1rem gutters via media queries.
- **Images**: Responsive (max-width:100%; height:auto); alt text mandatory (e.g., "API endpoint flowchart"). Compress to <100KB via TinyPNG.

### 4.2 Mobile Optimization (Priority: 100% Responsive)
- **Breakpoints**: 320px (phone), 768px (tablet), 1024px+ (desktop). Use `@media (max-width: 768px)` for stack nav, enlarge touch targets (48px min).
- **Performance**: Minify CSS/JS (via mkdocs-minify-plugin); lazy-load images (native HTML); no JS bloat—pure CSS animations (fade-ins).
- **Navigation**: Off-canvas drawer on mobile (swipe-right); sticky TOC collapses to tabs.
- **Readability**: Progressive enhancement; dark mode auto-detect (prefers-color-scheme); font-size toggle (+/- buttons).
- **Accessibility**: Semantic HTML (ARIA roles); keyboard nav; color-blind modes; tested with WAVE tool.
- **Custom CSS Snippet** (in `extra_css`):
```css
@media (max-width: 768px) {
  .md-nav { transform: translateX(-100%); transition: 0.3s ease; }
  .md-content { padding: 1rem; }
  img { max-height: 300px; object-fit: cover; }
}
.md-typeset h1 { color: #1E3A8A; border-bottom: 2px solid #10B981; padding-bottom: 0.5rem; }
```

### 4.3 CTA Widget Implementation
HTML partial (`partials/widget.html` via mkdocs-macros-plugin):
```html
<div class="hire-widget mdx-sidebar__inner" style="background: #F9FAFB; padding: 1rem; border-radius: 8px; margin: 2rem 0;">
  <h3>Need Expert Help?</h3>
  <script src="https://platform.linkedin.com/badges/js/badge.js" async></script>
  <div class="linkedin-badge"><a href="https://www.linkedin.com/in/yourprofile/" data-badge="professional"><img alt="Your LinkedIn"></a></div>
  <a href="https://indeed.com/yourprofile" class="md-button md-button--primary" style="width:100%; margin-top:0.5rem;">Hire Me on Indeed</a>
  <small>Consultations from $250/hr</small>
</div>
```
- Placement: Right sidebar desktop; bottom sticky mobile (position:fixed; bottom:0;).
- Analytics: Track clicks via Google Analytics events.

## 5. SEO Strategy: 100+ Long-Tail Keywords

Leverage Yoast-inspired meta in MKDocs (via meta-plugin). On-page: Keywords in H1/H2, density 1-2%, LSI terms (e.g., "doc user experience"). Off-page: Submit sitemap to Google/Bing; build backlinks via HARO/guest posts.

**Keyword Research Basis**: 2025 estimates via Google Keyword Planner trends (global monthly searches, US skew). Long-tails: 3-7 words, low comp (<30 KD). Potential traffic: 10-25% capture if top 3 (annual calc: volume x 12 x capture %).

| # | Keyword | Est. Monthly Vol. | KD | Annual Traffic Est. | Target Page |
|---|---------|-------------------|----|---------------------|-------------|
|1| how to start technical writing career 2025 | 420 | 25 | 500-1,000 | Career Intro |
|2| best practices for clear technical writing examples | 240 | 20 | 290-580 | Clarity |
|3| audience analysis techniques in tech docs | 160 | 15 | 190-380 | Audience |
|4| active voice vs passive in technical manuals | 130 | 18 | 160-310 | Voice |
|5| technical writing for beginners free guide | 350 | 22 | 420-840 | Beginners |
|6| how to write user manual step by step | 290 | 28 | 350-700 | User Manuals |
|7| api documentation best practices openapi 3 | 190 | 30 | 230-460 | API |
|8| writing effective release notes software | 110 | 12 | 130-260 | Release Notes |
|9| free troubleshooting guide template download | 510 | 35 | 610-1,220 | Troubleshooting |
|10| sop template for tech processes 2025 | 250 | 20 | 300-600 | SOPs |
|11| white paper writing guide for ai startups | 150 | 25 | 180-360 | White Papers |
|12| technical case study examples pdf | 180 | 22 | 220-430 | Case Studies |
|13| rfp proposal template technical writing | 70 | 15 | 85-170 | Proposals |
|14| gdpr compliance document examples | 200 | 28 | 240-480 | Compliance |
|15| best markdown editors for tech writers 2025 | 120 | 18 | 140-280 | Markdown |
|16| github actions workflow for doc builds | 90 | 20 | 110-220 | GitHub |
|17| ai writing tools for technical docs review | 320 | 32 | 380-760 | AI Tools |
|18| draw.io tutorial for technical diagrams | 80 | 10 | 100-190 | Diagramming |
|19| medical technical writing fda 510k guide | 170 | 25 | 200-400 | FDA |
|20| engineering spec sheet template free | 140 | 22 | 170-330 | Engineering Specs |
|21| fintech api documentation compliance tips | 70 | 18 | 85-170 | FinTech |
|22| software localization best practices 2025 | 60 | 15 | 70-140 | Localization |
|23| seo for technical documentation google | 210 | 30 | 250-500 | SEO Docs |
|24| agile doc sprints scrum examples | 50 | 12 | 60-120 | Agile |
|25| roi metrics for technical writing projects | 40 | 10 | 50-100 | Metrics |
|26| bias free language in tech content | 30 | 8 | 35-70 | Ethics |
|27| freelance technical writer hourly rates 2025 | 310 | 28 | 370-740 | Freelance |
|28| technical writing portfolio samples github | 190 | 25 | 230-460 | Portfolio |
|29| stc technical writing certification cost | 100 | 20 | 120-240 | Certs |
|30| write the docs 2026 conference preview | 50 | 15 | 60-120 | Networking |
|31| ai prompt engineering for api docs | 280 | 35 | 340-670 | AI Prompts |
|32| documenting machine learning models best practices | 220 | 30 | 260-520 | ML Docs |
|33| hallucination prevention in ai generated docs | 150 | 25 | 180-360 | AI Ethics |
|34| rag pipeline documentation tutorial | 120 | 28 | 140-280 | RAG |
|35| fine tuning llms for technical manuals | 90 | 22 | 110-210 | Fine-Tuning |
|36| quantum computing software doc examples | 60 | 18 | 70-140 | Quantum |
|37| blockchain technical whitepaper structure | 130 | 20 | 160-310 | Blockchain |
|38| vr ar user guide writing tips | 80 | 15 | 100-190 | VR/AR |
|39| iot firmware installation guide template | 100 | 12 | 120-240 | IoT |
|40| cybersecurity doc threat modeling strid e | 110 | 25 | 130-260 | Cyber |
|41| clinical trial protocol writing fda | 140 | 30 | 170-330 | Trials |
|42| hipaa compliant telemedicine docs | 90 | 20 | 110-210 | Telemed |
|43| ai in medical device ifu guidelines | 70 | 18 | 85-170 | Med AI |
|44| mechanical engineering process flow diagrams | 120 | 22 | 140-280 | Mech Eng |
|45| electrical schematic annotation best practices | 80 | 15 | 100-190 | Elec Eng |
|46| civil engineering bid document templates | 60 | 12 | 70-140 | Civil |
|47| automotive ecu diagnostic guide | 100 | 25 | 120-240 | Auto |
|48| solar panel installation sop safety | 110 | 20 | 130-260 | Renewables |
|49| sox compliance reporting for fintech | 150 | 28 | 180-360 | SOX |
|50| plaid api integration doc examples | 90 | 22 | 110-210 | Plaid |
|51| sec edgar filing technical guide | 70 | 18 | 85-170 | SEC |
|52| var risk model documentation finance | 50 | 15 | 60-120 | VaR |
|53| crypto wallet multi sig setup manual | 120 | 25 | 140-280 | Crypto |
|54| gri esg report writing framework | 80 | 20 | 100-190 | ESG |
|55| manufacturing six sigma dmaic doc template | 140 | 22 | 170-330 | Mfg |
|56| eia environmental impact assessment sample | 100 | 18 | 120-240 | Env |
|57| smart contract legal review checklist | 90 | 15 | 110-210 | Legal Tech |
|58| moodle lms plugin developer guide | 70 | 12 | 85-170 | EdTech |
|59| unity game dev kit documentation | 130 | 25 | 160-310 | Gaming |
|60| schema markup for api reference pages | 190 | 30 | 230-460 | Schema |
|61| dita xml single sourcing tutorial | 60 | 20 | 70-140 | DITA |
|62| google analytics for doc engagement | 110 | 22 | 130-260 | Analytics |
|63| eu ai act technical annex writing | 80 | 28 | 100-190 | AI Act |
|64| post incident doc review playbook | 50 | 15 | 60-120 | Crisis |
|65| google technical writing certification 2025 | 240 | 25 | 290-580 | Google Cert |
|66| upwork technical writing gig proposals | 160 | 20 | 190-380 | Upwork |
|67| notion portfolio for tech writers | 100 | 18 | 120-240 | Notion |
|68| jira doc ticket best practices | 70 | 12 | 85-170 | Jira |
|69| inclusive language audit tools 2025 | 90 | 15 | 110-210 | Inclusive |
|70| neural diagram generation ai tools | 120 | 30 | 140-280 | Neural |
|71| free api doc template swagger | 300 | 35 | 360-720 | Swagger |
|72| changelog md keep a changelog examples | 140 | 22 | 170-330 | Changelog |
|73| faq accordion html for mkdocs | 80 | 18 | 100-190 | FAQ |
|74| idempotent install scripts writing | 60 | 15 | 70-140 | Install |
|75| decision tree troubleshooting visuals | 110 | 20 | 130-260 | Trees |
|76| thought leadership blog to whitepaper | 90 | 25 | 110-210 | Leadership |
|77| anonymized case study template tech | 70 | 12 | 85-170 | Anon Case |
|78| press kit seo optimization tips | 50 | 10 | 60-120 | Press |
|79| kyc aml onboarding doc finance | 130 | 28 | 160-310 | KYC |
|80| vs code tech writing extensions list | 200 | 22 | 240-480 | VS Code |
|81| confluence ai page generation 2025 | 150 | 25 | 180-360 | Confluence |
|82| plantuml sequence diagrams tutorial | 100 | 18 | 120-240 | PlantUML |
|83| vale prose linter setup github | 80 | 15 | 100-190 | Vale |
|84| claude ai for doc outlining prompts | 220 | 30 | 260-520 | Claude |
|85| hardware bom bill of materials template | 140 | 20 | 170-330 | BOM |
|86| can bus protocol doc automotive | 90 | 22 | 110-210 | CAN |
|87| do 178c avionics software guide | 70 | 18 | 85-170 | Avionics |
|88| regtech compliance automation docs | 60 | 15 | 70-140 | RegTech |
|89| ami kyc checklist template | 110 | 25 | 130-260 | AML |
|90| dmaic template excel for mfg docs | 120 | 20 | 140-280 | DMAIC |
|91| ros robot kinematics yaml examples | 80 | 12 | 100-190 | ROS |
|92| core web vitals optimization docs | 160 | 28 | 190-380 | Vitals |
|93| po file translation workflow tools | 70 | 15 | 85-170 | PO |
|94| csat survey integration tech docs | 50 | 10 | 60-120 | CSAT |
|95| pair writing mentorship session guide | 40 | 8 | 50-100 | Mentorship |
|96| buttondown newsletter for writers | 90 | 18 | 110-210 | Newsletter |
|97| youtube embed mkdocs tech tutorials | 100 | 20 | 120-240 | YouTube |
|98| discord community tech writing tips | 60 | 12 | 70-140 | Discord |
|99| semantic doc versioning strategy | 80 | 15 | 100-190 | Versioning |
|100| pr review checklist for docs github | 110 | 22 | 130-260 | PR Review |
|101| bootcamp technical writing online 2025 | 180 | 25 | 220-430 | Bootcamp |
|102| ats resume keywords technical writer | 140 | 20 | 170-330 | ATS |

**Total Est. Annual Traffic**: 15,000-30,000 (sum of mids). Strategy: Cluster content (e.g., AI cluster links); update for 2026 vols.

## 6. Technical Setup: GitHub Actions & MKDocs

### 6.1 MKDocs Config (mkdocs.yml Excerpt)
```yaml
site_name: Tech Write Expert
theme:
  name: material
  features: [content.tabs, navigation.instant, search.suggest]
  palette: [blue, green]
plugins:
  - search
  - macros2  # For widget
  - minify  # CSS/JS
  - meta-descriptions  # SEO
markdown_extensions:
  - admonition
  - pymdownx.highlight
  - pymdownx.superfences
extra:
  social: [linkedin: yourprofile]
```

### 6.2 GitHub Actions Workflow (.github/workflows/ci.yml)
```yaml
name: Deploy Docs
on: [push, pull_request]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - uses: actions/setup-python@v5
      with: {python-version: 3.12}
    - run: pip install mkdocs-material mkdocs-minify-plugin
    - run: mkdocs build --strict
    - uses: actions/upload-artifact@v4  # For review
    - if: github.ref == 'refs/heads/main'
      uses: peaceiris/actions-gh-pages@v4
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./site
```

- **Repo Structure**: `/docs/` for MD files; `/assets/` for images/templates.
- **Testing**: Pre-commit hooks for Vale linting; Netlify preview deploys.

## 7. Development Roadmap and Maintenance

### 7.1 Build Phases
- **Phase 1 (Setup)**: Init repo, theme install, 5 sample pages.
- **Phase 2 (Content Sprint)**: Batch-write sections; use AI for drafts (review manually).
- **Phase 3 (Polish)**: SEO audit (Screaming Frog); mobile tests (BrowserStack).
- **Phase 4 (Launch)**: Domain point (Namecheap); analytics setup.

### 7.2 Maintenance
- Quarterly: Add 10 pages (e.g., "Groq API Docs 2026").
- Tools: Hugo for backups? No—stick to MKDocs.
- Backup: GitHub + Vercel mirror.

This Bible is your north star—iterate as needed. Total tokens maximized for detail; build starts now!

Domain will be https://technicalwriter.site ensure no 301 issues, redirect www version properly. 

Project folder is C:\tech
github repo is https://github.com/justinarndt/tech.git

linkedin is https://www.linkedin.com/in/justinlarndt/
twitter is https://x.com/JustinArndtAI


Design info is in design.md
If there is a conflict in this file and design always choose human looking and best practices for SEO