# Manuscript Consistency Review

A cross-check of all 10 submission files (`01_` through `10_`) for
numbers, claims, and cross-references that don't agree with each other,
plus wording that's unclear as written. Findings are ranked by severity;
each links to the exact sentence and quotes the conflicting values so
they can be verified independently.

## High priority — numeric or factual errors

### 1. Abstract's precision floor contradicts the Results chapter

- **Abstract** (`01_submit_abstract.md`): "SSIF achieved precision **≥ 0.93**
  and probability of detection (POD) rising from 0.257 at the 10-second
  window..."
- **Results — Station-Level Alert and Class Prediction**
  (`07_submit_Results.md`): "all windows maintain precision between
  **0.922** (15-second window, the lowest) and 0.985 (25-second window,
  the highest)."

The POD figures quoted in the same abstract sentence (0.257 → 0.907)
match the *station-level* numbers exactly, so the precision claim is
describing the same station-level metric — whose actual floor is 0.922,
not 0.93. **0.922 rounds to 0.92, not 0.93.** This is the single most
visible number in the paper (it's in the abstract) and it doesn't match
the body. Fix by changing the abstract to "≥ 0.92" (or the exact "≥ 0.922"),
or explain if a different quantity was intended.

### 2. Data chapter's validation-split arithmetic doesn't add up

**`06_submit_Data.md`**, "Data Partitioning and Model Selection Protocol":

> "...validation (147 events, ≈15%)..."
>
> "...The validation subset (**73** events)... the calibration subset
> (**36** events)... An internal test subset (**36** events)..."

73 + 36 + 36 = **145**, not 147. Two events in the validation split are
unaccounted for. Either the subdivision counts are off by one each
(74+36+37, 73+37+37, etc. — several combinations sum to 147) or the
147 total needs correcting.

### 3. Case study's percentage doesn't match its own numerator/denominator

**`08_submit_case_study_hualien_m72.md`**: "The CWA network recorded 526
station–event records for this earthquake, of which **515 stations
(97.8%)** experienced a final peak intensity of CWA class ≥4."

515 / 526 = 0.9791 → **97.9%**, not 97.8%. Off by one rounding step.

### 4. Method chapter's forward-reference is stale after the last restructuring

**`03_submit_Method.md`**: "...while SSIF is limited by the amount of
seismic information that has reached the station by the prediction time.
**The full architecture, training procedure, and evaluation framework
are described in the following chapter, Model Architecture and Input
Representation.**"

This sentence was accurate when Model Architecture and Multitask
Optimization/Evaluation Framework were one chapter. They were since
split into two separate chapters (`04_` and `05_`), and `04_` now covers
only the architecture — training and evaluation moved to `05_`. The
sentence in `03_` still claims a single "following chapter" covers all
three things. Needs to say "the following two chapters" (or name both
`04_` and `05_`).

*(This is a leftover from the most recent chapter-splitting request in
this conversation — the assistant updated the forward-reference at the
end of `04_` but missed the one earlier in `03_` that pointed at the
pre-split `04_`.)*

### 5. Results claims SSIF "matches" eBEAR's POD when the same paragraph shows it doesn't

**`07_submit_Results.md`**, "Region-Based Detection and eBEAR
Complementarity": "SSIF at the 20-second window **matches** eBEAR's POD
while exceeding it in precision..."

Two sentences earlier in the *same* paragraph: SSIF's 20-second POD is
1.000 (all 39 region-positive events detected) and eBEAR's is a fixed
0.949 — and the very next sentence says "eBEAR misses 2 region-positive
events, SSIF misses none," which is only possible if SSIF's POD is
*higher*, not equal. "Matches" should read "exceeds" or "surpasses."

## Medium priority — unclear or undefined wording

### 6. "ST − OT" is never defined

**`08_submit_case_study_hualien_m72.md`**: "The operational eBEAR system
issued its first alert 9.4 seconds after origin time (**ST − OT** =
9.44 s)..." `ST` and `OT` (presumably Solution/System Time and Origin
Time) are used without a definition anywhere in the 10 files. Spell it
out on first use.

### 7. Inconsistent magnitude-type labeling for the same event

**`02_submit_Introduction.md`** refers to "the 2024 **ML** 7.2 Hualien
earthquake" (local magnitude), while every other chapter (`06_`, `07_`,
`08_`) calls the same event simply "**M**7.2" with no magnitude type
specified. It's not clear from the text whether these are the same
number under different naming conventions, or whether ML was an early
operational estimate later revised to a different scale. Worth a
one-clause clarification wherever the magnitude type first appears.

