# SSIF_Architecture.pdf — Submission Architecture Figure

**Type:** Vertical block-flow diagram, monochrome + two-accent
(blue/maroon) print-safe design, purpose-built for manuscript submission
(see `SSIF_Architecture_source.html`, rendered to PNG at ~350 dpi and to
vector PDF).

## What it shows

Input (2-channel 1 Hz sequence + validity mask, bar-chart glyph
distinguishing valid vs. masked steps) → Conv Stem ×3 (2→96→192→192) →
`+` learnable positional embedding → Transformer ×4 (pre-norm,
Multi-Head Self-Attention with masking, Feed-Forward, residual arcs,
masked-attention glyph) → Masked Mean-Pool (`[B,192]`) → two output heads
(Class Head: `Linear→Softmax(10)`, CWA intensity 0,1,2,3,4,5−,5+,6−,6+,7;
Alert Head: `Linear→Sigmoid(1)`, I≥4, rendered with a diagonal hatch fill
so the two heads stay distinguishable in grayscale print).

It does **not** show the joint-loss breakdown (cross-entropy / alert BCE /
ordinal regression / consistency) — see
[`fig_ssif_architecture.md`](fig_ssif_architecture.md) for the sibling
figure that does.

## Cross-reference

Built directly from the "Model Architecture and Input Representation"
subsection of
[`03_submit_Method.md`](../03_submit_Method.md).
Suggested caption text is in
[`SSIF_Architecture_caption.txt`](SSIF_Architecture_caption.txt).

## Files

| File | Purpose |
|---|---|
| `SSIF_Architecture.pdf` | vector, for LaTeX/print |
| `SSIF_Architecture_source.html` | editable source (open in browser or re-render with headless Chromium) — re-render this to regenerate a PNG if one is needed again |
| `SSIF_Architecture_caption.txt` | suggested figure caption |

> The high-res PNG export (`SSIF_Architecture.png`) has been removed
> from this directory; the PDF and HTML source remain.

## Suggested manuscript placement

Method section (03_), as the primary architecture figure — this is the
submission-ready version; prefer it over `fig_ssif_architecture.png`
unless the loss-weight breakdown needs to be shown visually rather than
in prose.

> 中文版: [SSIF_Architecture.zh-TW.md](SSIF_Architecture.zh-TW.md)
