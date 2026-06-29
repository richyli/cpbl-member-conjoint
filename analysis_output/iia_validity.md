# IIA 假設檢驗（Mixed Logit / RPL）

## §1 不採 Hausman-McFadden 之理由
2/3-alternative forced-choice CBC，移除 alternative 重估不可行（Hausman 須 J≥3 且可移除非退化選項）。改採 Train (2003) RPL 路線。

## §2 估計設定
- 全部 16 個 effect-coded 變項設常態隨機係數；none_dummy（None ASC）固定。
- 500 Halton draws，panel = 受訪者，L-BFGS-B。
- 有效樣本 N = 107。

## §3 LR test
- ℓ_MNL = -777.33；ℓ_RPL = -740.74
- LR = 2(ℓ_RPL − ℓ_MNL) = **73.17**，df = 16，**p = 0.0000**
- p < .05 → IIA 違反（存在個體偏好異質性）；**非 fatal**，由 LC-MNL（K≥2）主分析吸收個體層次異質性。

## §4 各 σ_k 顯著性
- 顯著隨機標準差數量：7 / 16
  - sd.price_e1: σ=+1.147, |z|=3.93
  - sd.price_e3: σ=+0.643, |z|=2.89
  - sd.media_e3: σ=+0.545, |z|=2.63
  - sd.ticket_e1: σ=+0.747, |z|=4.31
  - sd.interact_e1: σ=+0.958, |z|=5.26
  - sd.freetix_e1: σ=+0.741, |z|=4.11
  - sd.gift_e1: σ=+0.535, |z|=2.66

## §5 MNL ↔ RPL 同號通過率
- 同號通過：**15/16**（⚠️ 有反號，檢查 specification）

## §6 應對策略
同號未全通過，須檢查模型設定。