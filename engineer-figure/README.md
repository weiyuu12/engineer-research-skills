# engineer-figure skill

Submission-grade engineering and scientific figure workflow for Nature-tier, IEEE,
Elsevier, Springer, and other high-impact academic venues. The skill supports Python
and R, but always requires one selected backend before plotting.

The current design is claim-first: define the figure's conclusion, evidence logic,
visual concept, typography/layout contract, export requirements, and review risks
before writing plotting code.

## Current reference priority

For engineering, deep learning, modeling, simulation, control, robotics, neural-operator,
digital-twin, inverse-design, and interception-style figures, use:

1. `references/figure-concept-card.md` for the claim and reviewer question.
2. `references/visual-innovation-atlas.md` for non-traditional visual structures.
3. `references/engineering-reference-atlas.md` for top-journal engineering/AI/control
   figure references.
4. `references/typography-layout-contract.md` for font, margin, whitespace, and
   anti-overlap rules.
5. `references/visual-quality-loop.md` for first-render inspection and revision.

The older `assets/gallery/` and `assets/figures4papers/` materials are still useful,
but they are no longer the first visual inspiration source for engineering-domain tasks.
Use them mainly for reusable plotting mechanics.

## Bundled assets

```text
assets/
  engineering-reference-atlas/   engineering/AI/control paper figure references
  chart-atlas/                   chart-family preview panels
  figures4papers/                reusable Python demo scripts and previews
  gallery/                       older simulated output previews
references/
  engineering-reference-atlas.md engineering reference routing and source index
  visual-innovation-atlas.md     mechanism/process/evidence visual structures
  typography-layout-contract.md  readable Chinese fonts, size ladders, whitespace
  visual-quality-loop.md         preview audit and revision loop
  api.md                         Python palette, helper signatures, export conventions
  r-workflow.md                  R plotting and export conventions
```

## Operating rules

- Ask `Python or R?` when the backend is not already specified.
- Use the selected backend exclusively for drawing, previewing, exporting, and QA.
- Do not default to bars, lines, or plain heatmaps when the figure's real job is
  mechanism, process, decision logic, system interaction, simulation evidence, or
  control feedback.
- Prefer one dominant hero panel plus smaller evidence panels.
- For Chinese manuscript/report figures, start from the readable Chinese font ladder
  in `typography-layout-contract.md`, with no more than three or four font sizes.
- Export manuscript figures as editable SVG/PDF plus high-resolution TIFF/PNG when needed.
- Inspect the rendered preview before final delivery; syntax success is not visual success.

## Validation

Run the system skill validator after structural edits:

```bash
python <skill-creator>/scripts/quick_validate.py <engineer-figure>
```

The validator requires `PyYAML` in the Python environment used to run it.

## Open-source release note

Before publishing this skill, audit all bundled third-party images and demo assets.
If redistribution rights are uncertain, publish only the metadata, article URLs, image
URLs, and usage notes rather than the source image files themselves.
