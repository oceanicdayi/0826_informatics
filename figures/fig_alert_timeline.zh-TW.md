# fig_alert_timeline.png — eBEAR 警報時間 vs. SSIF 最早偵測時窗（中文版）

**類型：** 橫向長條圖，每列一個事件（以 `YYYYMMDD_HHMM` 起始時間標示），
**n=44 個 I≥4 事件**，依 eBEAR 警報延遲（ST−OT）由大到小排序（最上方為
eBEAR 反應最慢的事件，最下方為最快的）。

## 圖片內容

- 粉紅／鮭魚色長條長度＝eBEAR 的警報延遲，即 ST−OT（秒），44 個事件
  約落在 6–33 秒之間。
- 藍色圓點＝SSIF 對該事件最早發出測站層級警報的時窗（10/15/20/25/30/
  35/40 秒）。多數事件在 10 秒時窗即被偵測到（圓點落在最左側的參考虛
  線上）；少數事件在 15 或 20 秒才首次觸發。
- 虛線垂直參考線標示 10、20、40 秒，對應 SSIF 的時窗刻度。

## 對應章節

與 [`fig_detection_categories.png`](fig_detection_categories.png) 使用
相同的 44 事件群組——關於此群組與
[`10_submit_Region_Based_Detection_and_Complementarity.md`](../10_submit_Region_Based_Detection_and_Complementarity.md)、
[`11_submit_Complementary_Failure_Modes_and_Generalization.md`](../11_submit_Complementary_Failure_Modes_and_Generalization.md)
中 50 事件／39 區域正例群組之間關係的未解問題，詳見
[`fig_detection_categories.zh-TW.md`](fig_detection_categories.zh-TW.md)。
eBEAR 延遲範圍（約 6–33 秒，中位數明顯低於 20 秒）大致符合
[`11_submit_Complementary_Failure_Modes_and_Generalization.md`](../11_submit_Complementary_Failure_Modes_and_Generalization.md)
中「中位數約 15 秒」的說法。

## 觀察重點

- 多數 SSIF 偵測落在 10 秒時窗，代表對於大多數 I≥4 事件而言，SSIF
  「最早的」時窗就已經產生測站層級警報——其他章節提到的整體 POD 數字
  （10 秒時站層級 POD 為 0.257）描述的是「每站」偵測率，而非「每事件
  是否至少一站觸發」，因此兩者並不矛盾，但撰文時應避免將這兩種不同的
  觀點（每站 POD vs. 每事件最早警報）混為一談。
- 有三列（`20240407_1413`、`20250202_0602`、`20260504_0659`）的長條
  底色明顯比其餘 41 列更淺／未填滿，但圖例中沒有對應說明。這看起來
  像是原始繪圖程式中一個有意義的編碼（例如標示區域負例事件，或標示
  eBEAR 規模估計信心較低的事件），但對應的圖例標籤遺失了——建議在
  納入投稿前檢查原始繪圖程式，因為未說明的視覺差異容易讓審稿人困惑。
- 清單中的 `20240403_0920` 這筆事件幾乎可以確定就是 2024-04-03 M7.2
  花蓮主震——但其 eBEAR 延遲長條（約 26 秒）與案例研究文件中報告的
  **9.4 秒**首次警報時間不一致。若確認是同一事件，代表兩張圖描述的是
  不同的東西（例如此圖可能呈現的是「較晚、經修正後」的 eBEAR 警報，
  而非首次警報），建議釐清後在圖說中說明。

## 建議放置位置

Results 或 Discussion 章節，作為
[`13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md`](../13_submit_Speed_Reliability_Tradeoff_and_Operational_Window.md)
中「SSIF 較慢但 eBEAR 的速度伴隨區域涵蓋缺口」論點的佐證——但需先解決
上述 n=44 群組定義與長條底色未說明的問題。
