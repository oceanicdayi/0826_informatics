# Figure Usage and Next Steps

A status snapshot of the 7 images in this directory: which manuscript
chapter each is embedded in today, which chapter it belongs in, and what
is blocking it from being embedded. See [`README.md`](README.md) for the
detailed per-figure analysis this table is drawn from.

## Current usage

| Image | Embedded today? | Belongs in | Blocker |
|---|---|---|---|
| `fig_case_study_hualien_m72.png` | ✅ [08_submit_case_study_hualien_m72.md](../08_submit_case_study_hualien_m72.md) | — (already placed) | Minor: panel (b)'s open-diamond marker has no legend entry |
| `fig_station_event_map.png` | ❌ not embedded anywhere | [06_submit_Data.md](../06_submit_Data.md) | None — ready to embed |
| `fig_region_contingency.png` | ❌ not embedded anywhere | [07_submit_Results.md](../07_submit_Results.md), "Region-Based Detection and eBEAR Complementarity" | None — ready to embed |
| `fig_detection_categories.png` | ❌ not embedded anywhere | 07_submit_Results.md, same subsection | **n=44 cohort doesn't match the 50/39 cohort used in the text** |
| `fig_alert_timeline.png` | ❌ not embedded anywhere | 07_submit_Results.md or [09_submit_Discussion.md](../09_submit_Discussion.md) | Same n=44 mismatch, plus 3 unlabeled bar shadings |
| `fig_ssif_architecture.png` | ❌ not embedded anywhere | [04_submit_Model_Architecture_and_Input_Representation.md](../04_submit_Model_Architecture_and_Input_Representation.md) / [05_submit_Multitask_Optimization_and_Evaluation_Framework.md](../05_submit_Multitask_Optimization_and_Evaluation_Framework.md) | Competes with `SSIF_Architecture.pdf` — pick one canonical figure |
| `SSIF_Architecture.pdf` | ❌ not embedded (PDFs don't render inline in Markdown) | same as above | Needs a PNG re-render if inline embedding is wanted; otherwise fine as a linked download |

**Bottom line: only 1 of 7 images is actually placed in the manuscript.**
The other 6 exist in `figures/` and have been analyzed, but nothing
outside `08_submit_case_study_hualien_m72.md` currently displays them —
a reader going chapter by chapter would see zero figures until the case
study.

## Next steps

In priority order:

1. **Resolve the n=44 vs. n=50/39 cohort mismatch** (blocks 2 of the 6
   unplaced figures). This needs the original analysis script/data, not
   just a doc edit — see [`fig_detection_categories.md`](fig_detection_categories.md)
   for exactly which numbers don't reconcile. Either regenerate
   `fig_detection_categories.png` and `fig_alert_timeline.png` from the
   same 50-event/39-region-positive cohort used in
   [07_submit_Results.md](../07_submit_Results.md) and the abstract, or
   add a caption explaining what the 44-event cohort is if it's
   intentionally different.
2. **Pick one canonical architecture figure** — `fig_ssif_architecture.png`
   (shows the joint-loss weights, less print-safe) or
   `SSIF_Architecture.pdf` (print-safe, vector, no loss weights). See the
   side-by-side in [`fig_ssif_architecture.md`](fig_ssif_architecture.md).
   If `SSIF_Architecture.pdf` wins, re-render a PNG from
   `SSIF_Architecture_source.html` for inline Markdown embedding (PDFs
   don't display inline on GitHub/most Markdown viewers).
3. **Embed the two figures that are already clean and ready**:
   - `fig_station_event_map.png` into 06_submit_Data.md
   - `fig_region_contingency.png` into 07_submit_Results.md
4. **Fix the unlabeled open-diamond marker** in
   `fig_case_study_hualien_m72.png`'s legend (panel b) — a small
   labeling fix, not a data issue.
5. **Once step 1 is resolved**, embed `fig_detection_categories.png` and
   `fig_alert_timeline.png` into their target chapters.
6. **Add figure numbers and a consistent caption style** once placement
   is final (e.g. "Figure 1", "Figure 2", ...) — right now only the case
   study figure has a caption, and none are numbered, which will matter
   once the manuscript is assembled for submission.

> 中文版: [USAGE_AND_NEXT_STEPS.zh-TW.md](USAGE_AND_NEXT_STEPS.zh-TW.md)
