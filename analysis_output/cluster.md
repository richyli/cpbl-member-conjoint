# 雙軌分群（K-Means 行為 + LCA 態度）

- 有效樣本 N = 97

## K-track（K-Means on conjoint behavior）
- 特徵：['none_rate', 'price_sens', 'win_price', 'win_ticket', 'win_freetix']
- Silhouette 搜尋：K2=0.247, K3=0.223, K4=0.233, K5=0.217, K6=0.216
- 資料驅動最佳 K = 2（sil=0.247）；報告採 **K=3**（一致性+可解釋性）
- K=3：Silhouette=0.223，Davies-Bouldin=1.424

### K=3 行為 profile（特徵均值）
| 群 | n | none_rate | price_sens | win_price | win_ticket | win_freetix |
|---|---|---|---|---|---|---|
| K-0 | 28 | 0.25 | 0.89 | 0.89 | 0.56 | 0.77 |
| K-1 | 51 | 0.04 | 0.61 | 0.61 | 0.64 | 0.46 |
| K-2 | 18 | 0.23 | 0.27 | 0.27 | 0.50 | 0.79 |

## L-track（LCA on 19 Likert items）— stepmix(categorical LCA)
- CAIC 搜尋：K2=6326, K3=6713, K4=7177, K5=7771
- Entropy：K2=0.99, K3=1.00, K4=0.99, K5=1.00
- 資料驅動最佳 K = 2（CAIC argmin）；報告採 **K=3**
- K=3 Entropy = 0.997（門檻 ≥ .80）

### K=3 態度 profile（量表均值 1–7）
| 類別 | n | 球隊認同 | 球迷社群認同 | 知覺價值 |
|---|---|---|---|---|
| L-0 | 39 | 5.55 | 5.40 | 5.88 |
| L-1 | 30 | 4.49 | 4.55 | 4.72 |
| L-2 | 28 | 6.09 | 6.12 | 6.38 |

## 兩軌交叉驗證
- 交叉表（K-track × L-track，N=97）：
```
lca_class    0   1   2
km_cluster            
0           14   9   5
1           16  19  16
2            9   2   7
```
- χ²=6.96, df=4, p=0.138；**Cramér's V = 0.189**
- V < .50 → 雙軌並列（K-Means=行為區隔；LCA=態度潛在類別）

## 好壞判定：兩軌指標皆偏弱 → 區隔結構不穩，論文限制節須說明