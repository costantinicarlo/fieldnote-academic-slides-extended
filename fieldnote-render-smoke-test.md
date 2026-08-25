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

All three slides should remain independently navigable. <!-- element class="lead" -->
