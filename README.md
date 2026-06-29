# 中華職棒球團付費會員方案 — 選擇式聯合分析（CBC）

研究草稿與完整分析輸出，供共同作者協作。

## 內容
- `versions/` — 論文草稿版本目錄，每版同時提供 `.md` 與 `.html`。
  - `v01/` — 研究方法 + 研究發現（2026-06-29）。
- `analysis_output/` — 分析報告（信效度、WTP、分群等）、圖表與 `results.json`（數據真相源）。
- `index.html` — 線上導覽頁（GitHub Pages）。

## 研究摘要
- 設計：6 屬性（年度會員費／獨家媒體內容／優先購票順位／互動活動／免費票券／會員周邊）× 各 3–4 水準；8 輪對比 + trap + 鏡像重複。
- 樣本：初始 N=84，品質四標準篩除後有效 **N=74**。
- 模型：3 替代方案（A/B/皆不選）條件羅吉特 + None ASC（McFadden, 1974），效果編碼；WTP 以 Krinsky-Robb CI。
- 分群：K-means（行為）+ LCA（態度）雙軌並列。
- 主結果：價格為最關鍵屬性（重要性 35.3%），其次媒體內容（18.2%）與互動活動（17.0%）。

## 線上閱讀
啟用 GitHub Pages 後，造訪 `https://richyli.github.io/cpbl-member-conjoint/`。

---
🤖 分析與草稿由 Claude Code 協助產生（方法以 Python + pandas/numpy/scipy/statsmodels/xlogit 實作）。
