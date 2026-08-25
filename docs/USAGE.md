# Fieldnote Academic

A local, minimalist, research-oriented theme system for the Obsidian **Slides Extended** plugin.

## Design character

Fieldnote Academic uses a warm-white canvas, graphite typography, a deep-teal accent, and dark section dividers. It is intentionally restrained: hierarchy comes from scale, spacing, and contrast rather than decorative effects.

It is designed for:

- lectures and graduate teaching;
- conference and seminar talks;
- research-group presentations;
- figure-, map-, table-, equation-, Mermaid-, and code-heavy material;
- both live presentation and online/HTML/PDF publication.

No network connection is required. The font stack uses locally available system fonts and degrades gracefully across macOS, Windows, and Linux.

## Included files

```text
fieldnote-academic/
├── assets/
│   └── css/
│       └── fieldnote-academic.css
├── templates/
│   ├── fieldnote-acknowledgments.md
│   ├── fieldnote-figure-focus.md
│   ├── fieldnote-references.md
│   └── fieldnote-two-column.md
├── CHANGELOG.md
├── acknowledgments-preview.png
├── fieldnote-pattern-library.md
├── fieldnote-render-smoke-test.md
├── fieldnote-starter-deck.md
├── preview-contact-sheet.png
├── references-preview.png
└── README.md
```

The CSS theme is sufficient on its own. The four Markdown templates are optional conveniences for layouts that otherwise require repetitive grid markup. The contact sheet and two closing-slide previews are illustrative; exact line breaks depend on the fonts installed on the presenting computer.

## Version 0.2.0 additions

Version 0.2.0 adds a visual acknowledgments/support archetype and a clickable selected-references archetype. The earlier rendering repair remains intact.

### Online references

Use ordinary Markdown links for DOI resolution, or raw HTML anchors with `target="_blank"` to open a DOI in a new tab. The theme recognizes links whose destination contains `doi.org` and renders them as discreet DOI pills. The Slides Extended `enableLinks` option is not required for external DOI links; that option governs Obsidian wikilinks.

Use a single column for roughly three to five full citations. Add `reference-columns` for approximately six to ten concise entries. Longer bibliographies should be split over multiple slides rather than reduced below comfortable online reading size.

### Acknowledgments and support

The new acknowledgments template reserves a large photographic mosaic, a panel for people and collaborators, a support panel for grants and facilities, and a flexible wall of institutional or funder logos. Keep each photograph on its own Markdown paragraph. One photograph fills the area; two sit side by side; three become one wide image above two supporting images; four form a 2 × 2 mosaic.

A practical dual-use sequence is: take-home message → acknowledgments/questions for the live stopping point → selected references for online readers.

## Version 0.1.1 rendering fix

Version 0.1.0 incorrectly applied `overflow: hidden` to every Reveal slide section. Slides Extended places each slide inside an absolutely positioned full-canvas grid, so ordinary sections have no intrinsic content height; clipping those sections made the slide background visible while hiding all slide content. Version 0.1.1 keeps section overflow visible and no longer overrides Reveal's display state for the four special slide archetypes.

Replace the earlier CSS file with the version included here. The Markdown deck and optional templates remain compatible and require no content changes.

### Verify the repair

Open `fieldnote-render-smoke-test.md` in Slides Extended. Its first three slides preserve the original clipping regression test; two additional slides exercise the acknowledgments and clickable-references archetypes. All five should remain independently navigable in both preview and browser presentation.

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
| `acknowledgments-slide` | Visual closing slide for people, photographs, support, and logos |
| `references-slide` | Selected bibliography with DOI-aware link styling |
| `reference-columns` | Two-column mode for a references slide |
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
| `ack-closing` | Closing phrase inside the acknowledgments people panel |
| `photo-placeholder` | Neutral placeholder for a future team or field photograph |
| `logo-placeholder` | Neutral placeholder for a future institutional or funder logo |
| `top-focus` | Keeps the upper part of a photograph visible when the mosaic crops it |
| `contain` | Fits an image without cropping inside the acknowledgments mosaic |

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

## Acknowledgments template

```md
<!-- .slide: class="acknowledgments-slide" -->
<!-- slide template="[[fieldnote-academic/templates/fieldnote-acknowledgments]]" -->

::: title
## Acknowledgments · questions welcome
:::

::: visuals
![[photos/lab-team.jpg]] <!-- element class="top-focus" -->

![[photos/field-team.jpg]]

![[photos/study-site.jpg]]
:::

::: people
### With thanks to

- Person · contribution
- Partner · contribution

<div class="ack-closing">Thank you</div>
:::

::: support
### Support

Programme · grant identifier · facility
:::

::: logos
![[logos/institution.svg|140]]
![[logos/funder.svg|140]]
:::
```

Photographs use `object-fit: cover` so the mosaic is visually full. Add `top-focus` to a people photograph when faces are near its upper edge, or `contain` when cropping would remove important content.

## Selected-references template

```md
<!-- .slide: class="references-slide reference-columns" -->
<!-- slide template="[[fieldnote-academic/templates/fieldnote-references]]" -->

::: title
## Selected references
:::

::: references
1. Author, A. et al. (Year). Article title. *Journal* **volume**, pages. <a href="https://doi.org/10.xxxx/example" target="_blank" rel="noopener noreferrer">10.xxxx/example</a>
:::

::: note
Selected references only.
:::
```

Use a real DOI in place of the illustrative value. Remove `reference-columns` for a single-column list. The raw HTML anchor opens a DOI in a new tab; an ordinary Markdown link remains fully valid when same-tab navigation is acceptable.

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
