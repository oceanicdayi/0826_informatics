# fig_station_event_map.png — Station and Earthquake Distribution

**Type:** Map of Taiwan (lon/lat, ~119.5–123°E, ~21.5–26°N).

## What it shows

- Black triangles: 642 CWA seismic stations, densely covering the western
  plain, the eastern rift valley, and offshore islets.
- Colored circles: earthquake epicenters, colored by dataset split —
  **blue = training (670)**, **green = validation (147)**, **red = testing
  (147)** — sized by magnitude (legend: M3.0–M7.0).
- Events cluster heavily off the east coast (Hualien/Taitung, the plate
  boundary) and in the western foothills (Chiayi/Nantou), with a sparser
  scatter far offshore to the northeast and southwest.

## Cross-reference

Matches the split counts (670 / 147 / 147 event-level
training/validation/testing split) and the station coverage described in
[`06_submit_Data.md`](../06_submit_Data.md) — the "Data Partitioning and
Model Selection Protocol" and "Intensity Observations and Alert-Task
Formulation" subsections, respectively.

## Observations

- The three splits are visually interleaved rather than regionally
  separated — red (testing) points sit inside the same east-coast and
  western-foothill clusters as blue (training) points, which is the
  expected signature of an event-level (not spatially blocked) split:
  it prevents information leakage across time/event but does not test
  geographic extrapolation.
- The single largest marker in the northeast cluster (near 24.0°N,
  121.8°E) is almost certainly the 2024-04-03 M7.2 Hualien event
  featured in
  [`08_submit_case_study_hualien_m72.md`](../08_submit_case_study_hualien_m72.md).
- Station coverage is visibly sparser offshore and in the southeast
  corner — a plausible geographic source of the longer-window
  performance gap noted for near-source/offshore stations elsewhere in
  the manuscript.

## Suggested manuscript placement

Best suited as a **Data** section figure (06_), to establish the
spatial/temporal representativeness of the train/val/test split before
the Results sections rely on it.

> 中文版: [fig_station_event_map.zh-TW.md](fig_station_event_map.zh-TW.md)
