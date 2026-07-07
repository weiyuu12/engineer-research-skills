# Visual Quality Loop

Use this reference whenever the user wants a figure that looks polished, journal-ready,
or closer to a high-impact Nature-family visual style. A figure is not finished just
because the script runs and the export files exist.

## Visual brief before plotting

Before writing plotting code, create a short visual brief in working notes:

```text
Visual family:
  quantitative grid / schematic-led / image plate + quant / clinical triptych /
  asymmetric hero / minimal single-panel
Hero element:
  which panel or mark should be seen first
Density:
  sparse / moderate / dense, and why
Palette roles:
  neutral, primary signal, secondary group, accent/delta
Legend strategy:
  direct labels / shared legend / legend-only axis / no legend
Typography target:
  primary font, Chinese fallback, 3-tier or 4-tier font-size ladder
Layout reserve:
  top title space, bottom legend/x-label space, left y-label space, colorbar/legend space
Main risk:
  crowding / weak hierarchy / too many colors / tiny labels / legend travel /
  misleading scale / same-looking panels / Chinese glyph fallback / blank-heavy layout
Reference pattern:
  closest atlas, demo, Nature archetype, or engineering-reference-atlas ID to adapt
Rejected default:
  why a plain bar / line / heatmap is not enough, or why it is justified
```

If the user provides no aesthetic direction, choose a conservative default:
white background, one hero color family, neutral baselines, direct labels when possible,
small bold lowercase panel labels, and one shared legend outside data regions.
For engineering, deep learning, modeling, simulation, control, robotics, or digital-twin
topics, choose the reference pattern from `engineering-reference-atlas.md` before using
the older bio/chemistry-heavy gallery.

## First-render audit

After the first render, inspect the preview image at the intended final aspect ratio.
Do not rely only on code review. Check:

- **Hierarchy**: one visual element is clearly first; support panels are quieter.
- **Argument structure**: the hero panel carries a mechanism, process, decision, spatial,
  uncertainty, or system-interaction idea when the claim requires more than metric comparison.
- **Whitespace**: panels have enough gutter; labels do not collide with marks or edges;
  blank space supports grouping rather than dominating the page.
- **Typography**: all text remains readable at final size; Chinese text uses one locked
  font family; no clipped characters, fallback boxes, random font switching, or more
  than four font sizes in one figure.
- **Color**: colors have semantic roles; related groups use related hues; red/green are
  not the only distinction unless shape, line style, labels, or hatching also encode it.
- **Legend load**: legends are shared, direct, or moved out of data regions when possible.
- **Axes**: comparable panels use comparable limits; narrow-range data are not flattened
  by unnecessary 0-based axes unless that baseline is scientifically required.
- **Panel rhythm**: repeated panels align; asymmetric panels are intentionally dominant.
- **Export fidelity**: SVG/PDF text remains editable; raster preview is not blurry.

## Revision moves

When the figure looks disappointing, fix structure before decoration:

1. Reduce: remove redundant panels, repeated legends, excess tick labels, and decorative boxes.
2. Re-rank: enlarge the primary evidence panel and shrink secondary panels.
3. Re-space: increase gutters or margins where text touches axes, legends, or neighboring panels.
4. Re-map color: switch from many unrelated hues to one neutral family plus one signal family.
5. Re-label: use direct labels or one shared legend instead of repeated legends.
6. Re-scale: tighten y-limits for narrow ranges or standardize axes for direct comparisons.
7. Re-balance canvas: if equal-aspect panels create too much blank space, change figure
   size or GridSpec before accepting the layout.
8. Re-render: export a new preview and inspect again.

Iterate at least once after a failed visual audit. For high-stakes final figures, iterate
until there are no obvious overlaps, crowding, tiny labels, orphan legends, or ambiguous
color mappings.

## User-facing delivery

When delivering the figure, briefly report:

- what visual direction was used;
- what export files were produced;
- what was checked in the visual audit;
- any remaining limitation that affects appearance or interpretation.

Keep this concise. Do not expose private local paths, internal asset names, or private
reference provenance unless the user explicitly asks.
