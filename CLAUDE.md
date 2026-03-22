# CLAUDE.md

## Project overview

Static personal website for Philipp Eisenhauer, hosted via GitHub Pages at
peisenha.github.io. Three-page site covering professional profile, operating
principles, and technical memos.

## Development setup

```bash
# Preview locally — open index.html in a browser, or use a local server:
python -m http.server 8000
```

No build step. All pages are plain HTML with inline CSS.

## Common commands

- `python -m http.server 8000` — local preview server
- `git push origin main` — deploy to GitHub Pages (auto-published from main)

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

- **No build system** — plain HTML with inline `<style>` blocks, no bundler or preprocessor
- **Shared design tokens** — CSS variables (`--primary-color`, `--accent-color`, etc.) are duplicated per page; keep them consistent across all HTML files
- **Navigation** — every page includes the same `<nav>` with three links: Profile, Principles, Memos
- **Google Analytics** — gtag snippet (G-00JS1JND0F) included in every page's `<head>`
- **Fonts** — Crimson Pro (headings) and Inter (body) loaded from Google Fonts on every page
- **Responsive** — three breakpoints: default, 768px, 480px
- **No print statements** — not applicable (static HTML, no server-side code)