# Fieldnote Academic — pattern library

Copy the patterns you need into a Slides Extended deck using `fieldnote-academic.css`.

## 1. Canonical frontmatter

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

For a legacy 4:3 projector, change only `width: 960` and `height: 720`.

## 2. Title slide

```md
<!-- .slide: class="title-slide" -->

COURSE · SEMINAR · CONFERENCE <!-- element class="eyebrow" -->

# The title

A concise subtitle. <!-- element class="subtitle" -->

**Name** · Institution · Date <!-- element class="byline" -->
```

Optional lower-right logo:

```md
![[logo.svg|118]] <!-- element class="corner-logo" -->
```

## 3. Section divider

```md
<!-- slide bg="#132927" -->
<!-- .slide: class="section-slide" -->

02 · EVIDENCE <!-- element class="eyebrow" -->

# The next intellectual move

One orienting sentence. <!-- element class="subtitle" -->
```

## 4. Standard argument slide

```md
## A declarative heading

The main claim in one sentence. <!-- element class="lead" -->

- Evidence one
- Evidence two
- Qualification

Source: Author et al. (Year). <!-- element class="source" -->
```

## 5. Figure slide

```md
<!-- .slide: class="figure-slide" -->

## The finding, not “Results”

![[figures/result.png|900]]

What the audience should notice. <!-- element class="caption" -->

Source: Author et al. (Year), Fig. 2. <!-- element class="source" -->
```

Add `full-figure` to the slide class when the image should use nearly all available height:

```md
<!-- .slide: class="figure-slide full-figure" -->
```

Add `framed` when a pale figure needs a visible edge:

```md
![[figures/result.png|900]] <!-- element class="framed" -->
```

## 6. Reusable two-column template

```md
<!-- slide template="[[fieldnote-academic/templates/fieldnote-two-column]]" -->

::: title
## Comparison or paired argument
:::

::: left
### Left heading

- Point
- Point
:::

::: right
### Right heading

- Point
- Point
:::

::: source
Source or methodological note.
:::
```

## 7. Reusable figure-focus template

```md
<!-- slide template="[[fieldnote-academic/templates/fieldnote-figure-focus]]" -->

::: title
## The finding expressed as a claim
:::

::: figure
![[figures/result.png|820]]
:::

::: interpretation
### Interpretation

**Pattern:** …

**Magnitude:** …

**Caveat:** …
:::

::: source
Source: Author et al. (Year), Fig. X.
:::
```

## 8. Evidence, uncertainty, and caution callouts

```md
> [!evidence] Evidence
> What is directly supported.

> [!uncertainty] Uncertainty
> What remains imprecise or unidentified.

> [!danger] Invalid inference
> What the data cannot establish.
```

## 9. Table modes

Normal slide:

```md
<!-- .slide: class="compact" -->
```

Large or exhaustive table:

```md
<!-- .slide: class="dense" -->
```

Use `dense` sparingly; projection legibility is usually more important than completeness.

## 10. Code modes

Readable default code:

```md
<!-- .slide: class="compact-code" -->
```

Long lines that must wrap:

```md
<!-- .slide: class="compact-code wrap-code" -->
```

## 11. Take-home slide

```md
<!-- slide bg="#e2f0ed" -->
<!-- .slide: class="takeaway-slide" -->

TAKE-HOME MESSAGE <!-- element class="eyebrow" -->

# The conclusion as a claim

The qualification and implication. <!-- element class="lead" -->
```

## 12. Questions slide

```md
<!-- slide bg="#132927" -->
<!-- .slide: class="questions-slide" -->

# Questions

Thank you <!-- element class="subtitle" -->
```
