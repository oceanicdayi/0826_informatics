# SSIF Manuscript Sections

This repository contains the section drafts of the SSIF (Second-by-second
Seismic Intensity Forecaster) manuscript as individual Markdown files. The
files are numbered to reflect the paper's logical reading order:

**abstract → introduction → method → model architecture → multitask optimization & evaluation → data → results → case study → discussion → conclusions**

| # | File | Section |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | Abstract |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | Introduction — motivation, limitations of source-parameter-based EEW, observation-driven approach, and study objectives |
| 03 | [03_submit_Method.md](03_submit_Method.md) | Method — modeling approach and study objectives |
| 04 | [04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md) | Model Architecture and Input Representation |
| 05 | [05_submit_Multitask_Optimization_and_Evaluation_Framework.md](05_submit_Multitask_Optimization_and_Evaluation_Framework.md) | Multitask Optimization and Evaluation Framework |
| 06 | [06_submit_Data.md](06_submit_Data.md) | Data — intensity observations and alert-task formulation, data partitioning and model selection protocol |
| 07 | [07_submit_Results.md](07_submit_Results.md) | Results — overview, station-level alert and class prediction, persistence baseline and anticipatory detection, region-based detection and eBEAR complementarity, generalization |
| 08 | [08_submit_case_study_hualien_m72.md](08_submit_case_study_hualien_m72.md) | Case Study — 2024 M7.2 Hualien earthquake, SSIF vs. eBEAR |
| 09 | [09_submit_Discussion.md](09_submit_Discussion.md) | Discussion — speed–reliability tradeoff and operational window selection |
| 10 | [10_submit_Conclusions.md](10_submit_Conclusions.md) | Conclusions — operational integration and the anticipatory–confirmatory tradeoff |

This is a 10-file layout. Model Architecture and Input Representation
(04), Multitask Optimization and Evaluation Framework (05), and the
Hualien M7.2 Case Study (08) are each broken out as their own chapters —
all three were originally subsections of Method or Results. Every other
chapter is unchanged. The chapters now read in dependency order —
Method (why) → Model Architecture (what) → Multitask Optimization and
Evaluation Framework (how it's trained and measured) → Data → Results →
Case Study — so no chapter refers ahead to a concept its reader hasn't
reached yet; Results ends with a one-sentence pointer to the Case Study
chapter that follows it. Abstract (01) and Introduction (02) are
untouched throughout.

## Consistency Review

[`CONSISTENCY_REVIEW.md`](CONSISTENCY_REVIEW.md) cross-checks all 10
submission files against each other for numbers and claims that don't
agree, plus unclear or undefined wording — including a precision figure
in the abstract that contradicts the Results chapter, an arithmetic
error in the Data chapter's validation-split subdivision, and a stale
cross-reference left over from the most recent chapter split. Ends with
a prioritized next-steps list.

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
