# Private R Template Adaptation

Use this reference when the user chooses R and provides or mentions an existing
R plotting template collection. Treat such material as private working context.
Do not reveal absolute paths, folder names, filenames, screenshots, provenance, or
any identifying labels from the source collection in user-facing output.

## Privacy rules

- Never include absolute local paths in generated code, reports, comments, or final replies.
- Never mention the original source file, folder, template number, course title, download
  location, chat attachment, or private document name.
- When a template is useful, describe it generically by chart family: "a grouped bar
  template", "a ComplexHeatmap workflow", "a forest/interval plotting workflow".
- If a reusable idea is copied from a private template, rewrite the final code as a clean,
  self-contained script with neutral function names and neutral comments.
- If the user asks where a style came from, say it was adapted from the provided working
  materials without identifying the path or source file.

## Generic search strategy

Search private materials by chart family and package names, not by exposing paths:

```bash
find <private-template-root> -type f \( -name '*.R' -o -name '*.Rmd' -o -name '*.r' \)
rg -n "ggplot|patchwork|ComplexHeatmap|ggrepel|svglite|cairo_pdf|forestplot|circlize" <private-template-root>
```

Keep these commands in internal working notes only. Do not paste the user's private
root path into the final answer.

## Chart-family map

Use these generic families to decide what to inspect:

| Need | Search targets |
|---|---|
| Bars and grouped comparisons | `geom_col`, `geom_bar`, `position_dodge`, `stat_compare_means` |
| Error bars and point-interval plots | `geom_errorbar`, `geom_pointrange`, `mean_se`, `stat_summary` |
| Stacked or bidirectional bars | `position_stack`, `coord_flip`, signed values, paired positive/negative bars |
| Box, violin, paired, and raincloud-style distributions | `geom_boxplot`, `geom_violin`, `geom_jitter`, paired sample identifiers |
| Heatmaps and annotated heatmaps | `ComplexHeatmap`, `HeatmapAnnotation`, `pheatmap`, `geom_tile` |
| Correlation, scatter, bubble, and volcano plots | `geom_point`, `geom_smooth`, `ggrepel`, `logFC`, `pvalue`, bubble size scales |
| PCA, PCoA, NMDS, tSNE, UMAP | `prcomp`, `cmdscale`, `vegan`, `Rtsne`, embedding coordinates |
| Subgroup, ROC, forest, and interval plots | `forestplot`, `timeROC`, confidence intervals, grouped estimates |
| Circular engineering summaries | `circlize`, angular coordinates, cyclic process summaries |
| Maps and spatial summaries | `sf`, `maps`, spatial coordinates |
| Radar, lollipop, dumbbell, UpSet, Venn, Sankey | `ggradar`, `geom_segment`, `UpSetR`, `ggalluvial`, set operations |

## Adaptation checklist

When adapting a private template:

- Keep useful data wrangling, statistics, and geoms.
- Replace template-specific colors with the figure-level semantic palette.
- Normalize fonts to final-size 5-7 pt text and 8 pt bold lowercase panel labels.
- Convert single-output PNG/PDF scripts to SVG/PDF/TIFF export.
- Remove decorative elements that do not support the core conclusion.
- Ensure each statistical comparison has `n`, center, spread, test, and correction
  information in the legend or source-data notes.
- For image panels, document raw file, crop, contrast, scale-bar or physical-unit
  calibration, and any stitching or pseudo-coloring in private QA notes.
- Final code should be self-contained and should not require the original private
  folder structure unless the user explicitly asks to keep that workflow.
