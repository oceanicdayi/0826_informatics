# SSIF 論文章節文件

本儲存庫以個別 Markdown 檔案存放 SSIF（Second-by-second Seismic Intensity
Forecaster，逐秒地震強度預測器）論文的各章節草稿。檔案編號依論文的邏輯閱讀
順序排列：

**摘要 → 前言 → 方法 → 模型架構 → 資料 → 結果 → 案例研究 → 討論 → 結論**

| # | 檔案 | 章節 |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | 摘要（Abstract） |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | 前言 — 研究動機、現行以震源參數為基礎之地震預警系統的限制、觀測驅動方法與研究目標 |
| 03 | [03_submit_Method.md](03_submit_Method.md) | 方法 — 建模方法與研究目標 |
| 04 | [04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md) | 模型架構與輸入表示法 — 主幹架構、多任務最佳化與評估框架 |
| 05 | [05_submit_Data.md](05_submit_Data.md) | 資料 — 震度觀測資料與警報任務定義、資料切分與模型選擇流程 |
| 06 | [06_submit_Results.md](06_submit_Results.md) | 結果 — 總覽、測站層級警報與震度分類預測、持續性基準與預警偵測、區域式偵測與 eBEAR 互補性、泛化能力 |
| 07 | [07_submit_case_study_hualien_m72.md](07_submit_case_study_hualien_m72.md) | 案例研究 — 2024 年 M7.2 花蓮地震，SSIF 對比 eBEAR |
| 08 | [08_submit_Discussion.md](08_submit_Discussion.md) | 討論 — 速度與可靠度的取捨及作業時窗選擇 |
| 09 | [09_submit_Conclusions.md](09_submit_Conclusions.md) | 結論 — 作業整合與預警／確認的取捨 |

這是 9 個檔案的版面：「模型架構與輸入表示法」（04）與「花蓮 M7.2 案例
研究」（07）已獨立成各自的章節——先前兩者分別是「方法」與「結果」底下的
子章節。其餘章節內容與先前 7 個檔案的版面相同，未變動。因拆分而可能出現
的前後呼應問題，做了兩處小幅調整：原本在「方法」中討論訓練／評估（會提到
池化向量表示）的內容，改移入「模型架構」章節，避免文中提前引用尚未出現
的概念；「結果」章節結尾則加了一句話，指向緊接其後的「案例研究」章節。
摘要（01）與前言（02）全程維持不動。

## 圖表

所有圖表存放於 [`figures/`](figures/)，每張圖都有對應的分析 `.md` 檔——完整
索引與審閱時發現的兩個資料一致性問題（兩張圖使用未對齊的 n=44 vs n=50 事件
群組、以及重複的架構圖）請見 [`figures/README.md`](figures/README.md)。

投稿用架構圖（[`SSIF_Architecture.pdf`](figures/SSIF_Architecture.pdf) —
向量圖；PNG 點陣輸出已移除，如需要可從
[`SSIF_Architecture_source.html`](figures/SSIF_Architecture_source.html)
重新輸出，圖說在
[`SSIF_Architecture_caption.txt`](figures/SSIF_Architecture_caption.txt)）
對應
[04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md)
所描述的模型架構：輸入表示法、卷積主幹、位置編碼、遮罩 Transformer 編碼器、
遮罩平均池化，以及兩個多任務輸出頭。

> English version: [README.md](README.md)
