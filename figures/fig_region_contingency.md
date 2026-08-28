# fig_region_contingency.png — Region-Based Event Detection Contingency Table

**Type:** Stacked bar chart, one bar per early window (EW10…EW40),
50 matched testing events total (39 region-positive, 11 region-negative).

## What it shows

Per-window counts of the four contingency outcomes for the 47-reference-point
region-based detection criterion (≥3 co-located stations with I≥4 within a
30 km radius):

| Window | TP | FP | FN | TN | POD | Precision |
|---|---|---|---|---|---|---|
| EW10 | 34 | 0 | 5 | 11 | 0.872 | 1.000 |
| EW15 | 37 | 1 | 2 | 10 | 0.949 | 0.974 |
| EW20 | 39 | 3 | 0 | 8 | 1.000 | 0.929 |
| EW25 | 39 | 0 | 0 | 11 | 1.000 | 1.000 |
| EW30 | 39 | 0 | 0 | 11 | 1.000 | 1.000 |
| EW35 | 39 | 0 | 0 | 11 | 1.000 | 1.000 |
| EW40 | 39 | 0 | 0 | 11 | 1.000 | 1.000 |

(TN values read off the chart as 50 − TP − FP − FN; not separately
labeled in every bar.)

## Cross-reference

These exact figures (34/39 at 10 s, perfect POD from 20 s, perfect
precision+POD from 25 s onward) match
[`10_submit_Region_Based_Detection_and_Complementarity.md`](../10_submit_Region_Based_Detection_and_Complementarity.md)
line for line, and the "39 region-positive / 11 region-negative" split
matches the same file and
[`11_submit_Complementary_Failure_Modes_and_Generalization.md`](../11_submit_Complementary_Failure_Modes_and_Generalization.md).

## Observations

- EW20 is the only window with a false alarm (FP=3) rather than a miss —
  the moment SSIF crosses from "still missing 0 events" (EW15: FN=2) to
  "detects everything but over-triggers on 3 borderline regions"
  (EW20), before both errors vanish from EW25 onward. This is the
  precision dip mentioned qualitatively in
  [`13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md`](../13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md)
  as the operational-window trade-off.
- **n=50 here vs. n=44 in `fig_alert_timeline.png` / `fig_detection_categories.png`**
  — see the note in
  [`fig_detection_categories.md`](fig_detection_categories.md) for the
  apparent cohort-size discrepancy between figures.

## Suggested manuscript placement

Results section — pairs with
[`10_submit_Region_Based_Detection_and_Complementarity.md`](../10_submit_Region_Based_Detection_and_Complementarity.md)
as its primary supporting figure.
