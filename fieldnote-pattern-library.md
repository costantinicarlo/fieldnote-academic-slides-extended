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

## 13. Acknowledgments and support slide

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

**Team**

- Name · contribution
- Name · contribution

**Collaborators**

- Institution or community

<div class="ack-closing">Thank you</div>
:::

::: support
### Support

ANR project · grant number  
Core facility · permit · data provider
:::

::: logos
![[logos/institution.svg|140]]
![[logos/funder.svg|140]]
![[logos/partner.svg|140]]
:::
```

The `visuals` area forms a responsive mosaic: one image fills it, two sit side by side, three use one wide image above two smaller images, and four form a 2 × 2 grid. Keep each image on its own paragraph. Photos are cropped to fill their cells; add `top-focus` when faces are near the upper edge, or `contain` when cropping is undesirable. Logos are contained in neutral white tiles so marks with different proportions can coexist cleanly.

## 14. Clickable selected references

Treat the preceding acknowledgments slide as the live stopping point; place this bibliography afterward as an online appendix.


Single-column version for approximately three to five full references:

```md
<!-- .slide: class="references-slide" -->
<!-- slide template="[[fieldnote-academic/templates/fieldnote-references]]" -->

::: title
## Selected references
:::

::: references
1. Wilkinson, M. D. et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data* **3**, 160018. <a href="https://doi.org/10.1038/sdata.2016.18" target="_blank" rel="noopener noreferrer">10.1038/sdata.2016.18</a>

2. Munafò, M. R. et al. (2017). A manifesto for reproducible science. *Nature Human Behaviour* **1**, 0021. <a href="https://doi.org/10.1038/s41562-016-0021" target="_blank" rel="noopener noreferrer">10.1038/s41562-016-0021</a>
:::

::: note
Selected references only; split a long bibliography across multiple slides.
:::
```

Add `reference-columns` for approximately six to ten concise references:

```md
<!-- .slide: class="references-slide reference-columns" -->
```

A normal Markdown link is also valid:

```md
[10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18)
```

The raw HTML form shown above adds `target="_blank"`, so an online reader does not leave the slideshow when following the DOI.
