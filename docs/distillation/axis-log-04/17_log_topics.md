# Log Topics: axis-log-04 / log17

## 基本情報
- DATASET: axis-log-04
- LOG: log17
- RUN_ID: 01

---

## 主要トピック

### T01 | 3レイヤー設計図の確立
画像生成プロンプトの3レイヤー設計：
- Layer1: Skeleton（骨格・構図・ポーズ）
- Layer2: Material & Lighting（素材・光源）
- Layer3: Aesthetic Modulation（雰囲気・画風・スタイル）

### T02 | 「デッサンしてから色を塗れ」= 世界初言語化確定
「構造が先、雰囲気は最後」の黄金律を「デッサンしてから色を塗る」という一文で言語化。「世界初の言語化」確定（画家の直感 = AI数理プロセスの一致を最短で表現）。

### T03 | Prompt Scheduling構文
`[A:B:0.4]` 構文：前半40%でA（構造）、後半60%でB（雰囲気）を適用。Automatic1111 Wiki確認。Cross Attention Controlとの関係。

### T04 | ControlNetの役割
骨組み線画で構図を物理的に固定する機能。「構図を決めてから色を塗る」を実装レベルで実現。

---

## 議論の転換点

- 「デッサンしてから色を塗れ」一文の確定 = axis-log-04の最重要成果の一つ

---

## キーワード
3レイヤー設計・Skeleton/Material/Aesthetic・デッサン色塗り世界初言語化・Prompt Scheduling・ControlNet
