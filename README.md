# Fieldnote Academic

**Fieldnote Academic** is a minimalist academic presentation theme for the [Slides Extended](https://github.com/ebullient/obsidian-slides-extended) Obsidian plugin and Reveal.js.

It is designed for scientific and university presentations where the content should dominate the visual design: lectures, seminars, conference talks, lab meetings, methods presentations, figures, equations, code, quotations, and evidence-rich slides.

![Fieldnote Academic preview](preview-contact-sheet.png)

## Design principles

Fieldnote Academic uses a warm-white canvas, graphite typography, a restrained deep-teal accent, generous whitespace, and dark section dividers. It provides visual hierarchy without competing with scientific content.

Version **0.1.1** fixes a rendering regression in ordinary Slides Extended sections caused by slide-level overflow clipping and removes a display override that could interfere with Reveal.js slide state management.

## Quick start

1. Copy `assets/css/fieldnote-academic.css` and the optional `templates/` directory into your Slides Extended assets directory.
2. Set the deck theme in YAML frontmatter:

```yaml
theme: fieldnote-academic.css
width: 1280
height: 720
center: false
```

3. Use `fieldnote-starter-deck.md` as a starting point and `fieldnote-pattern-library.md` as a copy-and-paste layout reference.

See [docs/USAGE.md](docs/USAGE.md) for installation details and diagnostics.

## Repository contents

- `assets/css/fieldnote-academic.css` — the theme
- `templates/` — optional layout templates
- `fieldnote-starter-deck.md` — example deck
- `fieldnote-pattern-library.md` — reusable slide patterns
- `fieldnote-render-smoke-test.md` — regression test deck
- `preview-contact-sheet.png` — visual overview
- `CHANGELOG.md` — version history
- `docs/USAGE.md` — detailed usage notes

## Versioning

Semantic version tags preserve each published state of the theme.

## License

Fieldnote Academic is released under the [MIT License](LICENSE).
