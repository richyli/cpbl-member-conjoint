# 雙軌分群（K-Means 行為 + LCA 態度）

- 有效樣本 N = 107

## K-track（K-Means on conjoint behavior）
- 特徵：['none_rate', 'price_sens', 'win_price', 'win_ticket', 'win_freetix']
- Silhouette 搜尋：K2=0.251, K3=0.240, K4=0.236, K5=0.230, K6=0.236
- 資料驅動最佳 K = 2（sil=0.251）；報告採 **K=3**（一致性+可解釋性）
- K=3：Silhouette=0.240，Davies-Bouldin=1.374

### K=3 行為 profile（特徵均值）
| 群 | n | none_rate | price_sens | win_price | win_ticket | win_freetix |
|---|---|---|---|---|---|---|
| K-0 | 31 | 0.12 | 0.32 | 0.32 | 0.61 | 0.73 |
| K-1 | 57 | 0.05 | 0.71 | 0.71 | 0.60 | 0.51 |
| K-2 | 19 | 0.43 | 0.92 | 0.92 | 0.54 | 0.81 |

## L-track（LCA on 19 Likert items）— stepmix(categorical LCA)
- CAIC 搜尋：K2=6912, K3=7264, K4=7746, K5=8314
- Entropy：K2=0.98, K3=1.00, K4=0.99, K5=1.00
- 資料驅動最佳 K = 2（CAIC argmin）；報告採 **K=3**
- K=3 Entropy = 0.996（門檻 ≥ .80）

### K=3 態度 profile（量表均值 1–7）
| 類別 | n | 球隊認同 | 球迷社群認同 | 知覺價值 |
|---|---|---|---|---|
| L-0 | 33 | 5.96 | 6.01 | 6.20 |
| L-1 | 35 | 4.47 | 4.59 | 4.91 |
| L-2 | 39 | 5.75 | 5.51 | 5.95 |

## 兩軌交叉驗證
- 交叉表（K-track × L-track，N=107）：
```
lca_class    0   1   2
km_cluster            
0           13   7  11
1           13  22  22
2            7   6   6
```
- χ²=4.44, df=4, p=0.350；**Cramér's V = 0.144**
- V < .50 → 雙軌並列（K-Means=行為區隔；LCA=態度潛在類別）

## 好壞判定：兩軌指標皆偏弱 → 區隔結構不穩，論文限制節須說明