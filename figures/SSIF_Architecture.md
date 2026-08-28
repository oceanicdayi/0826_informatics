# SSIF_Architecture.png / .pdf — Submission Architecture Figure

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

Built directly from
[`04_submit_Model_Architecture_and_Input_Representation.md`](../04_submit_Model_Architecture_and_Input_Representation.md).
Suggested caption text is in
[`SSIF_Architecture_caption.txt`](SSIF_Architecture_caption.txt).

## Files

| File | Purpose |
|---|---|
| `SSIF_Architecture.png` | high-res raster (~350 dpi) |
| `SSIF_Architecture.pdf` | vector, for LaTeX/print |
| `SSIF_Architecture_source.html` | editable source (open in browser or re-render with headless Chromium) |
| `SSIF_Architecture_caption.txt` | suggested figure caption |

## Suggested manuscript placement

Method section (04_), as the primary architecture figure — this is the
submission-ready version; prefer it over `fig_ssif_architecture.png`
unless the loss-weight breakdown needs to be shown visually rather than
in prose.
