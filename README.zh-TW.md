# SSIF 論文章節文件

本儲存庫以個別 Markdown 檔案存放 SSIF（Second-by-second Seismic Intensity
Forecaster，逐秒地震強度預測器）論文的各章節草稿。檔案編號依論文的邏輯閱讀
順序排列：

**摘要 → 前言 → 方法 → 資料 → 結果 → 討論 → 結論**

| # | 檔案 | 章節 |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | 摘要（Abstract） |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | 前言 — 研究動機、現行以震源參數為基礎之地震預警系統的限制、觀測驅動方法與研究目標 |
| 03 | [03_submit_Method.md](03_submit_Method.md) | 方法 — 建模方法與研究目標、模型架構與輸入表示法、多任務最佳化與評估框架 |
| 04 | [04_submit_Data.md](04_submit_Data.md) | 資料 — 震度觀測資料與警報任務定義、資料切分與模型選擇流程 |
| 05 | [05_submit_Results.md](05_submit_Results.md) | 結果 — 總覽、測站層級警報與震度分類預測、持續性基準與預警偵測、區域式偵測與 eBEAR 互補性、泛化能力，以及 2024 年 M7.2 花蓮地震案例研究 |
| 06 | [06_submit_Discussion.md](06_submit_Discussion.md) | 討論 — 速度與可靠度的取捨及作業時窗選擇 |
| 07 | [07_submit_Conclusions.md](07_submit_Conclusions.md) | 結論 — 作業整合與預警／確認的取捨 |

03–07 章節已從先前 14 個檔案（每個子章節一個檔案）整併為每個頂層章節一個
檔案，並以 `##`／`###` 子標題保留原本的子章節結構。摘要（01）與前言（02）
維持不動；原本位於前言與方法之間、獨立成檔的「觀測驅動方法與研究目標」，
現已成為 03_submit_Method.md 開頭的 `##` 子章節，因為其內容是在闡述 SSIF
的建模方法，而非如 02_submit_Introduction.md 那樣鋪陳研究動機。

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
[03_submit_Method.md](03_submit_Method.md)
所描述的模型架構：輸入表示法、卷積主幹、位置編碼、遮罩 Transformer 編碼器、
遮罩平均池化，以及兩個多任務輸出頭。

> English version: [README.md](README.md)
