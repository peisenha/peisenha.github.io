# Design: Personal Website

## Motivation

The site serves as Philipp's public-facing professional presence — the place where hiring
managers, academics, business decision-makers, and students form their first impression.
Each page has a distinct job: the profile page establishes credibility, and the principles
page reveals how he thinks.

## Architecture overview

```
site/                          Deployable website directory
  index.html                   "Who is this person and why should I care?"
    ├── Positioning            Science × Engineering × Judgment formula
    ├── Showcase               Three flagship items (Science / Engineering / Judgment),
    │                          then a transition paragraph and the Teaching card
    ├── Speaking               One card per talk topic
    ├── Experience             Career timeline with results
    └── Publications           Business, Press, and Academia
  operating-principles.html    "How does he think?"
    ├── Foundation             Curiosity, Action, Rigor
    ├── Iteration              Learn · Decide · Repeat cycle
    └── Leverage               Speed × Scale
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
| `site/styles.css` | Full stylesheet: layout, typography, cards, responsive breakpoints |
| `.github/workflows/deploy.yml` | GitHub Pages deployment workflow |

### Speaking

One card per talk topic, not per venue, so the section grows only when the argument
does. A card reuses the showcase card style: a `Talk` badge, the topic as title, and a
short narrative of what the talk argues. No slides and no venue list; the work the
talk draws on is linked from the showcase above it.

## Data flow

Static site — no runtime data flow. Content is authored directly in HTML. The only
dynamic element is Google Analytics (gtag.js) sending pageview events.

Navigation is flat: every page links to every other page via the shared `<nav>` bar.

## Future directions

- **Audience-aware entry points** — the three showcase cards (Science / Engineering /
  Judgment) could serve as distinct landing paths for different audiences
- **Memos** — a page of standalone write-ups (e.g. experimentation design, portfolio
  allocation, evidence quality) to signal depth
- **Current work signal** — add a "currently working on" section to signal activity
  and currency
