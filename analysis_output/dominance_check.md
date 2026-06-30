# Pareto Dominance Check（標準四）

> 定義：採 **global Pareto dominance**——被支配卡須在 price/ticket/freetix 三個方向性屬性上全部不優於對方、至少一項嚴格較差，**且** media/interact/gift 三個 categorical 屬性兩卡完全相同（否則視為 categorical trade-off，非真正支配）。
> 此保守定義避免把「以價格/順位/票券換取偏好的內容、互動或贈品」的理性受訪者誤判為非交易者。
> （webform 自帶的 anti-dominance guard 以「全部非 media 屬性」判定，含 categorical，導致 ~49% 的 A/B pair 在三個方向性屬性上呈支配——故事後須以此較嚴格定義重判。）

- 受訪者數：127
- strict dominance fail（任一題選被支配方）：**0** 人
- near-dominance fail：0 人
- 100% 同一邊（strict non-trader）+ strict fail 雙失格 → 整人剔除：**6** 人 [29, 36, 45, 64, 75, 101]
- strict fail 但其他指標正常 → 標記待審（保留）：0 人 []

## Robustness：含/不含標記者 AMCE（part-worth range）差異
| 屬性 | 差異 % |
|------|-------:|
| 年度會員費 | 8.9% |
| 獨家媒體內容 | 9.6% |
| 優先購票順位 | 13.5% |
| 互動活動 | 12.9% |
| 免費票券 | 4.3% |
| 會員周邊 | 6.5% |

- 最大差異：**13.5%** → 主表選擇：**並陳兩套（10–20%）**

（global Pareto 定義下無 strict/near dominance fail task，故無逐題明細。）