### 8. The Discussion's 20-second station-level POD number isn't traceable to Results

**`09_submit_Discussion.md`**: "At this window, station-level POD reaches
**0.512**..." — Results (`07_`) only ever states the two endpoint values
(0.257 at 10 s, 0.907 at 40 s) in prose; no per-window station-level POD
table exists anywhere in the 10 files to verify 0.512 against (unlike the
Hualien case study, which does include a full per-window table). Not
necessarily wrong, but a reader has no way to check it from the text
alone.

### 9. The Generalization section's "maximum gap" isn't attributed to a specific window

**`07_submit_Results.md`**, "Generalization": "The training–testing F1
gap is largest at early windows (**−0.077** at 10 seconds)... A maximum
gap of **7.8 percentage points** is modest..." 0.077 is 7.7 percentage
points, not 7.8 — close enough to read as a typo, but the text never
states which window actually produces the 7.8pp maximum (10 s is offered
as representative of "early windows," not explicitly as the maximum).
Either cite the window where 7.8pp occurs, or correct 7.8 to 7.7.

## Lower priority — structural gap

### 10. No References / Bibliography chapter exists

The 10 files cite roughly 17 sources by author-year (Hoshiba and Aoki,
2015; Jozinović et al., 2020; Li et al., 2018; Mousavi and Beroza, 2020;
Wang et al., 2022; Huang et al., 2025; Baevski et al., 2020; Allen et
al., 2009; Allen and Melgar, 2019; Zhang et al., 2021; Colombelli et
al., 2012; Lara et al., 2023; Lin et al., 2021; Hoshiba et al., 2011;
Kodera et al., 2021; Song et al., 2025; Kodera et al., 2018), but there
is no `11_submit_References.md` or equivalent. Every in-text citation is
currently unresolvable to a full reference.

## Already tracked elsewhere (figure-level, not text-level)

These were found during the earlier figure review
(see [`figures/README.md`](figures/README.md)) and are not re-derived
here, but they affect overall submission consistency and are worth
resolving alongside the items above:

- `fig_detection_categories.png` and `fig_alert_timeline.png` use an
  n=44 event cohort that doesn't reconcile with the n=50 (39
  region-positive) cohort used throughout the text.
- `fig_case_study_hualien_m72.png` panel (b) has an unlabeled
  open-diamond marker.
- `fig_alert_timeline.png`'s eBEAR delay for the Hualien event (~26 s)
  doesn't match the 9.4 s first-alert time stated in
  `08_submit_case_study_hualien_m72.md`.

## Suggested next steps

In priority order:

1. **Fix the five high-priority items above** — these are the ones a
   careful reviewer or co-author will catch immediately (#1 especially,
   since it's in the abstract). Items #1–#3 need the original analysis
   re-checked to determine the correct number, not just a text edit;
   #4 and #5 are pure text fixes.
2. **Resolve the two medium-priority definitional gaps** (#6, #7) with a
   one-clause addition each — low effort, removes reviewer confusion.
3. **Decide whether to add a per-window station-level POD table** to
   `07_submit_Results.md` (addresses #8) — the Hualien case study already
   sets the precedent with its Window/TP/FP/FN/POD table; an aggregate
   equivalent would make every per-window number in Discussion and
   Conclusions independently checkable.
4. **Add a References chapter** (#10) before this goes anywhere near
   submission — reserve `11_submit_References.md` and update both
   READMEs' section tables once it exists.
5. **Resolve the figure-level items** tracked in
   [`figures/USAGE_AND_NEXT_STEPS.md`](figures/USAGE_AND_NEXT_STEPS.md) —
   several of them (the n=44 cohort, the eBEAR timing mismatch) touch the
   same underlying numbers as #1–#5 above, so it may be efficient to
   re-run the original analysis scripts once and fix the text, tables,
   and figures together rather than patching each document separately.
6. **Run one more full pass after fixes land** — several of these
   corrections (especially #1 and #2) may cascade into other numbers
   that currently look consistent only because they're derived from the
   same (possibly incorrect) source values.

> 中文版: [CONSISTENCY_REVIEW.zh-TW.md](CONSISTENCY_REVIEW.zh-TW.md)
