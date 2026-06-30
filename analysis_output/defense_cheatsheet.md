# CPBL_MEMBER 分析技術摘要（口試備用）

> 計算邏輯詳見各 wiki note；本文件只列本次執行結果與索引。

| 分析 | 套件 | 本次結果 | 計算詳解 |
|------|------|---------|---------|
| 品質篩除（標準一~三）| pandas, numpy | 篩除 n=6 | [[Pareto Dominance Check conjoint Python]] |
| 品質篩除（標準四 Pareto）| pandas, numpy | strict fail 0；剔除 100%同邊 n=6 | [[Pareto Dominance Check conjoint Python]] |
| CBC 模型（3-alt MNL + None ASC）| scipy | None ASC=-1.065 | [[MNL Python computation]] |
| 屬性編碼 | pandas | effects coding（混合 4/4/3/4/3/4）| [[effects coding conjoint Python]] |
| LC 分群（K-means 行為）| scikit-learn | K=3, Sil=0.252 | [[LC-MNL EM algorithm Python]] |
| LCA 分群（態度）| stepmix | K=3, Entropy=0.995 | [[BIC model selection Python]] |
| Holdout 命中率 | scikit-learn | 57.8% | [[holdout hit rate McFadden Python]] |
| Holdout McFadden R² | — | 0.154 | [[holdout hit rate McFadden Python]] |
| 不回應偏誤（MWU）| scipy | min p=0.006 | [[Mann-Whitney U Python]] |
| 資料飽和曲線 | numpy, matplotlib | 飽和：是 | [[data saturation curve Python]] |
| 折半信度 SB（重要性）| scipy | 0.824 | [[split-half Spearman-Brown Python]] |
| 折半信度 SB（部分效用）| scipy | 0.907 | [[split-half Spearman-Brown Python]] |
| 統計考驗力 Power | scipy | 0.57 | [[Retrodesign power Type S Type M Python]] |
| Type S | scipy | 0.201 | [[Retrodesign power Type S Type M Python]] |
| Type M | scipy | 1.32× | [[Retrodesign power Type S Type M Python]] |
| IIA（RPL LR test）| xlogit, scipy | LR=86.685, p=0.0 | [[Random Parameter Logit xlogit Python]] |
| IIA 同號通過率 | — | 15/16 | [[Random Parameter Logit xlogit Python]] |
| WTP（MRS + Krinsky-Robb）| scipy | β_price=-0.000642, 堆疊=2,985元 | [[Krinsky-Robb WTP CI Python]] |