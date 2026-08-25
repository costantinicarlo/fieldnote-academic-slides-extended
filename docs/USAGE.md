# Fieldnote Academic

A local, minimalist, research-oriented theme system for the Obsidian **Slides Extended** plugin.

## Design character

Fieldnote Academic uses a warm-white canvas, graphite typography, a deep-teal accent, and dark section dividers. It is intentionally restrained: hierarchy comes from scale, spacing, and contrast rather than decorative effects.

It is designed for:

- lectures and graduate teaching;
- conference and seminar talks;
- research-group presentations;
- figure-, map-, table-, equation-, Mermaid-, and code-heavy material;
- both live presentation and HTML/PDF export.

No network connection is required. The font stack uses locally available system fonts and degrades gracefully across macOS, Windows, and Linux.

## Included files

```text
fieldnote-academic/
├── assets/
│   └── css/
│       └── fieldnote-academic.css
├── templates/
│   ├── fieldnote-figure-focus.md
│   └── fieldnote-two-column.md
├── CHANGELOG.md
├── fieldnote-pattern-library.md
├── fieldnote-render-smoke-test.md
├── fieldnote-starter-deck.md
├── preview-contact-sheet.png
└── README.md
```

The CSS theme is sufficient on its own. The two Markdown templates are optional conveniences for layouts that otherwise require repetitive grid markup. The contact sheet is an illustrative design preview; exact line breaks depend on the fonts installed on the presenting computer.

## Version 0.1.1 rendering fix

Version 0.1.0 incorrectly applied `overflow: hidden` to every Reveal slide section. Slides Extended places each slide inside an absolutely positioned full-canvas grid, so ordinary sections have no intrinsic content height; clipping those sections made the slide background visible while hiding all slide content. Version 0.1.1 keeps section overflow visible and no longer overrides Reveal's display state for the four special slide archetypes.

Replace the earlier CSS file with the version included here. The Markdown deck and optional templates remain compatible and require no content changes.

### Verify the repair

Open `fieldnote-render-smoke-test.md` in Slides Extended. It deliberately places one ordinary slide between two special archetype slides. All three slides should show their full content and remain independently navigable in both preview and browser presentation.

A restart of Obsidian is normally unnecessary, but close and reopen the presentation preview after replacing the CSS so the embedded browser reloads the stylesheet.

## Installation

1. Copy the complete `fieldnote-academic` directory into your Obsidian vault.
2. Open **Settings → Slides Extended**.
3. Set the plugin’s **Assets directory** to `fieldnote-academic/assets`.
4. Duplicate `fieldnote-starter-deck.md` when beginning a new presentation.
5. Keep this frontmatter entry in the deck:

```yaml
theme: fieldnote-academic.css
```

The plugin searches the `css` subdirectory of the selected assets directory, so no absolute path is needed in the frontmatter.

## Recommended deck settings

```yaml
---
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
---
```

This is a 16:9 canvas. For a 4:3 room or projector, use:

```yaml
width: 960
height: 720
```

The layout classes and templates use relative dimensions and remain usable in both ratios, although figure placement should always be checked before presenting.

## Core slide classes

Add classes through Slides Extended slide annotations:

```md
<!-- .slide: class="title-slide" -->
```

Available slide classes:

| Class | Purpose |
|---|---|
| `title-slide` | Opening slide with strong left edge and generous whitespace |
| `section-slide` | Dark section divider |
| `figure-slide` | Centered figure with heading and source aligned left |
| `full-figure` | Allows a figure to use nearly all slide height |
| `takeaway-slide` | Pale-teal conclusion slide |
| `questions-slide` | Dark closing/discussion slide |
| `dark-slide` | Generic light-on-dark content slide |
| `centered` | Centers the slide’s principal content |
| `compact` | Moderately reduces content scale |
| `dense` | Stronger reduction for unavoidable dense tables |
| `compact-code` | Smaller code for longer but still readable listings |
| `wrap-code` | Wraps long code or command lines |

Useful element classes:

| Class | Purpose |
|---|---|
| `eyebrow` | Small uppercase context label |
| `lead` | One-sentence principal claim |
| `subtitle` | Secondary title or orienting text |
| `byline` | Presenter, affiliation, event, and date |
| `caption` | Figure interpretation or caption |
| `source` | Small source line fixed at the lower left |
| `corner-logo` | Optional institutional logo at lower right |
| `framed` | Fine border around pale figures |
| `muted` | Secondary text |
| `badge` | Small categorical label |
| `key-number` | Large numerical result |
| `key-label` | Label paired with a key number |

Element classes use this syntax:

```md
A concise principal claim. <!-- element class="lead" -->
```

## Optional layout templates

The included templates are ordinary Markdown notes and can be called by wikilink.

Two-column layout:

```md
<!-- slide template="[[fieldnote-academic/templates/fieldnote-two-column]]" -->

::: title
## Slide heading
:::

::: left
Left content
:::

::: right
Right content
:::

::: source
Optional source line
:::
```

Figure-focus layout:

```md
<!-- slide template="[[fieldnote-academic/templates/fieldnote-figure-focus]]" -->

::: title
## Claim expressed by the figure
:::

::: figure
![[figure.png|820]]
:::

::: interpretation
### Interpretation

**Pattern:** …

**Magnitude:** …

**Caveat:** …
:::

::: source
Optional source line
:::
```

## Compatibility with older custom snippets

Disable or revise any pre-existing snippet that hard-codes `.slides` to `960px × 700px`; it will override the 1280 × 720 frontmatter and distort the 16:9 design.

A previous rule such as:

```css
[data-viewport-size="true"] pre code {
  font-size: 32px !important;
}
```

will also override Fieldnote’s 26 px code setting if it loads later. Keeping 32 px is perfectly reasonable for short teaching examples, but remove the older rule when you want the theme’s normal and compact code modes to control the size.

## Editing the palette

All colors and sizes are tokens at the beginning of `fieldnote-academic.css`. The safest values to customize are:

```css
--fn-canvas: #f7f7f3;
--fn-ink: #18212a;
--fn-muted: #66707a;
--fn-accent: #0b6b63;
--fn-accent-pale: #e2f0ed;
--fn-dark: #132927;
--fn-code-size: 26px;
```

Changing these tokens updates the whole deck consistently.

## Recommended editorial discipline

A strong Fieldnote slide normally contains one intellectual action: pose a question, establish a pattern, compare explanations, expose uncertainty, explain a method, or state a conclusion. Use additional slides rather than shrinking content whenever possible.
