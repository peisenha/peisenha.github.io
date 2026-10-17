# CLAUDE.md

Shared conventions: see `../GUIDELINES.md` for cross-site standards (design tokens,
typography, responsive breakpoints, content principles).

## Project overview

Static personal website for Philipp Eisenhauer, hosted via GitHub Pages at
peisenha.github.io. Two-page site covering professional profile and operating
principles. Deployed to GitHub Pages via a deploy workflow.

## Development setup

No build step. Open any `.html` file under `site/` in a browser to preview. Deploy happens
automatically on push to main via `.github/workflows/deploy.yml` (publishes `site/` directory).

## Common commands

- `python -m http.server -d site` — serve locally at localhost:8000 for preview
- `git push origin main` — deploy to GitHub Pages (triggers CI)

## Architecture

- `site/` — deployable website directory (published to GitHub Pages)
  - `index.html` — home page: header, positioning, showcase (incl. teaching), speaking, experience, publications
  - `operating-principles.html` — operating principles: foundation, iteration (Learn/Decide/Repeat), leverage
  - `styles.css` — shared stylesheet across all pages
  - `assets/` — images and SVG assets (`{page}-{subject}.{ext}` naming)
- `.github/workflows/deploy.yml` — GitHub Pages deployment workflow

## Verification

1. Open each HTML page under `site/` in a browser and verify navigation links work
2. Verify all external links open correctly (LinkedIn, GitHub, publications)
3. Check mobile responsiveness at 768px and 480px breakpoints
4. Push to GitHub and confirm deploy workflow passes

## Key conventions

- Pure static HTML/CSS — no build tools, no frameworks, no JavaScript beyond the analytics snippet
- No inline styles; every look lives in `styles.css`
- All pages share the same nav (Home / Principles), font stack, and `styles.css`
- Google Analytics — gtag snippet (G-00JS1JND0F) included in every page's `<head>`
- Active nav link uses `aria-current="page"`

## Cross-page structure (MUST maintain symmetry)

### Navigation

`Home` / `Principles` — consistent across all pages.

### Page structure

All pages follow the same skeleton:

1. `<nav>` — sticky gradient bar with two links
2. `<div class="content">` → `<header>` (title + optional subtitle/epigraph) → `<main>`
3. `<header>` has bottom border with 120px accent gradient overlay

### Section headings

| Page | Sections |
|------|----------|
| Home (index.html) | Science × Engineering × Judgment / Showcase / Speaking / Experience / Publications |
| Principles | Foundation / Iteration / Leverage |

### Showcase cards (index.html)

Three cards with badge labels matching the positioning formula, followed by a
transition paragraph and a **Teaching** card (Impact-Driven Business Decisions):

- **Science** — Structural Models for Policy-Making
- **Engineering** — Impact Engine
- **Judgment** — Addressing Gen AI's Quality-Control Problem

### Speaking (index.html)

One card per talk topic (`Talk` badge, topic title, short narrative). Add a card only for a
new argument; new venues for an existing talk do not change the site.
