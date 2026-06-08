# Phase 2 Implementation Plan — Core Content (Sections 1–3)

Based on `_SPEC.md` §10 Phase 2. The goal is to replace all placeholder content in Sections 1–3 with near-final quality content ready for professor review.

## Scope deviations from spec

The spec's Phase 2 exit criteria include "Cross-links between sections are in place."
Per user decision (2026-06-08), cross-links are deferred to Phase 3 so that all four sections have content before cross-linking.
The spec's cross-link exit criterion will be satisfied in Phase 3 instead.

## Content conventions (apply to every step)

These conventions derive from the [U of I Library Style Guide](https://www.lib.uidaho.edu/docs/) and the [data-management-guide README](https://github.com/uidaholib/data-management-guide#readme).
All content must follow them throughout:

- One sentence per line (for cleaner diffs and easier editing)
- Blank lines between all elements (headers, paragraphs, lists, code blocks)
- H1 (`#`) at page top, matching the front matter `title`
- Logical header hierarchy — never skip levels (H1 → H2 → H3)
- Backticks for inline code and variables; "straight quotes" for filenames
- Target depth: 600–1500 words per page
- Clear, direct, educational tone; define unfamiliar terms on first use
- Keep existing front matter unchanged; only replace the body content below the YAML front matter block
- Do NOT add `layout:` to front matter — inherited from `_config.yml` defaults
- Do NOT add cross-links to other sections (deferred to Phase 3)
- Do NOT add multimedia callout boxes to section index pages (deferred to Phase 3)

**Alert component syntax** (for callout boxes within child pages):

```liquid
{% include feature/alert.html color="blue" text="Alert text here." %}
```

Available colors: `primary`, `purple`, `blue`, `green`, `yellow`, `red`.

**Button component syntax** (for external links):

```liquid
{% include feature/button.html color="pride-gold" link="https://example.com" text="Button text" %}
```

## Steps

### Step 1: Section 1 index + Scholarly vs. Web Sources (2 files)

**Files:** `guide/scholarly-sources/index.md`, `guide/scholarly-sources/scholarly-vs-web.md`

**Section index (`index.md`):**
Replace the one-sentence placeholder with 2–3 sentences that orient students to the section: what they will learn, why it matters for their assignment, and what the three child pages cover.

**Scholarly vs. Web Sources (`scholarly-vs-web.md`) — FR-S1-1:**
Replace placeholder with content covering:

- Why the scholarly vs. web distinction matters for academic research
- What makes a source "scholarly" (peer review, methodology, institutional affiliation)
- Concrete examples: a scholarly journal article vs. a blog post or Wikipedia entry on the same topic
- How to recognize scholarly sources (author credentials, journal name, DOI, references section)
- Brief note that the assignment requires sources from IEEE, ASEE, ASME, or similar institutions

**Verification:** `bundle exec jekyll serve` builds without errors. Both pages render with full content, correct headings, and no broken formatting.

---

### Step 2: Navigating IEEE Xplore & Web of Science (1 file)

**File:** `guide/scholarly-sources/ieee-xplore-wos.md`

**Content — FR-S1-2:**
Replace placeholder with content covering:

- Brief introduction to IEEE Xplore and Web of Science as primary databases for ECE research
- How to access each through the U of I Library (proxy URL links — ask user for exact proxy URLs before writing)
- Basic search guidance for each platform: entering search terms, using filters (year, document type, subject area)
- Navigation tips: reading search results, accessing full text, saving/exporting citations
- Note about off-campus access requiring the library proxy

**External links to include (flag for proxy review):**

- IEEE Xplore (proxy URL)
- Web of Science (proxy URL)
- U of I Library databases page (if applicable)

**Verification:** Page renders with all content. External links are present and flagged for proxy review. Build succeeds.

---

### Step 3: Google Scholar & Verifying Journal Quality (1 file)

**File:** `guide/scholarly-sources/google-scholar-jcr.md`

**Content — FR-S1-3:**
Replace placeholder with content covering:

- Google Scholar overview: what it searches, strengths and limitations vs. IEEE Xplore/WoS
- Setting up Google Scholar library integration (Settings → Library Links → "University of Idaho") so full-text links appear in results
- Introduction to Journal Citation Reports (JCR): what it measures, how to access through the library (proxy URL)
- Using JCR to check journal impact factor and ranking within a subject category
- Using a journal's website to verify peer-reviewed status (look for editorial board, submission guidelines, review process)
- Brief note: impact factor is one indicator of quality but not the only one

**External links to include (flag for proxy review):**

- Google Scholar (no proxy needed)
- Journal Citation Reports / JCR (proxy URL)

**Verification:** Page renders with all content. Google Scholar and JCR links present. Build succeeds.

---

### Step 4: Section 2 index + Interrogating Your Sources (2 files)

**Files:** `guide/citation-integrity/index.md`, `guide/citation-integrity/interrogating-sources.md`

**Section index (`index.md`):**
Replace placeholder with 2–3 sentences orienting students: what citation integrity means, why the assignment requires it, and what the three child pages cover.

**Interrogating Your Sources (`interrogating-sources.md`) — FR-S2-1:**
Replace placeholder with content covering:

- **Checking citation independence:** What circular citation looks like (Source A cites Source B, Source B cites Source A, neither has independent evidence). How to check whether your sources cite each other. Why the assignment prohibits this.
- **Critical evaluation vs. justification:** The difference between:
  - Justification: "This source is good because it's peer-reviewed" (describes the source's credentials)
  - Interrogation: "This source's methodology tested only X condition, which means its conclusions may not apply to Y" (evaluates the source's actual claims)
- Concrete before/after example: the same paper evaluated with justification vs. interrogation
- Questions students should ask: What methodology was used? What are its limitations? Do the conclusions follow from the data? What is missing?
- The professor's observation that students tend to justify rather than interrogate, and why interrogation produces stronger papers

**Verification:** Page renders with clear distinction between justification and interrogation, including the before/after example. Build succeeds.

---

### Step 5: Citation Chaining (1 file)

**File:** `guide/citation-integrity/citation-chaining.md`

**Content — FR-S2-2:**
Replace placeholder with content covering:

- What citation chaining is and why it is useful for finding related research
- **Backward chaining:** Looking at a paper's reference list to find its sources. How this reveals the foundational work in a topic area.
- **Forward chaining:** Finding papers that cite a known paper. How this reveals how a topic has evolved since publication.
- Interface guidance for each platform:
  - IEEE Xplore: where to find "References" and "Cited By" on an article page
  - Web of Science: using "Cited References" and "Times Cited" links
  - Google Scholar: using the "Cited by" link under search results
- Callout box (using `{% include feature/alert.html %}`): brief mention of citation network visualization tools (e.g., citationgraph.org) as a supplementary resource — not required for the assignment

**Verification:** Page renders with clear explanations of forward and backward chaining, platform-specific guidance, and the callout box. Build succeeds.

---

### Step 6: Common Citation Pitfalls (1 file)

**File:** `guide/citation-integrity/citation-pitfalls.md`

**Content — FR-S2-3:**
Replace placeholder with content covering:

- **Over-cited seminal papers:** Widely cited papers that get referenced without being read carefully. Risk: misinterpreting or over-generalizing their findings. How to check: actually read the paper, especially methodology and limitations.
- **Publish-or-perish distortions:** How academic incentive structures can lead to incremental or low-quality publications. How to identify: look for papers that make large claims with minimal new evidence.
- **Predatory journals:** What they are (journals that charge fees without providing legitimate peer review). Warning signs: aggressive solicitation emails, rapid "peer review," no recognizable editorial board. How to check: verify journal indexing in JCR or check the journal's website for an established editorial board.
- **Circular citation patterns:** How to detect when a group of papers cite each other to inflate credibility without independent validation. Connection back to the assignment requirement.

**Verification:** Page renders with all four pitfall categories clearly explained. Build succeeds.

---

### Step 7: Section 3 index + IEEE Templates & Tools (2 files)

**Files:** `guide/ieee-format/index.md`, `guide/ieee-format/templates-tools.md`

**Section index (`index.md`):**
Replace placeholder with 2–3 sentences orienting students: what IEEE format is, why the assignment uses it, and what the three child pages cover.

**IEEE Templates & Tools (`templates-tools.md`) — FR-S3-1:**
Replace placeholder with content covering:

- Link to the IEEE Author Center and its conference/journal templates (Word and LaTeX)
- Which template to use for a two-page conference-style paper (most appropriate for the assignment)
- Brief overview of authoring options: Microsoft Word template vs. LaTeX template vs. Overleaf (online LaTeX editor with IEEE templates built in)
- Getting started: downloading the template, understanding the pre-formatted sections, where to begin writing
- Note: the template handles most formatting (margins, columns, font sizes) — students should focus on content, not layout tweaking

**External links to include:**

- IEEE Author Center (public, no proxy)
- Overleaf IEEE templates (public, no proxy)

**Verification:** Page renders with template links and getting-started guidance. Build succeeds.

---

### Step 8: Structuring Your Paper (1 file)

**File:** `guide/ieee-format/structuring-paper.md`

**Content — FR-S3-2:**
Replace placeholder with content covering:

- Standard IEEE article structure: Title, Abstract, Introduction, Body sections, Conclusion, References
- What each section should contain and approximately how much space it gets in a two-page paper
- The role of the Introduction: establishing context, stating the problem, previewing the paper's contribution
- Body sections: presenting research, analysis, or calculations with supporting evidence
- The Conclusion: summarizing findings, stating implications, noting limitations
- Connection to the assignment: every statement must be supported by research or calculations
- Link to the IEEE Author Center structure guide

**External links to include:**

- IEEE Author Center structure/formatting guide (public, no proxy)

**Verification:** Page renders with clear section-by-section structure guidance. Build succeeds.

---

### Step 9: IEEE Citation Practices (1 file)

**File:** `guide/ieee-format/citation-practices.md`

**Content — FR-S3-3:**
Replace placeholder with content covering:

- IEEE citation format basics: numbered references in square brackets [1], listed in order of appearance (not alphabetically)
- How to format common reference types: journal articles, conference papers, books, online sources
- The rationale behind IEEE conventions: numbered citations keep text compact (important for page-limited papers), order-of-appearance reflects the paper's narrative flow
- Common mistakes: alphabetical ordering (that is APA/MLA, not IEEE), inconsistent formatting, missing required fields
- Link to the IEEE Editorial Style Manual for authoritative reference

**External links to include:**

- IEEE Editorial Style Manual (public or verify access)

**Verification:** Page renders with citation format examples and the Editorial Style Manual link. Build succeeds.

---

### Step 10: External link audit + full build verification

**Task:** Review all external links added across Sections 1–3. This step may touch multiple files across all three sections to apply proxy URL corrections.

1. Compile a list of every external URL added in Steps 1–9.
2. Confirm proxy URL decisions with the user (the user has a list of which links need proxying).
3. Update any links that need the `uidaho.idm.oclc.org` proxy wrapper.
4. Run `bundle exec jekyll serve` and verify:
   - All 9 content pages (3 per section) render with full content
   - All 3 section index pages render with updated descriptions
   - All external links are present and correctly formatted
   - No broken internal navigation
   - No build warnings or errors
   - Site branding still matches data-management-guide

**Verification:** All checks pass. Site builds cleanly with complete Sections 1–3 content.

---

## Exit checklist

- [ ] `bundle exec jekyll serve` builds without errors
- [ ] Section 1 index page has updated section description (not just placeholder)
- [ ] Section 1: all 3 child pages have complete, near-final content
- [ ] Section 2 index page has updated section description
- [ ] Section 2: all 3 child pages have complete, near-final content
- [ ] Section 3 index page has updated section description
- [ ] Section 3: all 3 child pages have complete, near-final content
- [ ] All external links are present and correctly formatted
- [ ] All external links have been reviewed for proxy URL applicability
- [ ] Proxy URLs applied where needed (per user's list)
- [ ] Content follows style conventions (one sentence per line, blank lines between elements, H1 at top, logical headers)
- [ ] Cross-links deferred to Phase 3 (per user decision 2026-06-08; spec exit criterion will be satisfied then)
- [ ] No multimedia callout boxes on section index pages (deferred to Phase 3)
- [ ] No blank pages — every page has substantive content
- [ ] All pages target 600–1500 words
- [ ] Navigation still works correctly (sidebar, footer, aux links)
- [ ] Branding still matches data-management-guide
