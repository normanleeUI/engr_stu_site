# Phase 3 Implementation Plan — AI Content (Section 4) + Multimedia Callouts

Based on `_SPEC.md` §10 Phase 3. The goal is to write full content for Section 4 (AI in Research) and add multimedia placeholder callout boxes to all four section index pages.

## Scope deviations from spec

- **Contact page:** The spec lists "Create the contact/help page" as a Phase 3 task, but it was completed in Phase 1 (commit `0328ecf`) and is already functional. No changes needed.
- **Cross-links:** The spec's Phase 2 exit criteria included "Cross-links between sections are in place." This was deferred from Phase 2 to Phase 3 (per user decision 2026-06-08), and is now deferred again from Phase 3 to Phase 4 (review and launch). This is the second deferral; the spec's cross-link exit criterion will be satisfied in Phase 4.

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
- Do NOT add cross-links to other sections (deferred to Phase 4)
- Do NOT modify the contact page (already complete)

**Alert component syntax** (for callout boxes):

```liquid
{% include feature/alert.html color="blue" text="Alert text here." %}
```

Available colors: `primary`, `purple`, `blue`, `green`, `yellow`, `red`.

- Use `blue` for informational content callouts within child pages (consistent with Sections 1–3)
- Use `yellow` for "coming soon" multimedia placeholder callouts (visually distinct from content callouts)

**Button component syntax** (for external links):

```liquid
{% include feature/button.html color="pride-gold" link="https://example.com" text="Button text" %}
```

## Steps

### Step 1: Section 4 index + AI Search Tools & Their Limitations (2 files)

**Files:** `guide/ai-in-research/index.md`, `guide/ai-in-research/ai-tools-limitations.md`

**Section index (`index.md`):**
Replace the one-sentence placeholder with 2–3 sentences that orient students to the section: what they will learn, why AI literacy matters for their assignment, and what the three child pages cover.

**AI Search Tools & Their Limitations (`ai-tools-limitations.md`) — FR-S4-1:**
Replace placeholder with content covering:

