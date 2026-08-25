# Fieldnote Academic

**Fieldnote Academic** is a minimalist academic presentation theme for the [Slides Extended](https://github.com/ebullient/obsidian-slides-extended) Obsidian plugin and Reveal.js.

It is designed for scientific and university presentations where the content should dominate the visual design: lectures, seminars, conference talks, lab meetings, methods presentations, figures, equations, code, quotations, references, acknowledgments, and evidence-rich slides.

![Fieldnote Academic preview](preview-contact-sheet.png)

## Why Fieldnote Academic?

Academic slides have to do several different jobs well: introduce an argument, show data at useful scale, explain methods, present uncertainty, support teaching, and sometimes remain useful after a talk has ended. Fieldnote Academic treats these as a coherent visual system rather than a collection of decorative slide layouts.

The design uses a warm-white canvas, graphite typography, a restrained deep-teal accent, generous whitespace, and dark section dividers. It is intentionally quiet so that figures, equations, photographs, code, and scientific reasoning remain visually dominant.

## Slide system

The theme supports:

- title and section-divider slides;
- ordinary academic content and comparison layouts;
- figure-focused evidence slides;
- equations, code, tables, quotations, callouts, captions, and source lines;
- take-home and questions slides;
- compact and dense variants for information-heavy material;
- **acknowledgments slides** with photographic mosaics, people, financial support, and logo walls;
- **selected-reference slides** with compact, clickable DOI links for online presentations.

The final two archetypes make it possible to use the same deck naturally in two contexts: stop on acknowledgments during a live discussion, or continue to selected references when the slideshow is viewed online.

## Quick start

1. Copy `assets/css/fieldnote-academic.css` and, optionally, `templates/` into your Slides Extended assets directory.
2. Use this frontmatter as a starting point:

```yaml
theme: fieldnote-academic.css
highlightTheme: vs2015
width: 1280
height: 720
margin: 0.055
center: false
controls: true
progress: true
slideNumber: "c/t"
transition: fade
transitionSpeed: fast
```

3. Duplicate `fieldnote-starter-deck.md` for a new presentation.
4. Use `fieldnote-pattern-library.md` when you need a ready-made layout pattern.

For detailed installation, usage, compatibility notes, and customization guidance, see [docs/USAGE.md](docs/USAGE.md).

## Repository contents

- `assets/css/fieldnote-academic.css` — complete theme stylesheet
- `templates/fieldnote-two-column.md` — two-column layout
- `templates/fieldnote-figure-focus.md` — figure + interpretation layout
- `templates/fieldnote-acknowledgments.md` — visual acknowledgments layout
- `templates/fieldnote-references.md` — selected references layout
- `fieldnote-starter-deck.md` — complete demonstration deck
- `fieldnote-pattern-library.md` — copy-and-paste pattern catalogue
- `fieldnote-render-smoke-test.md` — rendering regression deck
- `preview-contact-sheet.png` — overview of the visual system
- `acknowledgments-preview.png` — acknowledgments example
- `references-preview.png` — selected references example
- `CHANGELOG.md` — version history
- `docs/USAGE.md` — detailed user guide

## Selected references and DOI links

For online decks, DOI links can be written as ordinary HTML anchors:

```html
<a class="doi-link"
   href="https://doi.org/10.xxxx/example"
   target="_blank"
   rel="noopener noreferrer">
  doi:10.xxxx/example
</a>
```

The `references-slide` archetype supports a single-column bibliography or an optional `reference-columns` class for a larger selected bibliography.

## Acknowledgments

The `acknowledgments-slide` archetype provides distinct regions for photographs, contributors, financial support, and logos. The photograph mosaic adapts to one to four images and can use `contain` or `top-focus` utility classes where cropping needs to be controlled.

## Compatibility

Fieldnote Academic targets Slides Extended and its bundled Reveal.js runtime. The theme is local-first and has no dependency on remote fonts, remote JavaScript, or hosted design assets.

The canonical canvas is **1280 × 720 (16:9)**. A conventional **960 × 720 (4:3)** deck can be produced by changing the frontmatter dimensions; the theme itself does not need to be rewritten.

## Releases and tags

- `v0.1.0` — initial design system
- `v0.1.1` — rendering compatibility fix
- `v0.2.0` — acknowledgments and selected-reference archetypes

Only milestone versions intended for general use need a GitHub Release. The current release is **v0.2.0**.

## License

Fieldnote Academic is released under the [MIT License](LICENSE).
