# Visual Innovation Atlas

Use this when a figure risks becoming another bar chart, line chart, or plain heatmap.
Choose the visual structure from the scientific job the figure must perform.

## First rule

Do not ask "which chart type fits this column?". Ask "what should the reviewer understand
after five seconds?". Then choose a structure that makes that understanding visible.

For engineering, deep learning, modeling, simulation, control, robotics, digital-twin,
neural-operator, inverse-design, or interception-style requests, open
`engineering-reference-atlas.md` before choosing a chart family. Use those examples as
the default reference set; use older bio/chemistry-style galleries only when the user's
domain actually needs them.

## Visual-job routing

| Visual job | Prefer these structures | Avoid defaulting to |
|---|---|---|
| Explain a mechanism | Hero schematic + callouts + small validation panels; causal chain; layered module diagram | A standalone bar chart of final metrics |
| Show a process | Phase strip, timeline lanes, before/during/after panels, state-transition diagram, process ribbon | A single line chart with many labels |
| Reveal decision logic | Decision landscape, feasibility/risk window map, threshold contour, quadrant map, rule-path diagram | Tables or grouped bars of thresholds |
| Show multi-agent/system interaction | Network map, bipartite matching diagram, lane timeline, matrix with glyphs, alluvial/Sankey flow | Separate per-agent bar charts |
| Show spatial/trajectory evidence | Trajectory bundles, density contours, vector fields, phase portraits, annotated snapshots | Mean endpoint bars |
| Show uncertainty/robustness | Envelope bands, sensitivity carpet, interval/ridge plot, scenario small multiples, uncertainty tiles | Error bars alone |
| Show composition or transition | Alluvial flow, stacked area with direct labels, mosaic/Marimekko, transition matrix | Pie charts or repeated stacked bars |
| Show hierarchy or decomposition | Nested blocks, icicle/sunburst-like hierarchy, error-budget waterfall, contribution tree | Flat bar chart of components |
| Compare methods fairly | Ordered dot/interval plot, slopegraph, dominance matrix, paired-difference plot, compact benchmark grid | Wide grouped bars unless categories are few |
| Summarize a pipeline | Input-process-output schematic + evidence thumbnails + quantitative footer | A flowchart with no evidence |

## Domain-neutral idea bank

Use these beyond biology/chemistry. Adapt labels to the user's field.

- **Engineering / algorithms**: decision landscape, feasible-window map, state machine,
  error-budget waterfall, pipeline with validation insets, latency/accuracy tradeoff
  frontier, scenario tiles. Cross-check `engineering-reference-atlas.md` for architecture,
  simulation, control-loop, inverse-design, and validation structures.
- **Control / robotics / interception**: trajectory bundle, risk envelope, candidate
  pruning funnel, agent-task matching matrix, phase timeline, miss-distance density
  map, threshold contour.
- **Machine learning**: embedding map with arrows, benchmark dominance matrix,
  ablation mechanism diagram, calibration/reliability panel, data-flow architecture,
  uncertainty band over training or deployment phases.
- **Operations / management**: bottleneck flow, resource allocation matrix, alluvial
  transition, queue timeline, decision tree with outcome insets.
- **Physical process**: layered process schematic, parameter-space phase map,
  before/after morphology plus quantification, sensitivity surface.

## Conservative-to-creative ladder

When uncertain, move one step at a time:

1. Replace grouped bars with dot/interval plots or paired-difference plots.
2. Add direct labels and a reference threshold so the key claim is visible.
3. Add a process or mechanism inset explaining why the pattern occurs.
4. Promote that mechanism/process view into the hero panel.
5. Move metrics into smaller validation panels or a compact evidence row.

This gives novelty through argument structure, not decoration.

## Rejection checklist

Before choosing a basic bar/line/heatmap as the main panel, answer:

- Is the figure's main job truly metric comparison?
- Would a reviewer understand the mechanism or process from this panel alone?
- Would a decision map, process strip, trajectory view, or uncertainty panel reveal
  something the metric chart hides?
- Can the quantitative metric become a smaller validation panel instead of the hero?

If two or more answers suggest hidden structure, use a mechanism/process-led composite.

## Panel recipes

### Mechanism-led composite

Use when the paper needs the reviewer to understand how the method or phenomenon works.

```text
a: hero mechanism / algorithm / physical process schematic
b: key intermediate evidence or process state
c: quantitative validation of the final claim
d: robustness or failure-mode/control panel
```

### Process-evidence strip

Use when the evidence changes across stages.

```text
a: stage strip with 3-5 phases
b-d: aligned small panels below selected phases
e: compact summary metric or uncertainty interval
```

### Decision landscape

Use when thresholds, risk windows, feasibility, or tradeoffs drive the conclusion.

```text
a: 2D contour/region map with feasible and infeasible zones
b: representative trajectories or examples placed on the map
c: small validation metric comparing chosen vs rejected regions
d: sensitivity or robustness strip
```

### Multi-agent/system map

Use when the figure involves assignment, coordination, information flow, or interaction.

```text
a: network or matching map showing who interacts with what
b: timeline/lane view showing order or synchronization
c: matrix or heatmap showing strength/feasibility of interactions
d: outcome validation panel
```

### Engineering method overview

Use when a method combines model architecture, physics/simulation, optimization, and
validation.

```text
a: hero architecture / closed-loop / physical-process schematic
b: representative simulation, field, trajectory, or state evidence
c: validation against baseline, experiment, or high-fidelity simulation
d: robustness, sensitivity, failure mode, or deployment constraint
```

Prefer this over a large metric grid when the reviewer must understand how the method
works, not only that it scores better.

## Guardrails

- Keep the hero panel legible; do not overload it with every metric.
- Use one visual grammar per figure. A composite can mix modalities, but the reader
  should feel one story, not a collage.
- Use quantitative panels to support the mechanism/process, not to drown it.
- Prefer direct labels and callouts over a large legend when the visual structure is new.
- If a creative structure would require fake data, unsupported geometry, or misleading
  interpolation, choose a simpler defensible structure.
