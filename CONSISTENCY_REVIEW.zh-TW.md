# 論文內容一致性審閱（中文版）

逐一檢查全部 10 個投稿檔案（`01_` 至 `10_`）中彼此對不上的數字／論述，
以及文字表達不清楚之處。以下依嚴重程度排序，每項都附上確切句子與
互相矛盾的數值，方便獨立核對。

## 高優先 — 數字或事實錯誤

### 1. 摘要的精確率下限與 Results 章節矛盾

- **摘要**（`01_submit_abstract.md`）：「SSIF achieved precision **≥ 0.93**
  and probability of detection (POD) rising from 0.257 at the 10-second
  window...」
- **Results — 測站層級警報與震度分類預測**（`07_submit_Results.md`）：
  「all windows maintain precision between **0.922**（15-second window，
  最低）and 0.985（25-second window，最高）。」

同一句摘要引用的 POD 數字（0.257 → 0.907）與測站層級（station-level）
的數字完全吻合，代表這句話講的就是測站層級的精確率——但其實際下限是
0.922，不是 0.93。**0.922 四捨五入應為 0.92，而非 0.93。** 這是整篇
論文中最顯眼的數字（因為它在摘要裡），卻與內文對不上。建議將摘要改為
「≥ 0.92"（或精確寫「≥ 0.922"），或說明是否指的是別的數值。

### 2. Data 章節的驗證集細分人數加總不對

**`06_submit_Data.md`**，「資料切分與模型選擇流程」：

> 「...validation（147 events, ≈15%)...」
>
> 「...The validation subset (**73** events)... the calibration subset
> (**36** events)... An internal test subset (**36** events)...」

73 + 36 + 36 = **145**，不是 147。驗證集有 2 個事件對不上。可能是三個
子集人數各差一點（例如 74+36+37、73+37+37 等多種組合都能湊到 147），
或者是驗證集總數 147 本身需要修正。

### 3. 案例研究的百分比與其自身的分子/分母不符

**`08_submit_case_study_hualien_m72.md`**：「The CWA network recorded
526 station–event records for this earthquake, of which **515 stations
(97.8%)** experienced a final peak intensity of CWA class ≥4.」

515 ÷ 526 = 0.9791 → **97.9%**，不是 97.8%。差了一個四捨五入位階。

### 4. Method 章節的前向引用在最近一次拆章後已過時

**`03_submit_Method.md`**：「...while SSIF is limited by the amount of
seismic information that has reached the station by the prediction
time. **The full architecture, training procedure, and evaluation
framework are described in the following chapter, Model Architecture
and Input Representation.**」

這句話在「模型架構」與「多任務最佳化與評估框架」還是同一章時是對的。
後來這兩者被拆成兩個獨立章節（`04_` 與 `05_`），`04_` 現在只涵蓋架構
本身——訓練與評估的內容已經移到 `05_`。但 `03_` 這句話仍宣稱「接下來
的（單一）章節」涵蓋全部三項內容。需要改成「接下來的兩個章節」（或
同時點名 `04_` 與 `05_`）。

*（這是本次對話中最近一次「拆章」請求留下的遺漏——助理當時更新了
`04_` 結尾指向 `05_` 的前向引用，卻漏掉了 `03_` 中原本指向拆分前
`04_` 的那一句。）*

### 5. Results 宣稱 SSIF「與 eBEAR 的 POD 相同」，但同一段內容其實顯示並非如此

**`07_submit_Results.md`**，「區域式偵測與 eBEAR 互補性」：「SSIF at the
20-second window **matches** eBEAR's POD while exceeding it in
precision...」

同一段前兩句已經指出：SSIF 在 20 秒時窗的 POD 是 1.000（39 個區域正例
事件全數偵測到），eBEAR 則固定在 0.949——緊接著下一句又說「eBEAR misses
2 region-positive events, SSIF misses none」，這只有在 SSIF 的 POD
**高於**、而非等於 eBEAR 時才成立。「matches」應改為「exceeds」或
「surpasses」。

## 中優先 — 文字表達不清楚或未定義

### 6. 「ST − OT」從未被定義

**`08_submit_case_study_hualien_m72.md`**：「The operational eBEAR
system issued its first alert 9.4 seconds after origin time
(**ST − OT** = 9.44 s)...」`ST` 與 `OT`（推測是 Solution/System Time
與 Origin Time）在全部 10 個檔案中都沒有明確定義過。建議在第一次出現
時完整拼出全名。

### 7. 同一事件的地震規模類型標示不一致

**`02_submit_Introduction.md`** 稱該事件為「the 2024 **ML** 7.2 Hualien
earthquake」（局部地震規模），但其他所有章節（`06_`、`07_`、`08_`）
都只稱「**M**7.2」，未註明規模類型。文中無法判斷這兩者是否為同一個
數值只是命名慣例不同，還是 ML 是即時初估值、後來被修正為其他規模系統
的最終值。建議在規模類型第一次出現時，補上一句簡短說明釐清。

