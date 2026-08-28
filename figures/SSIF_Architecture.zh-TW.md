# SSIF_Architecture.pdf — 投稿用架構圖（中文版）

**類型：** 由上而下的方塊流程圖，單色系＋兩個強調色（藍／棗紅），專為投稿
印刷設計（原始碼見 `SSIF_Architecture_source.html`，輸出為約 350 dpi 的
PNG 及向量 PDF）。

## 圖片內容

輸入（雙通道 1 Hz 序列 + 有效性遮罩，以柱狀圖示區分有效／遮罩時間步）→
卷積主幹 ×3（2→96→192→192）→「+」可學習位置編碼 → Transformer ×4（
pre-norm、含遮罩的多頭自注意力、前饋層、殘差弧線、遮罩注意力圖示）→
遮罩平均池化（`[B,192]`）→ 兩個輸出頭（Class Head：
`Linear→Softmax(10)`，CWA 震度 0,1,2,3,4,5−,5+,6−,6+,7；Alert Head：
`Linear→Sigmoid(1)`，I≥4，以斜線網底呈現以確保灰階列印時仍可辨識）。

此圖**未**呈現聯合損失的組成（交叉熵／警報 BCE／序數迴歸／一致性損失）
——請見 [`fig_ssif_architecture.zh-TW.md`](fig_ssif_architecture.zh-TW.md)
中有呈現該部分的另一張圖。

## 對應章節

直接根據
[`04_submit_Model_Architecture_and_Input_Representation.md`](../04_submit_Model_Architecture_and_Input_Representation.md)
繪製。建議圖說文字在
[`SSIF_Architecture_caption.txt`](SSIF_Architecture_caption.txt)。

## 檔案說明

| 檔案 | 用途 |
|---|---|
| `SSIF_Architecture.pdf` | 向量圖，適用於 LaTeX／印刷投稿 |
| `SSIF_Architecture_source.html` | 可編輯原始檔（以瀏覽器開啟，或用 headless Chromium 重新輸出）——如需要 PNG 可從此重新輸出 |
| `SSIF_Architecture_caption.txt` | 建議的圖說文字 |

> 高解析度 PNG 輸出檔（`SSIF_Architecture.png`）已從本目錄移除，PDF 與
> HTML 原始檔仍保留。

## 建議放置位置

模型架構與輸入表示法章節（04_），作為主要架構圖——這是投稿就緒版本；除非
需要
以視覺方式（而非文字）呈現損失權重，否則建議優先使用此圖，而非
`fig_ssif_architecture.png`。