- Which AI tools search which sources (e.g., ChatGPT uses training data, Perplexity searches the web, Semantic Scholar's AI features query an academic database)
- Why AI-generated citations must always be verified — AI models can hallucinate citations that look real but don't exist
- A concrete example of how AI can produce unreliable results even when querying academic databases (e.g., a plausible-sounding paper with a real-looking DOI that doesn't resolve)
- The distinction between AI as a discovery tool (useful starting point) and AI as a citation source (dangerous without verification)
- Practical guidance: if an AI tool suggests a source, verify it exists in IEEE Xplore, Web of Science, or Google Scholar before citing it

**Verification:** `bundle exec jekyll serve` builds without errors. Both pages render with full content, correct headings, and no broken formatting.

---

### Step 2: Appropriate vs. Inappropriate AI Use (1 file)

**File:** `guide/ai-in-research/appropriate-use.md`

**Content — FR-S4-2:**
Replace placeholder with content covering:

- The professor's concrete examples of appropriate vs. inappropriate use:
  - **Appropriate:** Hand-sketch a flow diagram, then ask AI to clean up the lines and make it presentable
  - **Inappropriate:** Give AI your code and ask it to generate a flow diagram for you (the student hasn't demonstrated understanding)
- The general principle: AI should assist your work, not replace your thinking
- Additional examples relevant to a two-page research paper:
  - Appropriate: ask AI to check your grammar or suggest a clearer way to phrase a sentence you've already written
  - Inappropriate: ask AI to write a paragraph or section of your paper
  - Appropriate: ask AI to explain a concept you're struggling with so you can write about it in your own words
  - Inappropriate: paste an AI explanation directly into your paper
- Why this matters: the assignment is evaluating the student's ability to research, synthesize, and write — not the AI's
- Note that the professor's expectations may vary — when in doubt, ask
- An in-page placeholder callout for a future "honest discussion" video about AI pros and cons (per FR-S4-2), using a `yellow` alert

**Verification:** Page renders with clear, concrete examples of appropriate and inappropriate use. The hand-sketch diagram example from the professor is prominently featured. The video placeholder callout is visible. Build succeeds.

---

### Step 3: IEEE AI Policy & U of I Resources (1 file)

**File:** `guide/ai-in-research/ieee-policy-resources.md`

**Content — FR-S4-3:**
Replace placeholder with content covering:

- IEEE's position on AI-generated content in submissions: authors are responsible for all content, AI-generated text must be disclosed, and AI cannot be listed as an author
- Link to IEEE's AI-generated content policy page
- University of Idaho's Google AI partnership: what it offers (self-paced tutoring, comprehension checking) and how to access it
- Link to U of I's AI resources page (if available)
- How these policies connect to the assignment: students should use AI as a learning aid and disclose any AI assistance per IEEE guidelines
- Brief note: AI policies are evolving rapidly — check for the latest guidance before submitting

**External links to include (flag for review):**

- IEEE AI-generated content policy
- U of I AI resources / Google AI partnership page

**Verification:** Page renders with policy links and U of I resource links. Build succeeds.

---

### Step 4: Multimedia placeholder callouts on all section index pages (4 files)

**Files:** `guide/scholarly-sources/index.md`, `guide/citation-integrity/index.md`, `guide/ieee-format/index.md`, `guide/ai-in-research/index.md`

This step touches 4 files because the change is identical and small across all of them: appending one alert include to each section index page.

**Task:** Add a placeholder callout box to each section index page using the alert component. The callout indicates that a video walkthrough or interactive tutorial is coming soon. Place each callout after the existing section description text.

**Callout format:**

```liquid
{% include feature/alert.html color="yellow" text="**Coming soon:** A video walkthrough for this section is in development. Check back for an interactive tutorial." %}
```

Use `yellow` to visually distinguish these "coming soon" placeholders from the `blue` informational alerts used in child pages.

**Verification:** All four section index pages display the yellow callout box after their description text. Build succeeds. No existing content is displaced or broken.

---

### Step 5: External link audit + full build verification

**Task:** Review all external links added in Steps 1–3. This step may touch multiple files in Section 4.

1. Compile a list of every external URL added in Steps 1–3.
2. Confirm link accuracy and proxy URL decisions with the user.
3. Update any links that need the `uidaho.idm.oclc.org` proxy wrapper.
4. Run `bundle exec jekyll serve` and verify:
   - All 3 Section 4 child pages render with full content
   - Section 4 index page has expanded description
   - All 4 section index pages display the yellow multimedia placeholder callout
   - All external links are present and correctly formatted
   - Contact page is unchanged and still functional
   - Homepage still links correctly to all sections
   - No broken internal navigation
   - No build warnings or errors
   - Site branding still matches data-management-guide

**Verification:** All checks pass. Site builds cleanly with complete Section 4 content and multimedia callouts on all section index pages.

---

## Exit checklist

- [ ] `bundle exec jekyll serve` builds without errors
- [ ] Section 4 index page has expanded section description (2–3 sentences, not placeholder)
- [ ] Section 4: all 3 child pages have complete, near-final content
- [ ] Section 4: `appropriate-use.md` has in-page video placeholder callout (FR-S4-2)
- [ ] All external links in Section 4 are present and correctly formatted
- [ ] All external links have been reviewed for proxy URL applicability
- [ ] Proxy URLs applied where needed (per user confirmation)
- [ ] Multimedia placeholder callout boxes (yellow alerts) are visible on all 4 section index pages (FR-INFRA-6)
- [ ] Content follows style conventions (one sentence per line, blank lines between elements, H1 at top, logical headers)
- [ ] No `layout:` added to front matter
- [ ] No cross-links added (deferred to Phase 4)
- [ ] Contact page is unchanged and functional
- [ ] No blank pages — every page has substantive content
- [ ] All Section 4 pages target 600–1500 words
- [ ] Navigation still works correctly (sidebar, footer, aux links)
- [ ] Branding still matches data-management-guide