### 8. Discussion 中 20 秒時窗的測站層級 POD 數字在 Results 中找不到依據

**`09_submit_Discussion.md`**：「At this window, station-level POD
reaches **0.512**...」——Results（`07_`）正文只給出兩個端點值（10 秒
0.257、40 秒 0.907），全部 10 個檔案中都沒有逐時窗的測站層級 POD 表格
可供核對 0.512 這個數字（相較之下，花蓮案例研究就有完整的逐時窗表格）。
不代表這個數字是錯的，但讀者無法單從文字自行驗證。

### 9. Generalization 段落中的「最大差距」未指明是哪個時窗

**`07_submit_Results.md`**，「Generalization」：「The training–testing F1
gap is largest at early windows (**−0.077** at 10 seconds)... A maximum
gap of **7.8 percentage points** is modest...」0.077 是 7.7 個百分點，
不是 7.8——差距很小、讀起來像打字誤差，但文中始終沒有明確指出 7.8pp
這個最大值究竟出現在哪個時窗（10 秒只是被當作「早期時窗」的代表例子，
並未明確說是最大值本身）。建議註明 7.8pp 實際發生的時窗，或將 7.8
修正為 7.7。

## 較低優先 — 結構性缺口

### 10. 沒有「參考文獻」章節

10 個檔案中以作者—年份格式引用了約 17 篇文獻（Hoshiba and Aoki, 2015;
Jozinović et al., 2020; Li et al., 2018; Mousavi and Beroza, 2020;
Wang et al., 2022; Huang et al., 2025; Baevski et al., 2020; Allen et
al., 2009; Allen and Melgar, 2019; Zhang et al., 2021; Colombelli et
al., 2012; Lara et al., 2023; Lin et al., 2021; Hoshiba et al., 2011;
Kodera et al., 2021; Song et al., 2025; Kodera et al., 2018），但沒有
`11_submit_References.md` 或同等章節。目前每一筆文中引用都對應不到
完整書目資訊。

## 已在別處追蹤的問題（屬於圖片層級，非文字層級）

以下是先前圖片審閱時發現的問題（詳見 [`figures/README.md`](figures/README.md)），
這裡不重複推導，但仍與整體投稿一致性有關，建議與上述項目一併處理：

- `fig_detection_categories.png` 與 `fig_alert_timeline.png` 使用的
  n=44 事件群組，與正文全程使用的 n=50（39 區域正例）群組對不上。
- `fig_case_study_hualien_m72.png` 面板 (b) 有一個未標示說明的空心
  菱形標記。
- `fig_alert_timeline.png` 中花蓮事件的 eBEAR 延遲（約 26 秒）與
  `08_submit_case_study_hualien_m72.md` 文中所述的 9.4 秒首次警報時間
  不一致。

## 建議下一步

依優先順序：

1. **修正上述五項高優先問題**——這些是仔細的審稿人或共同作者會立刻
   發現的（尤其是第 1 項，因為它就在摘要裡）。第 1–3 項需要回頭核對
   原始分析結果才能確定正確數字，不只是改文字；第 4、5 項則是純文字
   修正。
2. **補上兩項中優先的定義缺口**（第 6、7 項）——各加一句簡短說明即可，
   成本低，但能消除審稿人的困惑。
3. **考慮在 `07_submit_Results.md` 加入逐時窗的測站層級 POD 表格**
   （對應第 8 項）——花蓮案例研究已經示範過這種 Window/TP/FP/FN/POD
   表格的做法；若 Results 也有對應的整體版本，Discussion 與
   Conclusions 中引用的每個逐時窗數字都能被獨立核對。
4. **在真正投稿前補上「參考文獻」章節**（對應第 10 項）——可保留
   `11_submit_References.md` 這個檔名，待內容補齊後同步更新兩份
   README 的章節表。
5. **一併處理 [`figures/USAGE_AND_NEXT_STEPS.md`](figures/USAGE_AND_NEXT_STEPS.md)
   中追蹤的圖片層級問題**——其中幾項（n=44 群組、eBEAR 時間點不一致）
   牽涉到與上述第 1–5 項相同的底層數字，建議一次性重新執行原始分析
   程式，同步修正文字、表格與圖片，而非分開個別修補。
6. **修正完成後再完整檢查一輪**——部分修正（尤其是第 1、2 項）可能會
   牽動其他目前「看似一致」但實際上是源自同一組（可能有誤的）原始
   數值所推導出的數字。

> English version: [CONSISTENCY_REVIEW.md](CONSISTENCY_REVIEW.md)
