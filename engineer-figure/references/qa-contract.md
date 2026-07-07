# QA Contract

Use this before final delivery, before a revision package, and whenever the figure
contains raster/simulation image panels, experimental photos, subgroup analysis, or statistical claims.
Journal rules change, so verify the latest target journal author guide for final
submission. The values below are conservative defaults for Nature-family style work.

## Current official references to verify

- Nature research figure guide: `https://research-figure-guide.nature.com/`
- Nature building/exporting panels: `https://research-figure-guide.nature.com/figures/building-and-exporting-figure-panels/`
- Nature preparing figures/specifications: `https://research-figure-guide.nature.com/figures/preparing-figures-our-specifications/`
- Nature initial submission and statistics guidance: `https://www.nature.com/nature/for-authors/initial-submission`
- Nature formatting guide: `https://www.nature.com/nature/for-authors/formatting-guide`
- Target journal image-integrity and figure-preparation guidance, if the venue has stricter requirements than the general Nature defaults.

## Pre-submission checklist

| Check | Pass condition |
|---|---|
| Core conclusion | One-sentence claim exists and every panel maps to it |
| Concept card | Reviewer question, visual job, evidence roles, and rejected default chart are documented for manuscript-facing figures |
| Archetype | Figure has a declared archetype and panel hierarchy |
| Innovation route | Bars/lines/plain heatmaps are used as hero panels only when metric comparison is truly the visual job; otherwise mechanism/process/decision evidence is represented structurally |
| Visual audit | Preview was inspected at final aspect ratio; hierarchy, spacing, labels, legends, colors, whitespace, and overlaps pass `visual-quality-loop.md` |
| Backend exclusivity | The selected backend produced all plotting, previews, exports, and visual QA renders |
| Final size | Single-column about 89 mm or double-column about 183 mm, height not above target journal limit |
| Text size | Text follows target context: Chinese manuscript/report figures usually start at base 12-14 with axis labels 15-16; exact English journal-final dense panels may use 5-8 pt only after readability QA |
| Font-size economy | Simple figures use at most three font sizes; dense multi-panel figures use at most four |
| Panel labels | Bold and near top-left; exact English final-size panels may use about 8 pt, while Chinese/report figures usually need 13-15 |
| Editable text | SVG/PDF text remains editable; no outlined text unless unavoidable for special symbols |
| Font | One primary font family is locked across the figure set; Chinese glyphs render correctly and do not silently mix Songti/Heiti/DengXian/YaHei |
| Color | No rainbow color maps; red/green is not the only encoding; grayscale print remains interpretable |
| Legend strategy | Shared or direct labels where possible; no repeated redundant legends |
| Statistics | `n`, experimental/simulation repeat definition, center, spread, test, correction, and exact comparison are documented |
| Source data | Quantitative panels can be traced to a clean CSV/TSV/XLSX or script output |
| Raster resolution | Photos, simulation snapshots, and field images are high-resolution enough for final size; line art uses vector where possible |
| Image scale | Scale bar or physical units are present when the image represents a spatial object, field, or device |
| Image integrity | Crop, contrast, pseudo-color, stitching, reuse, and raw-file provenance are recorded |
| Export bundle | Script, source data, SVG, PDF, TIFF/PNG preview, and QA notes are delivered together when requested |

## Statistics legend minimum

For each quantitative panel, capture:

```text
n definition:
experimental repeats:
simulation seeds or runs:
center statistic:
spread/interval:
test:
multiple-comparison correction:
p-value display:
source-data file:
```

For machine-learning/model figures, also capture:

```text
train/validation/test split:
number of seeds or folds:
metric definition:
confidence interval or variability definition:
baseline definition:
```

## Image-integrity minimum

For each image panel, capture:

```text
raw file:
processed file:
crop:
brightness/contrast/gamma:
pseudo-color:
scale calibration:
stitching:
reuse in other figures:
quantification link:
```

Global adjustments are generally safer than local selective edits. If an adjustment
changes the visibility of relevant background or bands, flag it instead of silently
normalizing it away.

## Export checks

Run only the export block for the selected backend. If that backend is unavailable,
stop and report the missing runtime/package instead of producing a substitute export
with the other language.

### Python

```python
import matplotlib as mpl
mpl.rcParams["svg.fonttype"] = "none"
mpl.rcParams["pdf.fonttype"] = 42
fig.savefig("figure.svg", bbox_inches="tight")
fig.savefig("figure.pdf", bbox_inches="tight")
fig.savefig("figure.tiff", dpi=600, bbox_inches="tight")
```

### R

```r
svglite::svglite("figure.svg", width = width_mm / 25.4, height = height_mm / 25.4)
print(plot)
dev.off()

grDevices::cairo_pdf("figure.pdf", width = width_mm / 25.4, height = height_mm / 25.4, family = "Arial")
print(plot)
dev.off()

ragg::agg_tiff("figure.tiff", width = width_mm / 25.4, height = height_mm / 25.4, units = "in", res = 600)
print(plot)
dev.off()
```

Open the SVG/PDF after export and verify that text can be selected, labels do not
overlap, and the figure still reads at final printed size.
