# 雙軌分群（K-Means 行為 + LCA 態度）

- 有效樣本 N = 74

## K-track（K-Means on conjoint behavior）
- 特徵：['none_rate', 'price_sens', 'win_price', 'win_ticket', 'win_freetix']
- Silhouette 搜尋：K2=0.244, K3=0.235, K4=0.242, K5=0.247, K6=0.242
- 資料驅動最佳 K = 5（sil=0.247）；報告採 **K=3**（一致性+可解釋性）
- K=3：Silhouette=0.235，Davies-Bouldin=1.343

### K=3 行為 profile（特徵均值）
| 群 | n | none_rate | price_sens | win_price | win_ticket | win_freetix |
|---|---|---|---|---|---|---|
| K-0 | 39 | 0.15 | 0.83 | 0.83 | 0.58 | 0.59 |
| K-1 | 28 | 0.03 | 0.44 | 0.44 | 0.59 | 0.54 |
| K-2 | 7 | 0.52 | 0.26 | 0.26 | 0.38 | 0.76 |

## L-track（LCA on 19 Likert items）— stepmix(categorical LCA)
- CAIC 搜尋：K2=4950, K3=5334, K4=5864, K5=6459
- Entropy：K2=1.00, K3=1.00, K4=1.00, K5=1.00
- 資料驅動最佳 K = 2（CAIC argmin）；報告採 **K=3**
- K=3 Entropy = 0.998（門檻 ≥ .80）

### K=3 態度 profile（量表均值 1–7）
| 類別 | n | 球隊認同 | 球迷社群認同 | 知覺價值 |
|---|---|---|---|---|
| L-0 | 26 | 4.60 | 4.68 | 4.87 |
| L-1 | 27 | 5.69 | 5.43 | 5.91 |
| L-2 | 21 | 6.00 | 6.02 | 6.24 |

## 兩軌交叉驗證
- 交叉表（K-track × L-track，N=74）：
```
lca_class    0   1   2
km_cluster            
0           16  13  10
1            9  11   8
2            1   3   3
```
- χ²=2.19, df=4, p=0.701；**Cramér's V = 0.122**
- V < .50 → 雙軌並列（K-Means=行為區隔；LCA=態度潛在類別）

## 好壞判定：兩軌指標皆偏弱 → 區隔結構不穩，論文限制節須說明