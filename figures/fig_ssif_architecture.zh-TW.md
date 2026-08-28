# fig_ssif_architecture.png — SSIF 模型架構參考圖（中文版）

**類型：** 由上而下的彩色方塊流程圖（自動產生風格），每個階段一種顏色：
輸入（藍）→ 卷積主幹（橘）→ 位置編碼（紫）→ Transformer 編碼器（靛）→
池化（藍綠）→ 輸出頭（紅／綠）→ 聯合損失（灰）。

## 圖片內容

1. **輸入** `(B, T)`：兩個子方塊——縮放後強度 `[0,1] = intensity/9`，以及
   有效性遮罩 `0/1，缺失=0`。
2. **卷積主幹**：3 層 Conv1d（kernel=3，padding=same），通道數
   2→96→192→192，每層搭配 GroupNorm(8)；每層後接 GELU + Dropout →
   `(B, T, 192)`。
3. **位置編碼**：可學習，`z = x + pos[:, :T, :]`，含遮罩歸零。
4. **Transformer 編碼器**：4 層 pre-norm，每層 4 個注意力頭、d=192、
   FFN 倍率=2、GELU、dropout=0.1；`src_key_padding_mask = ~valid_mask`
   將缺失時間步排除在注意力計算之外。
5. **池化**：遮罩平均池化 + LayerNorm + Dropout，
   `pooled = Σ(x·mask)/Σ(mask) → (B, 192)`。
6. **輸出頭**：10 類強度頭（`Linear(192→10)→Softmax`，預測 CWA 震度類別
   {0,...,7}）與二元警報頭（`Linear(192→1)→Sigmoid`，預測 I≥4）。
7. **聯合損失**（四項加權項，以獨立一列呈現，這是另一張架構圖沒有的
   內容）：
   - 交叉熵（Cross-Entropy），權重 **0.45** — 10 類分類
   - 警報 BCE（Alert BCE），權重 **0.35** — 二元警報 + pos_weight
   - 序數迴歸（Ordinal Regression），權重 **0.15** — 對期望類別的
     Smooth-L1
   - 一致性損失（Consistency），權重 **0.05** — MSE(σ(alert), Σp[k≥4])

## 對應章節

主幹部分對應
[`04_submit_Model_Architecture_and_Input_Representation.md`](../04_submit_Model_Architecture_and_Input_Representation.md)，
損失權重則與
[`05_submit_Multitask_Optimization_and_Evaluation_Framework.md`](../05_submit_Multitask_Optimization_and_Evaluation_Framework.md)
完全一致（0.45／0.35／0.15／0.05）。

## 與 `SSIF_Architecture.pdf` 的關係

> **更新：** `SSIF_Architecture.png` 已從本目錄移除，以解決下方所述的
> 重複問題。以下比較保留作為紀錄，改對照現存的 `SSIF_Architecture.pdf`
> （內容相同，向量格式；如需點陣圖可從 `SSIF_Architecture_source.html`
> 重新輸出）。

本目錄還有另一張獨立繪製的架構圖——
[`SSIF_Architecture.pdf`](SSIF_Architecture.pdf)（詳見
[`SSIF_Architecture.zh-TW.md`](SSIF_Architecture.zh-TW.md)）。兩者內容
大致重疊：

| | fig_ssif_architecture.png | SSIF_Architecture.pdf |
|---|---|---|
| 風格 | 彩色，各階段不同顏色方塊 | 單色系，投稿印刷風格，灰階可辨識 |
| 是否呈現損失項 | 是（4 項皆有，含權重） | 否（僅到兩個輸出頭為止） |
| 有效／遮罩圖例 | 無 | 有 |
| 印刷友善度（黑白、網底圖樣） | 否 | 是 |

若最終論文只保留一張架構圖，可考慮將此圖的「聯合損失」列合併進
`SSIF_Architecture.pdf`（或如
`05_submit_Multitask_Optimization_and_Evaluation_Framework.md` 目前做法，
改以正文文字說明損失權重）。

## 建議放置位置

模型架構與輸入表示法章節（04_）或多任務最佳化與評估框架章節（05_），
作為 Figure 1 或 2——視最終選定哪張
架構圖為正式圖而定。
