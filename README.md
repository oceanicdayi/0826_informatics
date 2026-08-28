# SSIF Manuscript Sections

This repository contains the section drafts of the SSIF (Second-by-second
Seismic Intensity Forecaster) manuscript as individual Markdown files. The
files are numbered to reflect the paper's logical reading order:

**abstract → introduction → method → data → results → discussion → conclusions**

| # | File | Section |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | Abstract |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | Introduction — motivation and limitations of source-parameter-based EEW |
| 03 | [03_submit_Observation_Driven_Intensity_Forecasting.md](03_submit_Observation_Driven_Intensity_Forecasting.md) | Introduction — observation-driven approach and study objectives |
| 04 | [04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md) | Method — model architecture and input representation |
| 05 | [05_submit_Multitask_Optimization_and_Evaluation_Framework.md](05_submit_Multitask_Optimization_and_Evaluation_Framework.md) | Method — multitask optimization and evaluation framework |
| 06 | [06_submit_Intensity_Observation_and_Alert_Formulation.md](06_submit_Intensity_Observation_and_Alert_Formulation.md) | Data — intensity observations and alert-task formulation |
| 07 | [07_submit_Data_Partitioning_and_Model_Selection_Protocol.md](07_submit_Data_Partitioning_and_Model_Selection_Protocol.md) | Data — partitioning and model selection protocol |
| 08 | [08_submit_Prediction_Performance_and_Generalization.md](08_submit_Prediction_Performance_and_Generalization.md) | Results — overall prediction performance and generalization |
| 09 | [09_submit_Station_Level_Alert_and_Class_Prediction.md](09_submit_Station_Level_Alert_and_Class_Prediction.md) | Results — station-level alert and class prediction |
| 10 | [10_submit_Region_Based_Detection_and_Complementarity.md](10_submit_Region_Based_Detection_and_Complementarity.md) | Results — region-based event detection and eBEAR complementarity |
| 11 | [11_submit_Complementary_Failure_Modes_and_Generalization.md](11_submit_Complementary_Failure_Modes_and_Generalization.md) | Results — complementary failure modes and generalization |
| 12 | [12_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md](12_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md) | Discussion — speed–reliability tradeoff and operational window selection |
| 13 | [13_submit_Operational_Integration_and_Tradeoff.md](13_submit_Operational_Integration_and_Tradeoff.md) | Conclusions — operational integration and the anticipatory–confirmatory tradeoff |

## Figures

Submission-ready figures live in [`figures/`](figures/):

- [`SSIF_Architecture.pdf`](figures/SSIF_Architecture.pdf) — vector figure, for LaTeX/print submission
- [`SSIF_Architecture.png`](figures/SSIF_Architecture.png) — high-resolution raster (~350 dpi), for Word-based submission systems
- [`SSIF_Architecture_caption.txt`](figures/SSIF_Architecture_caption.txt) — suggested figure caption
- [`SSIF_Architecture_source.html`](figures/SSIF_Architecture_source.html) — editable source (open in a browser, or re-render with headless Chromium)

The figure illustrates the model architecture described in
[04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md):
input representation, convolutional stem, positional embedding, the masked
Transformer encoder, masked mean-pooling, and the two multitask output heads.

> 中文版: [README.zh-TW.md](README.zh-TW.md)
