# Design: Personal Website

## Motivation

The site serves as Philipp's public-facing professional presence — the place where hiring
managers, academics, business decision-makers, and students form their first impression.
Each page has a distinct job: the profile page establishes credibility, the principles page
reveals how he thinks, and the memos page demonstrates depth on specific topics.

## Architecture overview

```
site/                          Deployable website directory
  index.html                   "Who is this person and why should I care?"
    ├── Positioning            Science × Engineering × Decision formula
    ├── Showcase               Three flagship items (Science / Engineering / Decision)
    ├── Experience             Career timeline with results
    ├── Publications           Business + Academic tracks
    └── Teaching               Course portfolio
  operating-principles.html    "How does he think?"
    ├── Foundation             Curiosity, Action, Rigor
    ├── Iteration              Learn · Decide · Repeat cycle
    └── Leverage               Speed × Scale
  memos.html                   "Can he go deep?"
    └── memos/validation.html  Individual memo pages
  styles.css                   Shared styles
  assets/                      Images and SVG assets ({page}-{subject}.{ext})
```

All pages are static HTML sharing one stylesheet. No build step, no templating engine.
The site deploys to GitHub Pages on push to main.

## Components

| File | Role |
|------|------|
| `site/index.html` | Profile — first impression, credibility, breadth of work |
| `site/operating-principles.html` | Principles — thinking framework, distinguishes from generic profiles |
| `site/memos.html` | Memos index — signals depth and writing ability |
| `site/memos/*.html` | Individual memos — standalone technical write-ups |
| `site/styles.css` | Full stylesheet: layout, typography, cards, responsive breakpoints |
| `.github/workflows/deploy.yml` | GitHub Pages deployment workflow |

## Data flow

Static site — no runtime data flow. Content is authored directly in HTML. The only
dynamic element is Google Analytics (gtag.js) sending pageview events.

Navigation is flat: every page links to every other page via the shared `<nav>` bar.
No hierarchy beyond the memos index linking to individual memo pages.

## Future directions

- **Audience-aware entry points** — the three showcase cards (Science / Engineering /
  Decision) could serve as distinct landing paths for different audiences
- **Memo expansion** — populate the validation memo and add additional memos on
  topics like experimentation design, portfolio allocation, or evidence quality
- **Current work signal** — add a "currently working on" section to signal activity
  and currency
