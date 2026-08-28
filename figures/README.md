# Figures — Index and Analysis

Every image in this directory has a companion `.md` file (same basename)
with a close reading of what it shows, which manuscript section it
supports, and any issues found while reviewing it.

| Image | Analysis | Summary |
|---|---|---|
| [`SSIF_Architecture.png`](SSIF_Architecture.png) | [`SSIF_Architecture.md`](SSIF_Architecture.md) | Submission-ready model architecture figure (print-safe, monochrome) |
| [`fig_ssif_architecture.png`](fig_ssif_architecture.png) | [`fig_ssif_architecture.md`](fig_ssif_architecture.md) | Alternate, colorful architecture figure — also shows the 4-term joint loss |
| [`fig_station_event_map.png`](fig_station_event_map.png) | [`fig_station_event_map.md`](fig_station_event_map.md) | Taiwan map: 642 stations + 670/147/147 train/val/test events |
| [`fig_region_contingency.png`](fig_region_contingency.png) | [`fig_region_contingency.md`](fig_region_contingency.md) | Region-based TP/FP/FN/TN by window, 50 matched events — matches manuscript exactly |
| [`fig_detection_categories.png`](fig_detection_categories.png) | [`fig_detection_categories.md`](fig_detection_categories.md) | SSIF/eBEAR both-detect / only / both-miss by window — **n=44, doesn't match the 50/39 cohort used elsewhere** |
| [`fig_alert_timeline.png`](fig_alert_timeline.png) | [`fig_alert_timeline.md`](fig_alert_timeline.md) | eBEAR delay vs. SSIF earliest window, per event, n=44 — same open cohort question, plus an unlabeled bar-shading distinction |
| [`fig_case_study_hualien_m72.png`](fig_case_study_hualien_m72.png) | [`fig_case_study_hualien_m72.md`](fig_case_study_hualien_m72.md) | Hualien M7.2 single-event detail — fully consistent with `12_submit_case_study_hualien_m72.md` |

## Headline findings from this review

1. **Two figures share an unresolved n=44 cohort.** `fig_alert_timeline.png`
   and `fig_detection_categories.png` both analyze 44 I≥4 events, while
   every manuscript section that discusses the SSIF/eBEAR comparison
   (10_, 11_, the abstract) and `fig_region_contingency.png` use 50
   matched testing events (39 region-positive, 11 region-negative).
   The "SSIF only" count in `fig_detection_categories.png` (3, from
   EW20 onward) doesn't match the "2 events eBEAR missed" figure quoted
   in the abstract and 11_. See
   [`fig_detection_categories.md`](fig_detection_categories.md) for
   detail. **Recommend regenerating both n=44 figures against the same
   50-event cohort, or explaining in their captions what the 44-event
   cohort is**, before either goes into the submission.
2. **Two architecture figures exist** (`SSIF_Architecture.png` and
   `fig_ssif_architecture.png`) with overlapping but not identical
   content — the latter additionally shows the joint-loss weights.
   Recommend picking one as canonical (see
   [`fig_ssif_architecture.md`](fig_ssif_architecture.md) for a
   side-by-side comparison) rather than carrying both into the paper.
3. **One unlabeled marker.** `fig_case_study_hualien_m72.png` panel (b)
   plots eBEAR's 14.0 s/M6.8 magnitude revision as an open diamond with
   no legend entry.
4. Everything else checked out: `fig_station_event_map.png`'s split
   counts and `fig_region_contingency.png`'s per-window contingency
   counts match their corresponding manuscript sections exactly, and
   `fig_case_study_hualien_m72.png`'s numbers match
   `12_submit_case_study_hualien_m72.md` line for line.

> 中文摘要見 [README.zh-TW.md](README.zh-TW.md) 的「圖表」章節。
