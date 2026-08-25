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

<!-- .slide: class="title-slide" -->

RENDERING TEST <!-- element class="eyebrow" -->

# Archetype slide before ordinary content

This slide should render normally. <!-- element class="subtitle" -->

---

## Ordinary content must remain visible

If this heading, paragraph, list, and callout are visible, the clipping regression is fixed. <!-- element class="lead" -->

- Ordinary Markdown content
- No full-height archetype class
- Content produced inside the Slides Extended canvas wrapper

> [!evidence] Expected result
> The complete slide is visible in both the plugin preview and browser presentation.

---

<!-- slide bg="#e2f0ed" -->
<!-- .slide: class="takeaway-slide" -->

RENDERING TEST PASSED <!-- element class="eyebrow" -->

# Archetype slide after ordinary content

The first three regression slides should remain independently navigable. <!-- element class="lead" -->

---

<!-- .slide: class="acknowledgments-slide" -->
<!-- slide template="[[fieldnote-academic/templates/fieldnote-acknowledgments]]" -->

::: title
## New archetype: acknowledgments
:::

::: visuals
<div class="photo-placeholder">Hero photo</div>

<div class="photo-placeholder">Photo two</div>

<div class="photo-placeholder">Photo three</div>
:::

::: people
### People

- Contributor one
- Contributor two

<div class="ack-closing">Questions welcome</div>
:::

::: support
### Support

Grant · facility
:::

::: logos
<span class="logo-placeholder">Logo A</span>
<span class="logo-placeholder">Logo B</span>
:::

---

<!-- .slide: class="references-slide" -->
<!-- slide template="[[fieldnote-academic/templates/fieldnote-references]]" -->

::: title
## New archetype: clickable references
:::

::: references
1. Wilkinson, M. D. et al. (2016). FAIR Guiding Principles. <a href="https://doi.org/10.1038/sdata.2016.18" target="_blank" rel="noopener noreferrer">10.1038/sdata.2016.18</a>

2. Munafò, M. R. et al. (2017). A manifesto for reproducible science. <a href="https://doi.org/10.1038/s41562-016-0021" target="_blank" rel="noopener noreferrer">10.1038/s41562-016-0021</a>
:::

::: note
Both links should be visible and clickable in browser presentation.
:::

