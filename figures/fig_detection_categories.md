# fig_detection_categories.png — Detection Categories: SSIF vs eBEAR Complementarity

**Type:** Stacked bar chart, one bar per early window (EW10…EW40),
**n=44** I≥4 events, four categories: Both detect / SSIF only / eBEAR
only / Both miss.

## What it shows

| Window | Both detect | SSIF only | eBEAR only | Both miss |
|---|---|---|---|---|
| EW10 | 36 | 2 | 5 | 1 |
| EW15 | 39 | 2 | 2 | 1 |
| EW20 | 41 | 3 | 0 | 0 |
| EW25 | 41 | 3 | 0 | 0 |
| EW30 | 41 | 3 | 0 | 0 |
| EW35 | 41 | 3 | 0 | 0 |
| EW40 | 41 | 3 | 0 | 0 |

From EW20 onward the split is fixed at 41 (both) + 3 (SSIF-only) = 44,
with eBEAR-only and both-miss both at zero — i.e. every event either
system fails to catch alone is caught by the other.

## Cross-reference

Qualitatively matches the complementarity narrative in the "Region-Based
Detection and eBEAR Complementarity" subsection of
[`05_submit_Results.md`](../05_submit_Results.md)
and the abstract's "SSIF detected 2 region-positive events that eBEAR
missed" — but the **numbers don't line up exactly**, see below.

## ⚠ Data-consistency note (n=44 vs n=50/39)

This figure and `fig_alert_timeline.png` both use a cohort of **n=44**
events. Every part of the manuscript that discusses the SSIF/eBEAR
comparison (the "Region-Based Detection and eBEAR Complementarity"
subsection of [`05_submit_Results.md`](../05_submit_Results.md) and the
abstract) instead uses **50 matched testing events (39 region-positive,
11 region-negative)**, and `fig_region_contingency.png` matches that
50/39/11 figure exactly.

Two numbers that should be reconcilable but currently aren't, at face
value:
- Abstract / 05_: eBEAR misses **2** region-positive events → SSIF
  catches those 2 that eBEAR missed.
- This figure at EW20+: **SSIF only = 3**, **eBEAR only = 0**.

44 vs. 50 is a 6-event gap, and "SSIF only" here (3) doesn't match "SSIF
detected 2 events eBEAR missed" from the prose. Plausible explanations
(none confirmed — worth checking against the source analysis script/data
before using this figure in the submission):
- n=44 may be a different denominator, e.g. only events where eBEAR
  issued *any* alert (excluding some region-negative or unmatched
  events), rather than the full 50 matched / 39 region-positive set.
- "SSIF only" / "eBEAR only" here may be defined at the **event** level
  under a different criterion than the region-based (47-reference-point,
  ≥3 stations) criterion used for the 50/39/11 numbers.

Recommend regenerating this figure from the same 50-event / 39-positive
cohort used everywhere else before including it in the submission, or
adding a note explaining what distinguishes the 44-event cohort.

## Suggested manuscript placement

Results section (05_), alongside the "Region-Based Detection and eBEAR
Complementarity" subsection — but only after the n=44 vs n=50
discrepancy above is resolved.

> 中文版: [fig_detection_categories.zh-TW.md](fig_detection_categories.zh-TW.md)
