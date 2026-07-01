# 雙軌分群（K-Means 行為 + LCA 態度）

- 有效樣本 N = 139

## K-track（K-Means on conjoint behavior）
- 特徵：['none_rate', 'price_sens', 'win_price', 'win_ticket', 'win_freetix']
- Silhouette 搜尋：K2=0.246, K3=0.251, K4=0.222, K5=0.221, K6=0.230
- 資料驅動最佳 K = 3（sil=0.251）；報告採 **K=3**（一致性+可解釋性）
- K=3：Silhouette=0.251，Davies-Bouldin=1.370

### K=3 行為 profile（特徵均值）
| 群 | n | none_rate | price_sens | win_price | win_ticket | win_freetix |
|---|---|---|---|---|---|---|
| K-0 | 74 | 0.05 | 0.72 | 0.72 | 0.61 | 0.51 |
| K-1 | 37 | 0.12 | 0.29 | 0.29 | 0.64 | 0.73 |
| K-2 | 28 | 0.40 | 0.90 | 0.90 | 0.50 | 0.82 |

## L-track（LCA on 19 Likert items）— stepmix(categorical LCA)
- CAIC 搜尋：K2=8698, K3=9024, K4=9507, K5=10130
- Entropy：K2=0.98, K3=0.99, K4=0.99, K5=0.99
- 資料驅動最佳 K = 2（CAIC argmin）；報告採 **K=3**
- K=3 Entropy = 0.987（門檻 ≥ .80）

### K=3 態度 profile（量表均值 1–7）
| 類別 | n | 球隊認同 | 球迷社群認同 | 知覺價值 |
|---|---|---|---|---|
| L-0 | 62 | 5.62 | 5.48 | 5.91 |
| L-1 | 41 | 4.31 | 4.35 | 4.73 |
| L-2 | 36 | 6.17 | 6.36 | 6.51 |

## 兩軌交叉驗證
- 交叉表（K-track × L-track，N=139）：
```
lca_class    0   1   2
km_cluster            
0           37  23  14
1           14   7  16
2           11  11   6
```
- χ²=9.32, df=4, p=0.054；**Cramér's V = 0.183**
- V < .50 → 雙軌並列（K-Means=行為區隔；LCA=態度潛在類別）

## 好壞判定：兩軌指標皆偏弱 → 區隔結構不穩，論文限制節須說明