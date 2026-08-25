# Changelog

## 0.1.1 — 25 August 2026

### Fixed

- Ordinary slides no longer disappear while their Reveal background remains visible.
- The generic slide-section rule now preserves visible overflow because Slides Extended places slide content in an absolutely positioned full-canvas wrapper.
- Special slide archetypes no longer force `display: flex !important`, leaving Reveal.js in control of which slide is displayed.

### Added

- `fieldnote-render-smoke-test.md`, a minimal three-slide regression deck covering a special slide, an ordinary slide, and another special slide.

## 0.1.0 — 25 August 2026

- Initial Fieldnote Academic theme, starter deck, pattern library, and optional layout templates.
