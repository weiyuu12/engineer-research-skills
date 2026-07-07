# Figure Contract

Use this reference before writing plotting code. The goal is to make the figure
serve the paper's scientific logic.

## Privacy rule

Keep the figure contract user-facing, but keep the working trail private. Do not mention
private paths, source filenames, internal reference documents, template identifiers, or
where a private draft came from unless the user explicitly asks for provenance.

## Required contract

Create a short contract in working notes or in the response:

```text
Core conclusion:
Reviewer question:
Visual job:
Figure archetype:
Target journal/output:
Backend: Python or R
Final size:
Panel map:
  a:
  b:
  c:
Evidence hierarchy:
  phenomenon:
  mechanism/process:
  hero evidence:
  validation evidence:
  controls/robustness:
Rejected default chart:
Alternative concepts considered:
Statistics needed:
Source data needed:
Image-integrity notes:
Reviewer risk:
```

Do not start from a favorite template or from the first metric column. Start from the
conclusion and reviewer question, then choose the minimum set of panels that make the
claim clear and defensible. For creative or mechanism/process-oriented work, open
`figure-concept-card.md` and `visual-innovation-atlas.md` before choosing chart types.

## Core conclusion rules

- The core conclusion should be one sentence with a verb: "Treatment X reduces
  Y by restoring Z", not "Treatment results".
- Every panel must answer a unique question. If covering a panel would not weaken
  the argument, remove or merge it.
- Separate primary evidence from supporting evidence. The primary evidence gets
  the hero panel or the clearest axis; controls and robustness panels should be
  visually quieter.
- If the user provides data but no claim, infer a provisional claim from the data
  request and ask for confirmation before final styling.
- If the user provides only metrics, decide whether the main visual should still be a
  mechanism/process/decision panel with metrics as validation rather than the hero panel.

## Archetype selection

| Archetype | Use when | Hero panel | Supporting panels |
|---|---|---|---|
| `quantitative grid` | The claim is mainly numerical comparison | Optional; often a dominant summary metric | Shared axes, aligned scales, compact legends |
| `schematic-led composite` | A workflow, mechanism, device, or experimental design must be understood first | Left or top schematic, 35-60% of area | 2-4 quantitative validation panels |
| `image plate + quant` | Microscopy, imaging, histology, spatial overlays, segmentation, or blots lead the evidence | Image plate or representative image | Scale bars, overlays, crops, quantification |
| `asymmetric mixed-modality figure` | The figure combines schematic, raster images, heatmaps, and quantitative plots | One panel spans rows/columns | Smaller panels ranked by evidence value |

## Panel logic

Use this order unless the manuscript story clearly requires another:

1. Establish the system: sample, method, cohort, device, or experimental design.
2. Show the main effect or primary comparison.
3. Show mechanism or localization.
4. Quantify the representative image or qualitative observation.
5. Add robustness, controls, subgroup analysis, or sensitivity analysis.

For Fig. 1 or a method figure, the first panel often defines the visual vocabulary:
colors, symbols, workflow direction, sample classes, and scale. Reuse that vocabulary
through the whole figure and, where possible, through the manuscript.

## Aesthetic integration

- Use one neutral family, one signal family, and one accent family.
- Keep the same condition/method color across all panels.
- Prefer direct labels for stable line identities, channels, and fixed spatial regions.
- Use a shared legend area when repeated legends would waste space.
- Avoid equal-sized panels when the evidence is not equally important.
- Keep schematic colors and quantitative plot colors related. A schematic-led
  figure should look like one integrated argument, not a pasted collage.

## Reviewer-risk prompts

Before finalizing, ask what a skeptical reviewer would challenge:

- Is the sample size visible in the legend or source data?
- Are error bars, intervals, and statistical tests defined?
- Are axes comparable across panels that invite comparison?
- Are representative images quantified and traceable to raw files?
- Are image adjustments global and documented?
- Could the same conclusion be made from fewer panels?
- Does the figure explain why or how the result occurs, or only report final metrics?
- Is a conventional bar/line/heatmap being used because it is best, or because it was
  the easiest default?
