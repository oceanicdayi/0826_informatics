# SSIF Manuscript Sections

This repository contains the section drafts of the SSIF (Second-by-second
Seismic Intensity Forecaster) manuscript as individual Markdown files. The
files are numbered to reflect the paper's logical reading order:

**abstract → introduction → method → data → results → discussion → conclusions**

| # | File | Section |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | Abstract |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | Introduction — motivation, limitations of source-parameter-based EEW, observation-driven approach, and study objectives |
| 03 | [03_submit_Method.md](03_submit_Method.md) | Method — modeling approach and study objectives, model architecture and input representation, multitask optimization and evaluation framework |
| 04 | [04_submit_Data.md](04_submit_Data.md) | Data — intensity observations and alert-task formulation, data partitioning and model selection protocol |
| 05 | [05_submit_Results.md](05_submit_Results.md) | Results — overview, station-level alert and class prediction, persistence baseline and anticipatory detection, region-based detection and eBEAR complementarity, generalization, and the 2024 M7.2 Hualien case study |
| 06 | [06_submit_Discussion.md](06_submit_Discussion.md) | Discussion — speed–reliability tradeoff and operational window selection |
| 07 | [07_submit_Conclusions.md](07_submit_Conclusions.md) | Conclusions — operational integration and the anticipatory–confirmatory tradeoff |

Sections 03–07 were consolidated from a previous 14-file layout (one file
per subsection) into one file per top-level section, using `##`/`###`
subheadings to preserve the original subsection structure. Abstract (01)
and Introduction (02) were left untouched; the file that previously sat
between them and Method — "observation-driven approach and study
objectives" — is now the opening `##` subsection of 03_submit_Method.md,
since it frames SSIF's modeling approach rather than motivating the
problem the way 02_submit_Introduction.md does.

## Figures

All manuscript figures live in [`figures/`](figures/), each with a
companion analysis `.md` — see [`figures/README.md`](figures/README.md)
for the full index, including two data-consistency issues found during
review (an unreconciled n=44 vs. n=50 event cohort across two figures,
and a duplicate architecture figure).

The submission-ready architecture figure
([`SSIF_Architecture.pdf`](figures/SSIF_Architecture.pdf) — vector, the
PNG raster export was removed; re-render from
[`SSIF_Architecture_source.html`](figures/SSIF_Architecture_source.html)
if a PNG is needed again — caption in
[`SSIF_Architecture_caption.txt`](figures/SSIF_Architecture_caption.txt))
illustrates the model architecture described in
[03_submit_Method.md](03_submit_Method.md):
input representation, convolutional stem, positional embedding, the masked
Transformer encoder, masked mean-pooling, and the two multitask output heads.

> 中文版: [README.zh-TW.md](README.zh-TW.md)
