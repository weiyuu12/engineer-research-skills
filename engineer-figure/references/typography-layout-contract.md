# Typography and Layout Contract

Use this reference before rendering any Chinese figure, manuscript/report figure, or
revision requested because fonts were too small, inconsistent, clipped, or surrounded
by awkward blank space.

## Principle

Readability wins over tiny journal-native defaults. Do not start Chinese manuscript
figures at `6-8 pt` unless the user explicitly requests exact final journal assembly
at a specified physical width and the preview remains readable.

For Chinese Word/PDF manuscript insertion, start from a readable working figure and
keep the size system deliberately small. A single figure should usually use **three
font sizes**, and complex multi-panel figures should use **no more than four**.

Default Chinese manuscript ladder:

| Tier | Size | Use |
|---|---:|---|
| S0 optional small | 11 | tick labels, dense in-panel annotation boxes |
| S1 regular | 13 | legend text, ordinary labels, figure body text |
| S2 emphasis | 15 | axis labels, panel letters, important callouts |
| S3 title | 17 | subplot titles, strip labels, group titles |

For simple figures, prefer only `13 / 15 / 17`. Add `11` only when ticks or dense
annotation boxes truly need a smaller size. Do not invent many intermediate values
such as `10.2`, `11.5`, `12.5`, `14.5`, `16`, and `18` in the same figure; round to
the closest tier instead.

For very dense pages with 12 or more panels, reduce the whole ladder by at most 1
point first, for example `10 / 12 / 14 / 16`. Do not drop below tick or annotation
`10`, axis label `14`, or title `16` without telling the user why.

## Font consistency

Lock one primary Chinese sans-serif font per project and reuse it across all figures.
Use this priority order unless the user provides a journal or lab font rule:

1. `Microsoft YaHei`
2. `Noto Sans CJK SC`
3. `Source Han Sans SC`
4. `SimHei`
5. `Microsoft YaHei UI`
6. `SimSun` only as a last resort for Chinese coverage
7. `DejaVu Sans` only when no CJK font exists

Rules:

- Use one primary CJK font for Chinese, English, numbers, and symbols whenever possible.
- Keep weights consistent: group titles and subplot titles may be bold; axis labels,
  tick labels, legends, and annotation boxes should usually be regular.
- Do not mix Songti, Heiti, DengXian, YaHei, and Arial randomly in one figure set.
- Always set `axes.unicode_minus = False` in matplotlib so minus signs display correctly.
- Verify that Chinese text is not rendered as boxes, missing glyphs, or clipped strokes.

## Python scaffold

Use this pattern instead of letting matplotlib choose fonts automatically:

```python
import matplotlib as mpl
import matplotlib.font_manager as fm

def choose_cjk_font():
    preferred = [
        "Microsoft YaHei",
        "Noto Sans CJK SC",
        "Source Han Sans SC",
        "SimHei",
        "Microsoft YaHei UI",
        "SimSun",
        "Arial Unicode MS",
        "DejaVu Sans",
    ]
    available = {font.name for font in fm.fontManager.ttflist}
    for name in preferred:
        if name in available:
            return name
    return "DejaVu Sans"

def configure_readable_chinese_matplotlib(base=13):
    font_name = choose_cjk_font()
    mpl.rcParams.update({
        "font.family": "sans-serif",
        "font.sans-serif": [font_name, "DejaVu Sans", "Arial"],
        "axes.unicode_minus": False,
        "svg.fonttype": "none",
        "pdf.fonttype": 42,
        "font.size": base,
        "axes.labelsize": base + 2,
        "axes.titlesize": base + 4,
        "xtick.labelsize": base - 2,
        "ytick.labelsize": base - 2,
        "legend.fontsize": base,
        "axes.linewidth": 0.95,
        "axes.spines.top": False,
        "axes.spines.right": False,
        "legend.frameon": False,
    })
    return font_name
```

## R scaffold

For Chinese ggplot figures, use one base family and scale sizes from it:

```r
theme_chinese_manuscript <- function(base_size = 13,
                                     base_family = "Microsoft YaHei") {
  ggplot2::theme_classic(base_size = base_size, base_family = base_family) +
    ggplot2::theme(
      axis.line = ggplot2::element_line(linewidth = 0.45, colour = "black"),
      axis.ticks = ggplot2::element_line(linewidth = 0.45, colour = "black"),
      axis.title = ggplot2::element_text(size = base_size + 2),
      axis.text = ggplot2::element_text(size = base_size - 2),
      legend.title = ggplot2::element_text(size = base_size),
      legend.text = ggplot2::element_text(size = base_size),
      strip.text = ggplot2::element_text(size = base_size + 4, face = "bold"),
      plot.title = ggplot2::element_text(size = base_size + 4, face = "bold"),
      plot.subtitle = ggplot2::element_text(size = base_size),
      panel.grid = ggplot2::element_blank()
    )
}
```

If R cannot find the Chinese font, report the font blocker or use the best available
CJK family. Do not silently switch each plot to a different font.

## Canvas and whitespace defaults

Set figure size and margins from the amount of text and the number of panels, not from
the data alone.

For Chinese multi-panel figures:

- 1 panel: usually `(7-9, 4.8-6.2)` inches.
- 2-4 panels: usually `(10-13, 5.8-7.5)` inches.
- 3 x 3 panels: usually `(11.5-13.5, 7.2-8.4)` inches.
- 3 x 6 panels: usually `(16-18, 9-10.5)` inches.

Reserve space deliberately:

- left margin: `0.065-0.10`, larger when a vertical y-axis label exists;
- right margin: `0.965-0.99`, unless a right legend/colorbar exists;
- bottom margin: `0.12-0.18` when x-label and legend sit below panels;
- top margin: `0.88-0.93` when group titles or suptitles exist;
- `wspace`: start around `0.10-0.22`; reduce if columns look disconnected;
- `hspace`: start around `0.30-0.55`; increase only when titles or tick labels collide.

For equal-aspect axes, watch for excessive blank columns. If large white gaps appear,
reduce canvas width, use `GridSpec` width ratios, move labels into shared outer labels,
or loosen the fixed aspect only if it does not distort the science.

## Layout rules

- Do not rely on `tight_layout()` or `bbox_inches="tight"` to solve layout. They can
  crop exports but cannot fix bad hierarchy, large blanks, or text collisions.
- Prefer manual `fig.subplots_adjust(...)` or `GridSpec` when figures contain Chinese
  titles, bottom legends, shared labels, or equal-aspect panels.
- Put legends outside data regions and reserve physical space for them.
- Keep global titles away from subplot titles. If a global title collides, move it
  higher, reduce its size, or convert it into a left-aligned figure label.
- Use shared outer x/y labels for dense grids instead of repeating axis labels.
- Avoid giant empty corridors between columns. If panels feel disconnected, reduce
  width or `wspace` before increasing font size again.

## Required preview audit

After rendering, inspect PNG or TIFF at normal screen size and at the approximate size
it will appear in the manuscript. Check:

- Chinese characters render in the intended font and are not boxes or fallback glyphs.
- No text is clipped on the top, bottom, left, or right.
- Tick labels, axis labels, legend text, and annotation boxes are readable without zooming.
- The figure uses no more than four font sizes; simple figures use no more than three.
- Top titles do not overlap subplot titles.
- Legend does not steal data space or float too far from the figure.
- Outer margins feel balanced; blank space supports the figure rather than dominating it.
- Font family and weight match the previous figures in the same manuscript.

If any check fails, revise and render again before delivery.
