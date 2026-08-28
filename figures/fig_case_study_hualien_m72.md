# fig_case_study_hualien_m72.png — Hualien M7.2 Case Study Figure

**Type:** Two-panel figure for the single 2024-04-03 M7.2 Hualien event
(526 station–event records, 515 with actual I≥4).

## What it shows

**(a) Station-level detection bar chart** (one bar per window,
W10…W40): stacked TP (blue, correctly alerted) / Anticipatory TP
(green hatch, alerted before the station locally observed I≥4) / FN
(orange, missed), against a dashed reference line at 515 (actual I≥4
count):

| Window | TP | Anticipatory TP (subset of TP) | FN | POD |
|---|---|---|---|---|
| W10 | 18 | 1 | 497 | 0.035 |
| W15 | 35 | 5 | 480 | 0.068 |
| W20 | 81 | 30 | 434 | 0.157 |
| W25 | 210 | 102 | 305 | 0.408 |
| W30 | 363 | 103 | 152 | 0.705 |
| W35 | 414 | 62 | 101 | 0.804 |
| W40 | 436 | 50 | 79 | 0.847 |

Zero false alarms at every window (stated in the panel title).

**(b) Alert timeline**: eBEAR's first alert at **9.4 s** (M=6.2,
red triangle), a revised estimate at **14.0 s** (M=6.8, open diamond,
unlabeled in the legend), against SSIF's 7 window detections plotted as
blue dots with the cumulative detected-station count labeled at each
(18/35/81/210/363/414/436), with a callout on the EW20 point noting
"81 stations detected (30 anticipatory, 0 false alarm)."

## Cross-reference

Already used as the figure for
[`12_submit_case_study_hualien_m72.md`](../12_submit_case_study_hualien_m72.md)
(`![Case Study...](figures/fig_case_study_hualien_m72.png)`), and every
number in panel (a)'s table matches that file's table exactly. The
9.4 s / M6.2 first-alert and 14.0 s / M6.8 revision also match the
"Comparison with eBEAR" section of the same file.

## Observations

- Anticipatory TP peaks at W25–W30 (102–103 stations) then declines
  (62 at W35, 50 at W40) as most stations that will reach I≥4 have
  already crossed the threshold locally by then — the same
  anticipatory-vs-confirmatory shift described generally in
  [`13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md`](../13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md),
  now shown for one concrete, large event.
- Panel (b)'s open-diamond marker (eBEAR's 14.0 s / M6.8 revision) has
  no legend entry — only "eBEAR alert time" (filled triangle) and "SSIF
  window detection" (filled circle) are defined. Worth adding a legend
  entry or a text label before submission, since a reviewer has no way
  to identify that mark from the legend alone.
- This is the only one of the six analyzed figures whose numbers were
  found to be **fully self-consistent** with its corresponding
  manuscript section — no discrepancies noted (contrast with
  [`fig_alert_timeline.md`](fig_alert_timeline.md) and
  [`fig_detection_categories.md`](fig_detection_categories.md)).

## Suggested manuscript placement

Already correctly placed — the figure for
[`12_submit_case_study_hualien_m72.md`](../12_submit_case_study_hualien_m72.md).
Only the missing legend entry for the open-diamond marker needs fixing.

> 中文版: [fig_case_study_hualien_m72.zh-TW.md](fig_case_study_hualien_m72.zh-TW.md)
