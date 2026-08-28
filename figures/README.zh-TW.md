# 圖表 — 索引與分析（中文版）

本目錄中每張圖片都有一份同檔名的 `.md` 分析檔，詳細說明圖片內容、對應
論文哪個章節，以及審閱過程中發現的問題。

| 圖片 | 分析檔 | 摘要 |
|---|---|---|
| `SSIF_Architecture.pdf`（PNG 已刪除） | [`SSIF_Architecture.zh-TW.md`](SSIF_Architecture.zh-TW.md) | 投稿用模型架構圖（印刷安全、單色系設計） |
| [`fig_ssif_architecture.png`](fig_ssif_architecture.png) | [`fig_ssif_architecture.zh-TW.md`](fig_ssif_architecture.zh-TW.md) | 另一版彩色架構圖——額外呈現四項聯合損失權重 |
| [`fig_station_event_map.png`](fig_station_event_map.png) | [`fig_station_event_map.zh-TW.md`](fig_station_event_map.zh-TW.md) | 台灣地圖：642 測站 + 670/147/147 訓練/驗證/測試事件 |
| [`fig_region_contingency.png`](fig_region_contingency.png) | [`fig_region_contingency.zh-TW.md`](fig_region_contingency.zh-TW.md) | 各時窗的區域式 TP/FP/FN/TN，50 個配對事件——與論文完全吻合 |
| [`fig_detection_categories.png`](fig_detection_categories.png) | [`fig_detection_categories.zh-TW.md`](fig_detection_categories.zh-TW.md) | SSIF/eBEAR 各時窗的「皆偵測／各自偵測／皆漏失」分類——**n=44，與其他章節使用的 50/39 事件群組對不上** |
| [`fig_alert_timeline.png`](fig_alert_timeline.png) | [`fig_alert_timeline.zh-TW.md`](fig_alert_timeline.zh-TW.md) | 每個事件的 eBEAR 延遲 vs. SSIF 最早偵測時窗，n=44——同樣的群組疑問，另有未標示的長條底色差異 |
| [`fig_case_study_hualien_m72.png`](fig_case_study_hualien_m72.png) | [`fig_case_study_hualien_m72.zh-TW.md`](fig_case_study_hualien_m72.zh-TW.md) | 花蓮 M7.2 單一事件詳圖——與 `12_submit_case_study_hualien_m72.md` 完全一致 |

## 本次審閱的重點發現

1. **兩張圖使用了未解釋的 n=44 事件群組。** `fig_alert_timeline.png` 與
   `fig_detection_categories.png` 都分析 44 個 I≥4 事件，但所有討論
   SSIF/eBEAR 比較的論文章節（10_、11_、摘要）以及
   `fig_region_contingency.png` 用的都是 **50 個配對測試事件（39 個
   區域正例、11 個區域負例）**。`fig_detection_categories.png` 中
   「SSIF only」的數字（EW20 之後為 3）與摘要及 11_ 文件所述「eBEAR
   漏掉 2 個事件」對不上。詳見
   [`fig_detection_categories.zh-TW.md`](fig_detection_categories.zh-TW.md)。
   **建議在納入投稿前，將這兩張 n=44 的圖重新以相同的 50 事件群組
   產出，或在圖說中說明 44 這個群組的定義。**
2. ~~存在兩張重複的架構圖~~ **已處理：** `SSIF_Architecture.png` 已刪除，
   目前保留 `fig_ssif_architecture.png`（額外呈現聯合損失權重）與
   `SSIF_Architecture.pdf` 兩份架構相關檔案——各自涵蓋的內容比較詳見
   [`fig_ssif_architecture.zh-TW.md`](fig_ssif_architecture.zh-TW.md)。
3. **一個未標示的圖例標記。** `fig_case_study_hualien_m72.png` 面板 (b)
   中，eBEAR 14.0 秒／M6.8 的修正估計值以空心菱形繪製，但圖例中沒有
   對應說明。
4. 其餘檢查皆無問題：`fig_station_event_map.png` 的資料切分數量與
   `fig_region_contingency.png` 各時窗的列聯表數字，都與對應的論文章節
   完全吻合；`fig_case_study_hualien_m72.png` 的所有數字也與
   `12_submit_case_study_hualien_m72.md` 逐項一致。

> English version: [README.md](README.md)
