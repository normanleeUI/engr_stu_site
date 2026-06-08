# ECE Research Paper Guide — Specification

## 1. Overview

A static Jekyll website that helps undergraduate and graduate electrical and computer engineering students navigate University of Idaho Library resources to complete a two-page IEEE-format research paper.
The site is structured around the four core skills the assignment requires: finding scholarly sources, verifying citation integrity, writing in IEEE format, and using AI tools ethically.
It reuses the branding, theme, and deployment pattern of the existing [Data Management Guide](https://www.lib.uidaho.edu/services/data/data-management).

## 2. Users and context

**Primary users:** Upper-division undergraduate and graduate students in:
- ECE 310 — Microelectronics 1
- ECE 4700 / ME 4810 — Control Systems (cross-listed ECE / ME)
- ECE 5220 — Induction Machines

**Access path:** Students find the site via a direct link in the course syllabus.

**Content authors:** Norman Lee (research librarian) is the primary author.
The collaborating professor reviews and approves content before launch.
Contributing documentation is out of scope for now but noted as a future to-do.

**Assignment context:** All three courses use the same final project prompt (reproduced in Appendix A).
The assignment requires students to:
1. Write a two-page research paper in IEEE format on a course-related topic.
2. Cite scholarly sources (IEEE, ASEE, ASME, or similar institutions).
3. Ensure sources do not contain circular reasoning or references to one another.
4. Discuss the validity of sources and identify gaps in the information provided.
5. Support all statements with research or calculations.

The site maps directly to these requirements so students can find relevant guidance by task.

## 3. Functional requirements

### 3.1 Site infrastructure

- **FR-INFRA-1:** The site uses Jekyll with a vendored fork of the Just the Docs theme — all theme files (`_includes/`, `_layouts/`, `_sass/`, `assets/`) live in the repo, not installed via gem. The `Gemfile` requires only `github-pages` and `webrick`, matching the data-management-guide. The `_config.yml` preserves `permalink: pretty` and the `defaults` block that applies `layout: "page"` to paths under `guide/`.
- **FR-INFRA-2:** The site is deployable to GitHub Pages under `lib.uidaho.edu` (URL path TBD; placeholder used in config).
- **FR-INFRA-3:** Navigation has two levels: 4 top-level sections, each with 3 child pages. No deeper nesting. Pages use the following front matter conventions:
  - **Section index pages:** `title`, `has_children: true`, `nav_order` (integer, controls section ordering in sidebar).
  - **Child pages:** `title`, `parent` (must exactly match the parent's `title` field), `nav_order` (integer, controls ordering within section).
  - **Nav order assignments:** Homepage = 0, Section 1 = 1, Section 2 = 2, Section 3 = 3, Section 4 = 4, Contact = 5. Child pages use `nav_order` 1–3 within their parent.
- **FR-INFRA-4:** Pages may cross-link to related pages in other sections where relevant.
- **FR-INFRA-5:** External database links use U of I Library proxy URLs (`uidaho.idm.oclc.org`) where applicable. Links are flagged during authoring for case-by-case proxy decision.
- **FR-INFRA-6:** Each section index page includes a dedicated callout box (placeholder) for a future video walkthrough or Genially interactive element. These callouts are added in Phase 3, not Phase 1.

### 3.2 Section 1 — Finding Scholarly Sources

Maps to assignment requirement: *"Acceptable sources include textbooks and papers from IEEE, ASEE, ASME, or other similar institutions."*

- **FR-S1-1: Scholarly vs. Web Sources** — A page explaining why the distinction matters for academic research, with concrete examples of each type.
- **FR-S1-2: Navigating IEEE Xplore & Web of Science** — A page introducing both databases, how to access them through the library, and basic search/navigation guidance. Links to IEEE Xplore and Web of Science via library proxy.
- **FR-S1-3: Google Scholar & Verifying Journal Quality** — A page covering Google Scholar library integration setup, plus using Journal Citation Reports (JCR) and journal websites to verify peer-reviewed status and journal impact.

### 3.3 Section 2 — Citation Integrity

Maps to assignment requirements: *"Ensure that your sources do not contain circular reasoning or references to one another"* and *"discuss the validity of your sources and identify any gaps."*

- **FR-S2-1: Interrogating Your Sources** — A single page covering both (a) checking citation independence (circular references, sources citing each other) and (b) critically evaluating a source's claims and methods. Addresses the professor's observation that students tend to justify sources rather than interrogate them. Explains the difference between "this source is good because it's peer-reviewed" (justification) and "this source's methodology has limitation X, which means its conclusions may not apply to Y" (interrogation).
- **FR-S2-2: Citation Chaining** — A page explaining forward and backward citation chaining, with interface guidance for IEEE Xplore, Web of Science, and Google Scholar's "Cited By" feature. Optionally includes a callout box introducing citation network visualization tools (e.g., citationgraph.org) as a supplementary resource — not core content.
- **FR-S2-3: Common Citation Pitfalls** — A page covering failure modes students should watch for: over-cited seminal papers that get misinterpreted, publish-or-perish incentive distortions, predatory journals, and circular citation patterns.

### 3.4 Section 3 — Writing in IEEE Format

Maps to assignment requirement: *"write a two-page research paper in IEEE format"* and *"you must cite all sources and support all statements with research or calculations."*

- **FR-S3-1: IEEE Templates & Tools** — A page linking to IEEE Author Center templates and authoring tools, with brief guidance on getting started.
- **FR-S3-2: Structuring Your Paper** — A page on IEEE article structure conventions, linking to the IEEE Author Center structure guide.
- **FR-S3-3: IEEE Citation Practices** — A page on proper IEEE citation format, the rationale behind citation conventions, and the IEEE Editorial Style Manual.

### 3.5 Section 4 — AI in Research

Maps to the professor's requirement for ethical, effective, and prudent AI use. Content is largely placeholder in the initial version.

- **FR-S4-1: AI Search Tools & Their Limitations** — A page covering which AI tools search which sources, why AI-generated citations must always be verified, and a concrete example of how AI can hallucinate even when querying academic databases (e.g., Semantic Scholar's AI features).
- **FR-S4-2: Appropriate vs. Inappropriate AI Use** — A placeholder page structured around the professor's concrete examples (appropriate: hand-sketch a flow diagram, ask AI to clean up lines; inappropriate: give AI your code and ask it to write a flow diagram). Space reserved for a future "honest discussion" video about AI pros and cons.
- **FR-S4-3: IEEE AI Policy & U of I Resources** — A page linking to IEEE's AI-generated content policy and the U of I's Google AI partnership for self-paced tutoring and comprehension checking.

### 3.6 Homepage

- **FR-HOME-1:** The homepage states what the site is, who it's for (listing ECE 310, ECE 4700 / ME 4810, ECE 5220), and links to each of the four sections.
- **FR-HOME-2:** A brief summary of the assignment context so students understand why these resources exist.
- **FR-HOME-3:** Buttons linking to each section, styled consistently with the data-management-guide homepage (pride-gold, clearwater, lupine button variants).

### 3.7 Help / Contact

- **FR-CONTACT-1:** A page with contact information for library research help, following the data-management-guide's contact page pattern.

## 4. Concrete examples

### Example 1: Student looking for IEEE sources

A student in ECE 310 needs to find scholarly papers on MOSFET scaling.
They visit the site from the syllabus link, land on the homepage, and click "Finding Scholarly Sources."
From the section index, they navigate to "Navigating IEEE Xplore & Web of Science."
The page shows them how to access IEEE Xplore through the library proxy (so they don't hit a paywall), enter a search, and filter results.
They find three relevant papers.

### Example 2: Student unsure if their citations are valid

A student in ECE 5220 has found five sources but isn't sure they meet the assignment's requirement to avoid circular reasoning.
They visit "Citation Integrity" → "Interrogating Your Sources."
The page explains what circular citation looks like (Source A cites Source B, Source B cites Source A, neither has independent evidence) and how to check citation independence.
It also explains the difference between justifying and interrogating a source, with before/after examples of each approach applied to the same paper.

### Example 3: Student wondering if they can use ChatGPT

A student in ECE 4700 wants to know if they can use ChatGPT to help with their paper.
They visit "AI in Research" → "Appropriate vs. Inappropriate AI Use."
The page shows concrete examples of acceptable use (cleaning up a hand-drawn diagram) vs. unacceptable use (generating content and presenting it as their own work), along with the professor's expectations.

## 5. Failure modes and error handling

This is a static site, so traditional software failure modes (crashes, data loss) do not apply. Relevant concerns:

- **Link rot:** External URLs (IEEE Xplore, Web of Science, JCR, IEEE Author Center, etc.) may change or break. This is noted as a maintenance concern. The content author should periodically verify external links. A link-checking CI step (e.g., `htmlproofer`) is a possible future enhancement but out of scope for initial launch.
- **Proxy URL changes:** Library proxy URLs could change if the library switches proxy vendors. All proxy URLs are written in page content (not centralized in config), so updating them requires editing individual pages. This is acceptable for the initial scope; centralizing proxy URLs in a data file is a possible future enhancement.
- **Build failures:** Jekyll build errors from malformed front matter or Liquid syntax would prevent deployment. The content author should run `bundle exec jekyll serve` locally to verify before pushing.
- **Accessibility:** The Just the Docs theme provides a reasonable accessibility baseline. Additional accessibility guidelines from the [U of I Library remediation guide](https://aweymo-ui.github.io/libguide_remediation/) should be consulted as content is added, especially for images, embedded media, and link text.

## 6. Non-functional requirements

- **NFR-1: Branding consistency** — The site uses the same vendored theme files, color scheme (`library.scss`), logos, and layout structure as the data-management-guide. Custom style overrides are limited to `_sass/custom/custom.scss`. Content and structure differ; look and feel match.
- **NFR-2: Deployment** — GitHub Pages via the same pattern as the data-management-guide. Another team member handles deployment; the site must build cleanly with `github-pages` gem.
- **NFR-3: Accessibility** — Meets WCAG 2.1 AA as provided by the Just the Docs theme baseline. Additional remediation per U of I guidelines is a future enhancement.
- **NFR-4: Maintainability** — Content is Markdown with minimal Liquid templating. A non-developer (the librarian) should be able to edit page content by editing Markdown files.
- **NFR-5: No timeline pressure** — Quality over speed. All four sections should have real content before launch.

## 7. Out of scope

- Grading rubrics or assignment-specific instructions
- Course schedules or syllabi
- Student submissions, interaction, or feedback mechanisms
- Video walkthroughs or Genially interactive courses (placeholders only)
- Contributing documentation (noted as future to-do)
- Automated link checking (CI)
- Centralized proxy URL management
- Content for other professors or departments (site is scoped to the collaborating professor's three courses)
- Accessibility remediation beyond what the theme provides (future enhancement)
- Glossary collection (the data-management-guide has one, but unnecessary complexity for a ~15-page student-facing site)
- Detailed explanation of RAG architecture or AI internals (students need practical guidance, not systems knowledge)
- Custom domain or hosting setup (handled by another team)

## 8. Verification plan

| Check | Method | Expected result |
|---|---|---|
| Site builds cleanly | `bundle exec jekyll serve` | No errors; site renders at localhost |
| Branding matches reference | Visual comparison with data-management-guide | Same header, footer, nav style, colors, logos |
| All 4 sections have content | Manual review of each page | Real content on all pages; no blank pages |
| Placeholder callouts present | Manual review of section index pages | Each section index has a visible "tutorial coming soon" callout |
| Navigation structure correct | Click through all nav links | 4 top-level sections, 3 children each, all links work |
| Cross-links work | Click internal cross-references | All cross-links navigate to the correct page |
| External links work | Click each external link | All links resolve (proxy links require U of I authentication) |
| Proxy links flagged | Author review during content phase | Each external link has been evaluated for proxy URL applicability |
| Professor approval | Send site URL to professor | Professor confirms content is accurate and appropriate |
| Student comprehension spot-check | Have 1–2 students from the target courses attempt a task (e.g., "find an IEEE paper on your topic") using the site | Students can complete the task without external help; note any confusion points |

## 9. Open questions

1. **URL path under lib.uidaho.edu** — Not yet decided. Needed before deployment but not before development. Placeholder will be used in `_config.yml`.
2. **Site title** — Working title is "ECE Research Paper Guide." Professor should confirm.
3. **Contact page content** — Who specifically should students contact? Norman, the professor, general library help desk, or some combination?
4. **Accessibility audit scope** — The U of I remediation guide at `aweymo-ui.github.io/libguide_remediation/` should be retrieved and reviewed. Specific requirements from that guide may add to the non-functional requirements.
5. **Contributing docs** — If other librarians or faculty will eventually edit content, when should contributing documentation be added?

## 10. Phasing recommendation

### Phase 1 — Walking skeleton
Copy the entire vendored theme infrastructure from data-management-guide (`_includes/`, `_layouts/`, `_sass/`, `assets/`, `Gemfile`, `Rakefile`, `favicon.ico`, `404.html`). Customize `_config.yml` for this project (title, description, baseurl placeholder, aux links). Create the homepage and all content pages under `guide/` with correct front matter, an H1 heading, and a one-sentence description of what the page will cover. No multimedia callout boxes yet.

**Exit criteria:** `bundle exec jekyll serve` runs without errors. All nav links work (4 sections, 3 children each, homepage, contact). Branding matches the data-management-guide (same theme files, same color scheme). Every page has a heading and placeholder sentence — no blank pages.

### Phase 2 — Core content (Sections 1–3)
Write real content for Sections 1 (Finding Scholarly Sources), 2 (Citation Integrity), and 3 (Writing in IEEE Format). These sections have well-defined content and links from the initial communications. Flag all external links for proxy URL review.

**Exit criteria:** Sections 1–3 have complete content. All external links have been reviewed for proxy applicability. Cross-links between sections are in place.

### Phase 3 — AI content (Section 4) + Contact
Write content for Section 4 (AI in Research), including the placeholder structures for future video/interactive content. Create the contact/help page. Add multimedia placeholder callouts to all section index pages.

**Exit criteria:** All 4 sections have real content. Placeholder callouts are visible on all section index pages. Contact page is complete.

### Phase 4 — Review and launch
Professor reviews the complete site. Address feedback. Final verification pass (all links, navigation, branding, accessibility baseline). Hand off to deployment team.

**Exit criteria:** Professor has approved. All verification checks in §8 pass.

## 11. Directory structure

```
engr_stu_site/
├── _config.yml                     # Site config (customized for this project)
├── _includes/                      # Copied wholesale from data-management-guide
├── _layouts/                       # Copied wholesale from data-management-guide
├── _sass/                          # Copied wholesale from data-management-guide
│   └── custom/
│       └── custom.scss             # Only file modified after copying (site-specific overrides)
├── assets/                         # Copied wholesale from data-management-guide
├── guide/
│   ├── scholarly-sources/
│   │   ├── index.md                # Section 1 index (has_children: true, nav_order: 1)
│   │   ├── scholarly-vs-web.md     # (parent: "Finding Scholarly Sources", nav_order: 1)
│   │   ├── ieee-xplore-wos.md     # (parent: "Finding Scholarly Sources", nav_order: 2)
│   │   └── google-scholar-jcr.md  # (parent: "Finding Scholarly Sources", nav_order: 3)
│   ├── citation-integrity/
│   │   ├── index.md                # Section 2 index (has_children: true, nav_order: 2)
│   │   ├── interrogating-sources.md
│   │   ├── citation-chaining.md
│   │   └── citation-pitfalls.md
│   ├── ieee-format/
│   │   ├── index.md                # Section 3 index (has_children: true, nav_order: 3)
│   │   ├── templates-tools.md
│   │   ├── structuring-paper.md
│   │   └── citation-practices.md
│   ├── ai-in-research/
│   │   ├── index.md                # Section 4 index (has_children: true, nav_order: 4)
│   │   ├── ai-tools-limitations.md
│   │   ├── appropriate-use.md
│   │   └── ieee-policy-resources.md
│   └── contact.md                  # Help / contact page (nav_order: 5)
├── index.md                        # Homepage (nav_order: 0)
├── 404.html                        # Error page (copied from data-management-guide)
├── favicon.ico                     # Copied from data-management-guide
├── Gemfile                         # github-pages + webrick only
├── Rakefile                        # Build tasks (copied from data-management-guide)
├── .gitignore
└── README.md
```

**Note on theme directories:** `_includes/`, `_layouts/`, `_sass/`, and `assets/` are copied wholesale from the data-management-guide. The only files modified after copying are `_config.yml` (project-specific settings), `_sass/custom/custom.scss` (site-specific style overrides if needed), and `_includes/footer_custom.html` (updated footer nav links). All other theme files are used as-is to maintain branding consistency.

## Appendix A — Assignment prompt

> For your final project, you will write a two-page research paper in IEEE format on a topic of your choice relating to the course material. Your paper can involve a novel solution to an existing problem, exploring and explaining holes in the existing research, or exploring a specific topic at greater depth. You can find some suggested topics in the discussion forum or mentioned in class. This is a research paper, so you must cite all sources and support all statements with research or calculations. Acceptable sources include textbooks and papers from IEEE, ASEE, ASME, or other similar institutions. Papers from other scholarly journals are also acceptable. Ensure that your sources do not contain circular reasoning or references to one another. In your paper, discuss the validity of your sources and identify any gaps in the information provided.

The assignment is used identically across ECE 310, ECE 4700 / ME 4810, and ECE 5220.
The professor keeps the prompt intentionally open-ended so students can explore their own interests within the course material.
