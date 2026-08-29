# 圖片使用狀況與下一步建議（中文版）

盤點 `figures/` 目錄內 7 張圖片：目前是否已插入論文章節、應該放在哪個
章節、以及卡住的原因。詳細的逐圖分析請見 [`README.zh-TW.md`](README.zh-TW.md)，
本文的內容即根據該索引整理而成。

## 目前使用狀況

| 圖片 | 目前已插入？ | 應放置章節 | 卡住原因 |
|---|---|---|---|
| `fig_case_study_hualien_m72.png` | ✅ [08_submit_case_study_hualien_m72.md](../08_submit_case_study_hualien_m72.md) | ——（已就位） | 小問題：面板 (b) 的空心菱形標記缺少圖例說明 |
| `fig_station_event_map.png` | ❌ 尚未插入任何章節 | [06_submit_Data.md](../06_submit_Data.md) | 無——可直接插入 |
| `fig_region_contingency.png` | ❌ 尚未插入任何章節 | [07_submit_Results.md](../07_submit_Results.md)「區域式偵測與 eBEAR 互補性」子章節 | 無——可直接插入 |
| `fig_detection_categories.png` | ❌ 尚未插入任何章節 | 07_submit_Results.md，同一子章節 | **n=44 事件群組與正文使用的 50/39 群組對不上** |
| `fig_alert_timeline.png` | ❌ 尚未插入任何章節 | 07_submit_Results.md 或 [09_submit_Discussion.md](../09_submit_Discussion.md) | 同樣的 n=44 落差，另有 3 筆未標示說明的長條底色差異 |
| `fig_ssif_architecture.png` | ❌ 尚未插入任何章節 | [04_submit_Model_Architecture_and_Input_Representation.md](../04_submit_Model_Architecture_and_Input_Representation.md) / [05_submit_Multitask_Optimization_and_Evaluation_Framework.md](../05_submit_Multitask_Optimization_and_Evaluation_Framework.md) | 與 `SSIF_Architecture.pdf` 內容重疊——需擇一作為正式圖 |
| `SSIF_Architecture.pdf` | ❌ 尚未插入（PDF 無法在 Markdown 中內嵌顯示） | 同上 | 若要內嵌顯示需重新輸出 PNG；若只作為可下載連結則沒問題 |

**結論：7 張圖中目前只有 1 張真正放進論文章節。** 其餘 6 張都存放在
`figures/` 且已完成分析，但除了 `08_submit_case_study_hualien_m72.md`
之外，目前沒有任何章節實際顯示圖片——讀者依序讀到案例研究章節之前，
完全看不到任何圖表。

## 下一步建議（依優先順序）

1. **解決 n=44 vs n=50/39 事件群組不一致的問題**（卡住 6 張未插入圖片
   中的 2 張）。這需要原始分析程式／資料才能修，不是單純改文件就能
   解決——確切對不上的數字請見
   [`fig_detection_categories.md`](fig_detection_categories.md)。可以
   選擇：用與 [07_submit_Results.md](../07_submit_Results.md) 及摘要
   相同的 50 事件／39 區域正例群組重新產出 `fig_detection_categories.png`
   與 `fig_alert_timeline.png`；或者如果 44 這個群組是刻意的，就在圖說
   中說明其定義。
2. **擇一作為正式的架構圖**——`fig_ssif_architecture.png`（含聯合損失
   權重，印刷友善度較低）或 `SSIF_Architecture.pdf`（印刷友善、向量格式，
   不含損失權重）。兩者的並列比較請見
   [`fig_ssif_architecture.md`](fig_ssif_architecture.md)。若選定
   `SSIF_Architecture.pdf`，需從 `SSIF_Architecture_source.html` 重新
   輸出一份 PNG 供 Markdown 內嵌顯示（PDF 在 GitHub／多數 Markdown
   檢視器中無法內嵌顯示）。
3. **先插入兩張已確認無誤、可直接使用的圖**：
   - `fig_station_event_map.png` → 插入 06_submit_Data.md
   - `fig_region_contingency.png` → 插入 07_submit_Results.md
4. **修正 `fig_case_study_hualien_m72.png` 面板 (b) 中空心菱形標記缺少
   圖例說明的問題**——這只是標示問題，不是資料問題。
5. **待第 1 點解決後**，將 `fig_detection_categories.png` 與
   `fig_alert_timeline.png` 插入對應章節。
6. **待所有圖片位置確定後，統一加上圖號與圖說格式**（例如「Figure 1」
   「Figure 2」……）——目前只有案例研究那張圖有圖說，且沒有任何圖片
   編號，等論文整合投稿時這點會需要處理。

> English version: [USAGE_AND_NEXT_STEPS.md](USAGE_AND_NEXT_STEPS.md)
