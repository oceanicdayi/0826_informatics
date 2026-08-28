# fig_alert_timeline.png — eBEAR Alert Time vs SSIF Earliest Detection Window

**Type:** Horizontal bar chart, one row per event (labeled by
`YYYYMMDD_HHMM` origin timestamp), **n=44 I≥4 events**, sorted by eBEAR
alert delay (ST−OT) descending (slowest eBEAR alert at top, fastest at
bottom).

## What it shows

- Pink/salmon bar length = eBEAR's alert delay, ST−OT in seconds
  (roughly 6–33 s across the 44 events).
- Blue dot = the earliest SSIF window (10/15/20/25/30/35/40 s) at which
  SSIF's station-level alert first fires for that event. Most events are
  first caught at the 10 s window (dot sits on the leftmost dashed
  reference line); a handful first fire at 15 or 20 s.
- Dashed vertical reference lines at 10, 20, and 40 s mark SSIF's
  window grid.

## Cross-reference

Same 44-event cohort as
[`fig_detection_categories.png`](fig_detection_categories.png) — see
[`fig_detection_categories.md`](fig_detection_categories.md) for the
open question about how this cohort relates to the 50-event / 39
region-positive cohort used in the "Region-Based Detection and eBEAR
Complementarity" subsection of
[`07_submit_Results.md`](../07_submit_Results.md). The eBEAR delay range
(~6–33 s, median well under 20 s) is broadly consistent with the
"median ~15 s" figure quoted in that same subsection.

## Observations

- Most SSIF detections land at the 10 s window, meaning for a large
  majority of I≥4 events SSIF's *earliest* window already produces a
  station-level alert — the aggregate POD numbers elsewhere (0.257 at
  10 s station-level) describe per-station detection rate, not
  per-event "does at least one station fire," so this is not a
  contradiction, but the two views (per-station POD vs. per-event
  earliest-alert) should not be conflated when writing about this
  figure.
- Three rows (`20240407_1413`, `20250202_0602`, `20260504_0659`) are
  rendered with a visibly **lighter/unfilled pink bar** than the other
  41, with no separate legend entry explaining the distinction. This
  looks like an intentional encoding in the source plotting script
  (e.g. flagging region-negative events, or events with a
  lower-confidence eBEAR magnitude estimate) that lost its legend label
  — worth checking the generating script before this figure goes into
  the submission, since an unexplained visual distinction will confuse
  reviewers.
- The event `20240403_0920` in this list is almost certainly the
  2024-04-03 M7.2 Hualien mainshock — its eBEAR delay bar (~26 s) is
  inconsistent with the reported **9.4 s** first-alert time in
  [`08_submit_case_study_hualien_m72.md`](../08_submit_case_study_hualien_m72.md).
  If this row is the same event, the two figures are describing
  different things (e.g. this chart may show a *later, revised* eBEAR
  alert rather than the first alert) and the discrepancy should be
  resolved or clarified in the caption before submission.

## Suggested manuscript placement

Results (07_) or Discussion (09_), as supporting evidence for the "SSIF
is slower but eBEAR's speed comes with regional coverage gaps" argument
in [`09_submit_Discussion.md`](../09_submit_Discussion.md) —
contingent on resolving the n=44 cohort question and the unlabeled bar
shading first.

> 中文版: [fig_alert_timeline.zh-TW.md](fig_alert_timeline.zh-TW.md)
