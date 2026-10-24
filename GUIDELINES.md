# Website Guidelines

Shared conventions across all websites under `websites/`. Each site is an independent
git repo with its own root docs (README, CLAUDE, DESIGN, BACKLOG, SPRINT). This file
lives in `peisenha.github.io`, which owns the shared design; `websites/GUIDELINES.md`
is a symlink to it, so every site can read it as `../GUIDELINES.md`.

## Sites

| Directory | Purpose | URL |
|-----------|---------|-----|
| `impact-engine/` | Impact Engine project site | eisenhauerio.github.io/websites-impact-engine |
| `peisenha.github.io/` | Personal professional site | peisenha.github.io |
| `escape-velocity/` | Escape Velocity: versioned map of the space economy, read through its decisions | eisenhauerio.github.io/websites-escape-velocity (v1.0 built; repository still private) |

## Technology Stack

- **Pure static HTML/CSS** — no build tools, no frameworks, no templating engines.
  Exception: `escape-velocity/` generates its pages from `ledger/` data with
  `build.py` (Python standard library plus `markdown`, no framework); the output in `site/` is still
  plain static HTML/CSS and follows every convention below
- **Fonts** — Crimson Pro (headings) + Inter (body), loaded from Google Fonts
- **CSS approach** — shared `styles.css` preferred; inline styles only as a temporary state
- **JavaScript** — minimal, only when necessary (e.g., logo injection)
- **Deployment** — GitHub Pages from main branch

## Design Tokens

All sites share the same CSS variable palette:

```css
--primary-color: #1a365d;
--accent-color: #2c5282;
--text-color: #2d3748;
--text-light: #4a5568;
--background: #f7fafc;
--card-background: #ffffff;
--border-color: #e2e8f0;
--hover-color: #edf2f7;
```

These values must not drift between sites.

## Page Structure

Every page follows this skeleton:

1. `<nav>` — sticky top bar with gradient background, centered link list
2. `<div class="content">` — main content area with `<header>` + `<main>`
3. `<header>` — page title, optional epigraph or subtitle, bottom border with accent gradient
4. `<main>` — page-specific content sections

## Navigation

- Each site has its own nav links (not cross-site)
- Active page uses `aria-current="page"`
- Nav links are simple text — no icons, no dropdowns

## Typography

- `h1` — Crimson Pro, 3em+, `--primary-color`
- `h2` — Crimson Pro, 2em, `--primary-color`, gradient underline accent (60px)
- `h3` — Inter, 1.3-1.4em, `--accent-color`
- Body — Inter, `line-height: 1.7-1.8`, `--text-light`
- Links — `--accent-color`, no underline by default, underline on hover

## Cards

Used for showcase items, positions, memos, and deep-dive links:

- Background: `--hover-color`
- Left border: 4px solid `--accent-color`
- Border radius: 8px
- Hover: slight translateX or translateY + box-shadow

## Responsive Breakpoints

Three tiers, consistent across all sites:

| Breakpoint | Target |
|------------|--------|
| default | Desktop (> 768px) |
| `max-width: 768px` | Tablet |
| `max-width: 480px` | Mobile |

## Analytics

Google Analytics (gtag.js) snippet in every page's `<head>`. Each site has its own
tracking ID — do not share IDs across sites. `escape-velocity/` has none yet.

## Assets

- Static assets live in `site/assets/`
- SVGs preferred over raster images
- Asset naming: `logo-*` for branding, otherwise `{page}-{subject}.{ext}` (e.g., `index-headshot.jpg`, `science-counterfactual.svg`)

## Root Docs (MUST exist in every site repo)

Every site repo must have all 5 root docs:

| File | Purpose |
|------|---------|
| `README.md` | External-facing: title, tagline, problem/solution, live site link |
| `CLAUDE.md` | AI agent onboarding: project overview, setup, architecture, conventions |
| `DESIGN.md` | Architecture decisions: motivation, page structure, components, future directions |
| `BACKLOG.md` | Prioritized work queue with phased items |
| `SPRINT.md` | Current deliverable (or "No active sprint.") |

Follow the `bdc-engagement` skill's schemas for structural conformance.

## Content Principles

- **Result before method** — lead with what happened, then how
- **Problem before solution** — frame the pain point, then the response
- **Enable, don't impress** — the reader should feel smarter, not the author
- **Five-second test** — can someone redraw the key idea from memory? If not, simplify