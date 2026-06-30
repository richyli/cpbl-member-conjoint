# 雙軌分群（K-Means 行為 + LCA 態度）

- 有效樣本 N = 115

## K-track（K-Means on conjoint behavior）
- 特徵：['none_rate', 'price_sens', 'win_price', 'win_ticket', 'win_freetix']
- Silhouette 搜尋：K2=0.246, K3=0.252, K4=0.215, K5=0.231, K6=0.237
- 資料驅動最佳 K = 3（sil=0.252）；報告採 **K=3**（一致性+可解釋性）
- K=3：Silhouette=0.252，Davies-Bouldin=1.343

### K=3 行為 profile（特徵均值）
| 群 | n | none_rate | price_sens | win_price | win_ticket | win_freetix |
|---|---|---|---|---|---|---|
| K-0 | 62 | 0.05 | 0.71 | 0.71 | 0.61 | 0.51 |
| K-1 | 32 | 0.12 | 0.31 | 0.31 | 0.63 | 0.73 |
| K-2 | 21 | 0.44 | 0.93 | 0.93 | 0.56 | 0.82 |

## L-track（LCA on 19 Likert items）— stepmix(categorical LCA)
- CAIC 搜尋：K2=7325, K3=7672, K4=8097, K5=8755
- Entropy：K2=0.99, K3=0.99, K4=1.00, K5=0.99
- 資料驅動最佳 K = 2（CAIC argmin）；報告採 **K=3**
- K=3 Entropy = 0.995（門檻 ≥ .80）

### K=3 態度 profile（量表均值 1–7）
| 類別 | n | 球隊認同 | 球迷社群認同 | 知覺價值 |
|---|---|---|---|---|
| L-0 | 37 | 4.55 | 4.47 | 4.83 |
| L-1 | 31 | 6.05 | 6.21 | 6.38 |
| L-2 | 47 | 5.71 | 5.60 | 5.96 |

## 兩軌交叉驗證
- 交叉表（K-track × L-track，N=115）：
```
lca_class    0   1   2
km_cluster            
0           21  13  28
1            8  12  12
2            8   6   7
```
- χ²=3.62, df=4, p=0.460；**Cramér's V = 0.125**
- V < .50 → 雙軌並列（K-Means=行為區隔；LCA=態度潛在類別）

## 好壞判定：兩軌指標皆偏弱 → 區隔結構不穩，論文限制節須說明