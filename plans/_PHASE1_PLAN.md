# Phase 1 Implementation Plan — Walking Skeleton

Based on `_SPEC.md` §10 Phase 1. The goal is a Jekyll site that builds, matches the data-management-guide branding, and has all navigation pages in place with placeholder content.

## Prerequisites

### P-0: Install Ruby and Bundler in WSL

The WSL environment has no Ruby. Install it so we can build and test locally.

1. Install Ruby via `apt` (the `github-pages` gem pins Ruby compatibility, so the system Ruby from `apt` is fine).
2. Install Bundler.
3. Run `bundle install` in the project directory to install Jekyll and dependencies.

**Verification:** `bundle exec jekyll --version` prints a version number.

---

## Steps

### Step 1: Initialize git repo and commit the copied theme files

Create a clean baseline before any modifications.

1. `git init` in the project directory.
2. Create an initial commit with all copied theme files as-is, so we have a clean diff baseline.

**Verification:** `git log --oneline` shows one commit. `git status` is clean.

---

### Step 2: Update `_config.yml`

Modify the following fields (line numbers reference the current file):

| Line(s) | Field | Old value | New value |
|---|---|---|---|
| 1–8 | Header comment | References data-management-guide | References engr_stu_site |
| 15 | `title` | `U of I Library Data Management Guide` | `Library Use for ECE Students` |
| 16 | `description` | Data management paragraph | One sentence about helping ECE students navigate library resources for research papers |
| 17 | `baseurl` | `/services/data/data-management` | `/PLACEHOLDER` (TBD before deployment) |
| 62–64 | `aux_links` | `"U of I Library Data Services"` → data services URL | `"U of I Library"` → `https://www.lib.uidaho.edu/` |
| 89 | `gh_edit_repository` | data-management-guide repo URL | Placeholder or new repo URL (TBD) |
| 123–126 | `collections: glossary` | Glossary collection config | Remove entirely (glossary is out of scope per spec §7) |

All other fields (search config, color scheme, permalink, defaults, kramdown, `lib-media`, etc.) remain unchanged. The `lib-media` variable points to the same U of I Library media server used for logos — correct for this project too.

**Note on `defaults` block:** The `path: "guide/*"` default applies `layout: "page"` to all files under `guide/`. Pages under `guide/` should NOT include `layout:` in their front matter — it is inherited automatically.

**Verification:** `bundle exec jekyll serve` runs without errors after this change. The site title in the browser tab reads "Library Use for ECE Students."

---

### Step 3: Update `_includes/footer_custom.html`

Replace the three footer navigation links:

| Current link | New link |
|---|---|
| `GUIDE HOME` → `/` | `GUIDE HOME` → `{{ '/' \| relative_url }}` (unchanged) |
| `DATA HUB` → `https://www.lib.uidaho.edu/datahub/` | `U OF I LIBRARY` → `https://www.lib.uidaho.edu/` |
| `CONTACTS` → `{{ '/guide/contact/' \| relative_url }}` | `CONTACT` → `{{ '/guide/contact/' \| relative_url }}` (unchanged path, just rename label) |

The logo image URL stays the same (same U of I Library branding).

**Verification:** Footer shows "GUIDE HOME", "U OF I LIBRARY", "CONTACT" with correct links.

---

### Step 4: Update `LICENSE.txt`

Update line 31: change the year from `2019` to `2026` and update the description to reflect this project.

**Verification:** `LICENSE.txt` has two copyright blocks — the original Just the Docs theme (2016) and the U of I Library customizations (2026).

---

### Step 5: Create homepage (`index.md`)

Create `index.md` at the project root with:
- Front matter: `layout: default`, `title: Home`, `nav_order: 0`, `description: "Library Use for ECE Students"` (quoted to avoid YAML parsing issues with special characters). The page `title` is "Home" (used as the sidebar nav label), distinct from the site `title` in `_config.yml` (used in the header/branding).
- H1 heading: "Library Use for ECE Students" (matches the site title).
- One-sentence description of the site's purpose.
- Placeholder Markdown links to the four sections. Use plain Markdown link syntax (`[text](path)`), NOT Liquid `{% link %}` tags, since target pages do not exist yet and `{% link %}` would cause a build failure.

**Verification:** Homepage renders at `/` with the site title, heading, and placeholder content.

---

### Step 6: Create section index pages (4 files)

Create the `guide/` directory structure and four section index pages. Each gets:
- Front matter with `title`, `has_children: true`, and `nav_order`. No `layout:` field — inherited from `_config.yml` defaults.
- H1 heading matching the title.
- One-sentence description of what the section covers.

| File | Title | nav_order |
|---|---|---|
| `guide/scholarly-sources/index.md` | Finding Scholarly Sources | 1 |
| `guide/citation-integrity/index.md` | Citation Integrity | 2 |
| `guide/ieee-format/index.md` | Writing in IEEE Format | 3 |
| `guide/ai-in-research/index.md` | AI in Research | 4 |

