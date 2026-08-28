# fig_ssif_architecture.png — SSIF Model Architecture (reference diagram)

**Type:** Top-to-bottom colored block-flow diagram (auto-generated style),
one color per stage: Input (blue) → Conv Stem (orange) → Positional
Encoding (purple) → Transformer Encoder (indigo) → Pooling (teal) →
Output Heads (red/green) → Joint Loss (grey).

## What it shows

1. **Input** `(B, T)`: two sub-boxes — scaled intensity `[0,1] = intensity/9`
   and validity mask `0/1, missing=0`.
2. **Conv Stem**: 3× Conv1d (kernel=3, padding=same), channel path
   2→96→192→192, each with GroupNorm(8); GELU + Dropout after each layer
   → `(B, T, 192)`.
3. **Positional Encoding**: learnable, `z = x + pos[:, :T, :]`, with mask
   zeroing.
4. **Transformer Encoder**: 4 pre-norm layers, each 4 heads, d=192,
   FFN mult=2, GELU, dropout=0.1; `src_key_padding_mask = ~valid_mask`
   excludes missing steps from attention.
5. **Pooling**: masked mean pooling + LayerNorm + Dropout,
   `pooled = Σ(x·mask)/Σ(mask) → (B, 192)`.
6. **Output Heads**: 10-class intensity head (`Linear(192→10)→Softmax`,
   predicts CWA class {0,...,7}) and binary alert head
   (`Linear(192→1)→Sigmoid`, predicts I≥4).
7. **Joint Loss** (four weighted terms, shown as a separate row not present
   in the other architecture figure):
   - Cross-Entropy, weight **0.45** — 10-class classification
   - Alert BCE, weight **0.35** — binary alert + pos_weight
   - Ordinal Regression, weight **0.15** — Smooth-L1 on expected class
   - Consistency, weight **0.05** — MSE(σ(alert), Σp[k≥4])

## Cross-reference

Matches
[`04_submit_Model_Architecture_and_Input_Representation.md`](../04_submit_Model_Architecture_and_Input_Representation.md)
for the backbone, and the loss weights match
[`05_submit_Multitask_Optimization_and_Evaluation_Framework.md`](../05_submit_Multitask_Optimization_and_Evaluation_Framework.md)
exactly (0.45 / 0.35 / 0.15 / 0.05).

## Relationship to `SSIF_Architecture.pdf`

> **Update:** `SSIF_Architecture.png` has been removed from this
> directory to resolve the duplication noted below. The comparison is
> kept for reference, against the remaining `SSIF_Architecture.pdf`
> (same content, vector format; re-render from
> `SSIF_Architecture_source.html` if a raster is needed again).

This directory also contains a second, independently drawn architecture
figure — [`SSIF_Architecture.pdf`](SSIF_Architecture.pdf) (see
[`SSIF_Architecture.md`](SSIF_Architecture.md)). The two are largely
redundant:

| | fig_ssif_architecture.png | SSIF_Architecture.pdf |
|---|---|---|
| Style | Colorful, per-stage color blocks | Monochrome, print/submission style, grayscale-safe |
| Loss terms shown | Yes (all 4, with weights) | No (stops at the two output heads) |
| Masked/valid legend | No | Yes |
| Print-readiness (B&W, hatch pattern) | No | Yes |

If only one architecture figure is kept in the final manuscript, consider
merging the Joint Loss row from this figure into `SSIF_Architecture.pdf`
(or citing loss weights in the caption/body text instead, as
`05_submit_Multitask_Optimization_and_Evaluation_Framework.md` already
does in prose).

## Suggested manuscript placement

Model Architecture and Input Representation (04_) or Multitask
Optimization and Evaluation Framework (05_), as Figure 1 or 2 —
whichever architecture figure is chosen as canonical.

> 中文版: [fig_ssif_architecture.zh-TW.md](fig_ssif_architecture.zh-TW.md)
