# SSIF Manuscript Sections

This repository contains the section drafts of the SSIF (Second-by-second
Seismic Intensity Forecaster) manuscript as individual Markdown files. The
files are numbered to reflect the paper's logical reading order:

**abstract → introduction → method → model architecture → data → results → case study → discussion → conclusions**

| # | File | Section |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | Abstract |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | Introduction — motivation, limitations of source-parameter-based EEW, observation-driven approach, and study objectives |
| 03 | [03_submit_Method.md](03_submit_Method.md) | Method — modeling approach and study objectives |
| 04 | [04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md) | Model Architecture and Input Representation — backbone architecture, multitask optimization, and evaluation framework |
| 05 | [05_submit_Data.md](05_submit_Data.md) | Data — intensity observations and alert-task formulation, data partitioning and model selection protocol |
| 06 | [06_submit_Results.md](06_submit_Results.md) | Results — overview, station-level alert and class prediction, persistence baseline and anticipatory detection, region-based detection and eBEAR complementarity, generalization |
| 07 | [07_submit_case_study_hualien_m72.md](07_submit_case_study_hualien_m72.md) | Case Study — 2024 M7.2 Hualien earthquake, SSIF vs. eBEAR |
| 08 | [08_submit_Discussion.md](08_submit_Discussion.md) | Discussion — speed–reliability tradeoff and operational window selection |
| 09 | [09_submit_Conclusions.md](09_submit_Conclusions.md) | Conclusions — operational integration and the anticipatory–confirmatory tradeoff |

This is a 9-file layout: Model Architecture and Input Representation (04)
and the Hualien M7.2 Case Study (07) are broken out as their own chapters
— previously they were subsections of Method and Results, respectively.
Every other chapter is unchanged from the prior 7-file layout. Two small
bridging adjustments were made where the split otherwise would have left
a forward reference: Method's training/evaluation content (which
discusses the pooled representation vector) moved into the Model
Architecture chapter so it no longer refers ahead to a concept not yet
introduced, and Results ends with a one-sentence pointer to the Case
Study chapter that follows it. Abstract (01) and Introduction (02) are
untouched throughout.

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
[04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md):
input representation, convolutional stem, positional embedding, the masked
Transformer encoder, masked mean-pooling, and the two multitask output heads.

> 中文版: [README.zh-TW.md](README.zh-TW.md)
