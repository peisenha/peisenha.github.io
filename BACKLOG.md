# Personal Website Backlog

## Current state

Three-page static site is live at peisenha.github.io. Profile page has positioning,
showcase cards, experience, publications, and teaching. Principles and memos pages exist
but memos section has only a placeholder.

## Phase 0 — Positioning and Experience Rewrite

**Status**: planned

### Goal

Rewrite the profile page to lead with the problem (not the intersection), add results to
experience entries, and add a "currently" signal to the header.

### Key changes

- Rewrite positioning paragraph: open with the organizational pain point, then introduce
  the Science × Engineering × Decision formula as the response
- Add result statements to each Experience entry (Amazon: HBR publication + scale of
  decisions; UW: cross-department reach; Bonn: IER paper + software legacy)
- Add a "currently" line to the header area

## Phase 1 — Memos Section

**Status**: planned

### Goal

Either populate the validation memo with real content or remove the placeholder. Add at
least one additional memo to demonstrate depth.

### Key changes

- Write or remove `memos/validation.html`
- Add 1-2 new memos (candidates: experimentation design, portfolio allocation, evidence
  quality)

## Phase 2 — Operating Principles Update

**Status**: planned

### Goal

Add the "transfer" principle — design for others to carry forward without you — which is
the most distinctive element of Philipp's operating style but currently absent from the
principles page.

### Key changes

- Add a fourth section to operating-principles.html covering transfer / building for
  independence

## Phase 3 — Technical Improvements

**Status**: planned

### Goal

Extract shared CSS and improve maintainability.

### Key changes

- Extract inline CSS into a shared stylesheet (`assets/style.css`)
- Ensure all pages reference the shared stylesheet
- Verify responsive breakpoints still work across all pages