**Verification:** All four sections appear in the sidebar navigation in order. Clicking each shows the section page with its heading and description.

---

### Step 7: Create child content pages (12 files)

Create all 12 child pages. Each gets:
- Front matter with `title`, `parent` (must exactly match parent's `title`), and `nav_order`. No `layout:` field — inherited from defaults.
- H1 heading matching the title.
- One-sentence placeholder describing what the page will cover.

**Section 1 — Finding Scholarly Sources:**

| File | Title | nav_order |
|---|---|---|
| `guide/scholarly-sources/scholarly-vs-web.md` | Scholarly vs. Web Sources | 1 |
| `guide/scholarly-sources/ieee-xplore-wos.md` | Navigating IEEE Xplore & Web of Science | 2 |
| `guide/scholarly-sources/google-scholar-jcr.md` | Google Scholar & Verifying Journal Quality | 3 |

**Section 2 — Citation Integrity:**

| File | Title | nav_order |
|---|---|---|
| `guide/citation-integrity/interrogating-sources.md` | Interrogating Your Sources | 1 |
| `guide/citation-integrity/citation-chaining.md` | Citation Chaining | 2 |
| `guide/citation-integrity/citation-pitfalls.md` | Common Citation Pitfalls | 3 |

**Section 3 — Writing in IEEE Format:**

| File | Title | nav_order |
|---|---|---|
| `guide/ieee-format/templates-tools.md` | IEEE Templates & Tools | 1 |
| `guide/ieee-format/structuring-paper.md` | Structuring Your Paper | 2 |
| `guide/ieee-format/citation-practices.md` | IEEE Citation Practices | 3 |

**Section 4 — AI in Research:**

| File | Title | nav_order |
|---|---|---|
| `guide/ai-in-research/ai-tools-limitations.md` | AI Search Tools & Their Limitations | 1 |
| `guide/ai-in-research/appropriate-use.md` | Appropriate vs. Inappropriate AI Use | 2 |
| `guide/ai-in-research/ieee-policy-resources.md` | IEEE AI Policy & U of I Resources | 3 |

**Verification:** All 12 child pages appear under their parent sections in the sidebar. Clicking each shows the page with its heading and placeholder sentence. No broken navigation links.

---

### Step 8: Create contact page (`guide/contact.md`)

Create `guide/contact.md` with:
- Front matter: `title: Contact`, `nav_order: 5` (no parent — top-level page).
- H1 heading.
- Placeholder sentence noting that contact information will be added later.

**Verification:** "Contact" appears in the sidebar below the four sections. The footer "CONTACT" link resolves to this page.

---

### Step 9: Create `README.md`

Create a brief README with:
- Project name and one-line description.
- How to build locally (`bundle install`, `bundle exec jekyll serve`).
- Note that this is based on the data-management-guide theme.

**Verification:** File exists and is accurate.

---

### Step 10: Full build and navigation test

Run `bundle exec jekyll serve` and verify all exit criteria:

1. Site builds with no errors.
2. Homepage renders with correct title and placeholder content.
3. All 4 sections appear in sidebar in correct order.
4. All 12 child pages appear under their parents.
5. Contact page appears in sidebar.
6. All sidebar links navigate correctly.
7. Footer shows "GUIDE HOME", "U OF I LIBRARY", "CONTACT" with correct links.
8. Site header shows "Library Use for ECE Students" title and logo.
9. Aux link (top-right) shows "U of I Library" linking to the library homepage.
10. Branding matches the data-management-guide (same colors, fonts, layout).
11. Search box appears in the header and returns results when searching for a known page title (e.g., "Citation Chaining").

**Verification:** All 11 checks pass.

---

### Step 11: Commit and push

1. Commit all changes (config modifications + new content pages).
2. Initialize remote and push (if remote is set up), or note as pending.

**Verification:** `git log` shows clean commit history. Working tree is clean.

---

## Exit checklist

- [ ] Ruby + Bundler installed in WSL; `bundle exec jekyll serve` works
- [ ] Git repo initialized with clean commit history
- [ ] `_config.yml` updated (title, description, baseurl, aux_links, no glossary collection)
- [ ] `_includes/footer_custom.html` updated (GUIDE HOME, U OF I LIBRARY, CONTACT)
- [ ] `LICENSE.txt` copyright year updated
- [ ] Homepage (`index.md`) exists with placeholder content
- [ ] 4 section index pages exist with correct `has_children` and `nav_order`
- [ ] 12 child pages exist with correct `parent` and `nav_order`
- [ ] Contact page exists at `guide/contact.md`
- [ ] `README.md` exists with build instructions
- [ ] Full navigation works (all sidebar links, footer links, aux link)
- [ ] Branding matches data-management-guide (same theme files, colors, logos)
- [ ] No blank pages — every page has an H1 and placeholder sentence
