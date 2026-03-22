# CLAUDE.md

Shared conventions: see `../GUIDELINES.md` for cross-site standards (design tokens,
typography, responsive breakpoints, content principles).

## Project overview

Static personal website for Philipp Eisenhauer, hosted via GitHub Pages at
peisenha.github.io. Three-page site covering professional profile, operating
principles, and technical memos.

## Development setup

No build step. Open any `.html` file in a browser to preview. Deploy happens
automatically on push to main (GitHub Pages publishes from root).

## Common commands

- `python -m http.server 8000` — serve locally at localhost:8000 for preview
- `git push origin main` — deploy to GitHub Pages

## Architecture

| File | Role |
|------|------|
| `index.html` | Profile page — header, positioning, showcase, experience, publications, teaching, education |
| `operating-principles.html` | Operating principles — foundation, iteration (Learn/Decide/Repeat), leverage |
| `memos.html` | Memos index — links to individual memo pages |
| `memos/validation.html` | Memo: Validation Strategy (placeholder) |
| `assets/headshot.jpg` | Headshot photo |
| `assets/learn-decide-repeat.svg` | Iteration cycle diagram for principles page |

## Verification

1. Open each HTML page in a browser and confirm rendering
2. Verify all internal nav links resolve (Profile, Principles, Memos)
3. Verify all external links open correctly (LinkedIn, GitHub, publications)
4. Check mobile responsiveness at 768px and 480px breakpoints
5. Confirm `git push origin main` deploys successfully

## Key conventions

- Pure static HTML/CSS — no build tools, no frameworks, no JavaScript
- All pages share the same nav (Profile / Principles / Memos), font stack, and design tokens
- CSS is currently inline per page — keep tokens consistent (see GUIDELINES.md for values)
- Google Analytics — gtag snippet (G-00JS1JND0F) included in every page's `<head>`
- Active nav link uses `aria-current="page"`

## Cross-page structure (MUST maintain symmetry)

### Navigation

`Profile` / `Principles` / `Memos` — consistent across all pages.

### Page structure

All pages follow the same skeleton:

1. `<nav>` — sticky gradient bar with three links
2. `<div class="content">` → `<header>` (title + optional subtitle/epigraph) → `<main>`
3. `<header>` has bottom border with 120px accent gradient overlay

### Section headings

| Page | Sections |
|------|----------|
| Profile (index.html) | Science × Engineering × Decision / Showcase / Experience / Publications / Teaching / Education |
| Principles | Foundation / Iteration / Leverage |
| Memos | (card list, no h2 sections) |

### Showcase cards (index.html)

Three cards with badge labels matching the positioning formula:

- **Science** — Structural Models for Policy-Making
- **Engineering** — Impact Engine
- **Decision** — Inside Amazon's AI Factory