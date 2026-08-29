# SSIF 論文章節文件

本儲存庫以個別 Markdown 檔案存放 SSIF（Second-by-second Seismic Intensity
Forecaster，逐秒地震強度預測器）論文的各章節草稿。檔案編號依論文的邏輯閱讀
順序排列：

**摘要 → 前言 → 方法 → 模型架構 → 多任務最佳化與評估框架 → 資料 → 結果 → 案例研究 → 討論 → 結論**

| # | 檔案 | 章節 |
|---|---|---|
| 01 | [01_submit_abstract.md](01_submit_abstract.md) | 摘要（Abstract） |
| 02 | [02_submit_Introduction.md](02_submit_Introduction.md) | 前言 — 研究動機、現行以震源參數為基礎之地震預警系統的限制、觀測驅動方法與研究目標 |
| 03 | [03_submit_Method.md](03_submit_Method.md) | 方法 — 建模方法與研究目標 |
| 04 | [04_submit_Model_Architecture_and_Input_Representation.md](04_submit_Model_Architecture_and_Input_Representation.md) | 模型架構與輸入表示法 |
| 05 | [05_submit_Multitask_Optimization_and_Evaluation_Framework.md](05_submit_Multitask_Optimization_and_Evaluation_Framework.md) | 多任務最佳化與評估框架 |
| 06 | [06_submit_Data.md](06_submit_Data.md) | 資料 — 震度觀測資料與警報任務定義、資料切分與模型選擇流程 |
| 07 | [07_submit_Results.md](07_submit_Results.md) | 結果 — 總覽、測站層級警報與震度分類預測、持續性基準與預警偵測、區域式偵測與 eBEAR 互補性、泛化能力 |
| 08 | [08_submit_case_study_hualien_m72.md](08_submit_case_study_hualien_m72.md) | 案例研究 — 2024 年 M7.2 花蓮地震，SSIF 對比 eBEAR |
| 09 | [09_submit_Discussion.md](09_submit_Discussion.md) | 討論 — 速度與可靠度的取捨及作業時窗選擇 |
| 10 | [10_submit_Conclusions.md](10_submit_Conclusions.md) | 結論 — 作業整合與預警／確認的取捨 |

這是 10 個檔案的版面。「模型架構與輸入表示法」（04）、「多任務最佳化與
評估框架」（05）與「花蓮 M7.2 案例研究」（08）已各自獨立成章節——三者
原本都是「方法」或「結果」底下的子章節。其餘章節內容不變。章節順序現在
依照依賴關係排列：方法（為什麼）→ 模型架構（是什麼）→ 多任務最佳化與
評估框架（如何訓練與衡量）→ 資料 → 結果 → 案例研究，因此不會有章節提前
引用讀者尚未讀到的概念；「結果」章節結尾加了一句話，指向緊接其後的
「案例研究」章節。摘要（01）與前言（02）全程維持不動。

## 一致性審閱

[`CONSISTENCY_REVIEW.zh-TW.md`](CONSISTENCY_REVIEW.zh-TW.md) 逐一比對全部
10 個投稿檔案，找出彼此對不上的數字／論述，以及文字表達不清楚或未定義
之處——包括摘要中的精確率數字與 Results 章節矛盾、Data 章節驗證集細分
人數的加總錯誤，以及最近一次拆章後遺留的過時交叉引用。文末附上依優先
順序排列的下一步建議。

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
