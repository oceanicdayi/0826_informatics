# fig_case_study_hualien_m72.png — 花蓮 M7.2 案例研究圖（中文版）

**類型：** 雙面板圖，聚焦單一 2024-04-03 M7.2 花蓮地震事件（526 筆
測站－事件紀錄，其中 515 筆實際 I≥4）。

## 圖片內容

**(a) 測站層級偵測長條圖**（每個時窗 W10…W40 一根長條）：堆疊呈現
TP（藍色，正確發出警報）／Anticipatory TP（綠色網底，於測站在地觀測
到 I≥4 之前就已發出警報）／FN（橘色，漏失），並以虛線標示實際 I≥4
數（515）作為參考：

| 時窗 | TP | Anticipatory TP（TP 的子集） | FN | POD |
|---|---|---|---|---|
| W10 | 18 | 1 | 497 | 0.035 |
| W15 | 35 | 5 | 480 | 0.068 |
| W20 | 81 | 30 | 434 | 0.157 |
| W25 | 210 | 102 | 305 | 0.408 |
| W30 | 363 | 103 | 152 | 0.705 |
| W35 | 414 | 62 | 101 | 0.804 |
| W40 | 436 | 50 | 79 | 0.847 |

每個時窗皆為零誤報（面板標題中已說明）。

**(b) 警報時間軸**：eBEAR 首次警報於 **9.4 秒**發出（M=6.2，紅色三角
形），並於 **14.0 秒**修正為 M=6.8（空心菱形，圖例中未標示），對照
SSIF 的 7 個時窗偵測結果（藍色圓點），並在每點標示累積偵測測站數
（18／35／81／210／363／414／436），EW20 的點附近另有註記文字「81
stations detected（30 anticipatory, 0 false alarm）」。

## 對應章節

此圖已用作
[`07_submit_case_study_hualien_m72.md`](../07_submit_case_study_hualien_m72.md)
的配圖（`![Case Study...](figures/fig_case_study_hualien_m72.png)`），
面板 (a) 表格中的每個數字都與該文件的表格完全吻合。9.4 秒／M6.2 首次
警報與 14.0 秒／M6.8 修正值，也與該文件「Comparison with eBEAR」段落
一致。

## 觀察重點

- Anticipatory TP 在 W25–W30 達到高峰（102–103 個測站），之後下降
  （W35 為 62、W40 為 50），因為多數最終會達到 I≥4 的測站到此時已在
  本地觀測到門檻——這正是
  [`08_submit_Discussion.md`](../08_submit_Discussion.md)
  中一般性描述的「預警 vs. 確認」轉變，此處以一個具體的大型事件呈現。
- 面板 (b) 中的空心菱形標記（eBEAR 14.0 秒／M6.8 的修正值）在圖例中
  沒有對應項目——圖例僅定義了「eBEAR alert time」（實心三角形）與
  「SSIF window detection」（實心圓點）。建議在投稿前補上圖例項目或
  文字標籤，否則審稿人無法單從圖例辨識該標記的意義。
- 在本次分析的六張圖中，這是唯一一張數字與對應論文章節**完全一致、
  沒有發現任何落差**的圖（相對於
  [`fig_alert_timeline.zh-TW.md`](fig_alert_timeline.zh-TW.md) 與
  [`fig_detection_categories.zh-TW.md`](fig_detection_categories.zh-TW.md)
  中發現的問題）。

## 建議放置位置

已正確放置——作為
[`07_submit_case_study_hualien_m72.md`](../07_submit_case_study_hualien_m72.md)
的配圖。僅需修正空心菱形標記缺少圖例說明的問題。
