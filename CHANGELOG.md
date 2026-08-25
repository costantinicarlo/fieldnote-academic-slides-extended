# Changelog

## 0.2.0 — 25 August 2026

### Added

- `references-slide` and optional `reference-columns` modes for concise selected bibliographies.
- DOI-aware link styling and a documented new-tab anchor pattern for online decks.
- `fieldnote-references.md`, a reusable reference-list template.
- `acknowledgments-slide`, with dedicated areas for photographs, people, support, and logos.
- `fieldnote-acknowledgments.md`, a reusable visual closing-slide template.
- A deterministic one-, two-, three-, or four-image photographic mosaic with optional `top-focus` and `contain` treatments.
- Starter-deck and pattern-library examples for both new archetypes.

### Fixed

- The starter deck now uses the acknowledgment template’s canonical `visuals`, `people`, `support`, and `logos` slots.
- The online references example now uses the reusable reference template and its bottom note area.

### Preserved

- The version 0.1.1 overflow and Reveal display-state repairs.

## 0.1.1 — 25 August 2026

### Fixed

- Ordinary slides no longer disappear while their Reveal background remains visible.
- The generic slide-section rule now preserves visible overflow because Slides Extended places slide content in an absolutely positioned full-canvas wrapper.
- Special slide archetypes no longer force `display: flex !important`, leaving Reveal.js in control of which slide is displayed.

### Added

- `fieldnote-render-smoke-test.md`, a minimal three-slide regression deck covering a special slide, an ordinary slide, and another special slide.

## 0.1.0 — 25 August 2026

- Initial Fieldnote Academic theme, starter deck, pattern library, and optional layout templates.
