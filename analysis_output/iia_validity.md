# IIA 假設檢驗（Mixed Logit / RPL）

## §1 不採 Hausman-McFadden 之理由
2/3-alternative forced-choice CBC，移除 alternative 重估不可行（Hausman 須 J≥3 且可移除非退化選項）。改採 Train (2003) RPL 路線。

## §2 估計設定
- 全部 16 個 effect-coded 變項設常態隨機係數；none_dummy（None ASC）固定。
- 500 Halton draws，panel = 受訪者，L-BFGS-B。
- 有效樣本 N = 74。

## §3 LR test
- ℓ_MNL = -541.08；ℓ_RPL = -518.75
- LR = 2(ℓ_RPL − ℓ_MNL) = **44.65**，df = 16，**p = 0.0002**
- p < .05 → IIA 違反（存在個體偏好異質性）；**非 fatal**，由 LC-MNL（K≥2）主分析吸收個體層次異質性。

## §4 各 σ_k 顯著性
- 顯著隨機標準差數量：6 / 16
  - sd.price_e1: σ=+1.278, |z|=3.81
  - sd.price_e2: σ=+0.595, |z|=2.17
  - sd.price_e3: σ=+0.758, |z|=3.00
  - sd.interact_e1: σ=+0.898, |z|=3.84
  - sd.freetix_e1: σ=+0.689, |z|=3.45
  - sd.gift_e1: σ=+0.656, |z|=2.80

## §5 MNL ↔ RPL 同號通過率
- 同號通過：**16/16**（全通過 → 方向穩健）

## §6 應對策略
IIA 違反但已有 LC-MNL 主分析吸收異質性，且 MNL↔RPL 同號全通過 → 主分析方向穩健。