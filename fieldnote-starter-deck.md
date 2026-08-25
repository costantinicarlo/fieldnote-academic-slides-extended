---
theme: fieldnote-academic.css
highlightTheme: vs2015
width: 1280
height: 720
margin: 0.055
minScale: 0.2
maxScale: 2.0
center: false
controls: true
controlsLayout: bottom-right
progress: true
slideNumber: "c/t"
transition: fade
transitionSpeed: fast
---

<!-- .slide: class="title-slide" -->

ACADEMIC TALK · COURSE · SEMINAR <!-- element class="eyebrow" -->

# A clear title framed as a scientific question or claim

A concise subtitle defining the system, scale, and purpose of the presentation. <!-- element class="subtitle" -->

**Your Name** · Institution · Event · 25 August 2026 <!-- element class="byline" -->

note:
Open with the problem and why it matters. Avoid reading the title verbatim.

---

<!-- slide bg="#132927" -->
<!-- .slide: class="section-slide" -->

01 · ORIENTATION <!-- element class="eyebrow" -->

# Begin with the problem, not the agenda

The section divider resets attention and states the next intellectual move. <!-- element class="subtitle" -->

---

## Frame one question per slide

What process could generate the observed pattern? <!-- element class="lead" -->

- State the empirical pattern.
- Name the competing explanations.
- Tell the audience what evidence would distinguish them.

> [!question] Decision point
> What should the audience believe or do differently after this slide?

Source or context can sit here without competing with the argument. <!-- element class="source" -->

---

<!-- slide template="[[fieldnote-academic/templates/fieldnote-two-column]]" -->

::: title
## Separate observation from interpretation
:::

::: left
### What the data show

- A repeatable spatial or temporal pattern
- An estimated effect with uncertainty
- A result robust to the principal sensitivity checks
:::

::: right
### What remains inferred

- The causal mechanism
- Generality outside the sampled system
- Consequences at another biological scale

> [!uncertainty] Keep uncertainty visible
> Distinguish absence of evidence from evidence of absence.
:::

::: source
Illustrative structure — replace with primary sources and analysis identifiers.
:::

---

<!-- slide template="[[fieldnote-academic/templates/fieldnote-figure-focus]]" -->

::: title
## Give the principal figure most of the slide
:::

::: figure
<div class="figure-placeholder">Figure · map · photograph · diagram</div>
:::

::: interpretation
### Read the pattern

**Direction:** state the visible trend.

**Magnitude:** report the scale that matters.

**Uncertainty:** show what remains unresolved.
:::

::: source
Source: Author et al. (Year), figure or dataset identifier; analysis version.
:::

---

<!-- .slide: class="compact" -->

## Tables: retain only decision-relevant values

| Population | Estimate | 95% interval | Sample size | Interpretation |
|---|---:|---:|---:|---|
| Estuary | 0.42 | 0.31–0.54 | 86 | Higher tolerance |
| Inland | 0.18 | 0.09–0.29 | 91 | Reference range |
| Hybrid zone | 0.31 | 0.22–0.41 | 74 | Intermediate |

- Align numbers to support scanning.
- Round to the precision justified by the data.
- Move exhaustive tables to backup slides or a handout.

Illustrative values only. <!-- element class="source" -->

---

<!-- .slide: class="equation-slide" -->

## Equations need a verbal interpretation

$$
R_0 = \frac{m a^2 b c p^n}{-r\ln(p)}
$$

> [!evidence] Read the structure aloud
> Transmission potential rises quadratically with biting rate, while adult survival acts repeatedly through the extrinsic incubation period.

Define symbols only once; then use the equation to support reasoning rather than as decoration. <!-- element class="muted" -->

---

<!-- .slide: class="compact-code" -->

## Code: one operation, one reason

```r
fit <- brm(
  tolerance ~ salinity * taxon + (1 | population),
  data = larvae,
  family = gaussian(),
  chains = 4,
  cores = 4,
  seed = 20260825
)
```

- Show only the lines needed to understand the analytical decision.
- Put long commands or output on a backup slide.
- Add `wrap-code` to the slide class for unavoidable long lines.

---

## Methods: reveal the logic, not every command

```mermaid
flowchart LR
    A[Question] --> B[Sampling design]
    B --> C[Measurement]
    C --> D[Model]
    D --> E[Posterior checks]
    E --> F[Biological inference]
```

The audience should be able to reconstruct why each step exists. <!-- element class="lead" -->

---

<!-- slide bg="#e2f0ed" -->
<!-- .slide: class="takeaway-slide" -->

TAKE-HOME MESSAGE <!-- element class="eyebrow" -->

# A conclusion should be a claim, not a topic label

State what the evidence changes, preserve the important qualification, and make the next question explicit. <!-- element class="lead" -->

---

<!-- slide bg="#132927" -->
<!-- .slide: class="questions-slide" -->

# Questions

Thank you <!-- element class="subtitle" -->

**Possible discussion prompts:** mechanism · uncertainty · generality · next experiment <!-- element class="discussion-prompts" -->
