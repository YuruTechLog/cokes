# Chat Summary — axis-log-04 / log17

## 概要
axis-log-04最重要言語化：「デッサンしてから色を塗れ」の世界初言語化確定。3レイヤー設計図（Skeleton/Material/Aesthetic）の確立。Prompt Scheduling構文の確認。

## 意思決定ログ（時系列）

### 1. 3レイヤー設計図の確立
- Layer1 Skeleton: 骨格・構図・ポーズ（ControlNetで固定可能）
- Layer2 Material & Lighting: 素材感・光源（前半ステップで配置）
- Layer3 Aesthetic Modulation: 画風・雰囲気（LoRAで後付け可能）

### 2. 「デッサンしてから色を塗れ」確定
- 画家の直感（デッサン→色塗り）
- AI数理（前半ステップ→後半ステップ）
- Prompt設計（構造語彙→雰囲気語彙）
- 3つが完全一致 → 「世界初の言語化」確定

### 3. Prompt Scheduling構文確認
- `[A:B:0.4]`: 前40%でA（構造）、後60%でB（雰囲気）
- Automatic1111 Wikiで確認

### 4. ControlNetの役割確認
- 骨組み線画で構図を物理固定 → 「デッサン固定」の実装

## 確定判断

| 判断 | 内容 |
|------|------|
| **世界初言語化** | 「デッサンしてから色を塗れ」= 黄金律の最短表現 |
| 3レイヤー設計 | Skeleton→Material→Aesthetic の順序で確定 |
| Prompt Scheduling | `[A:B:0.4]`構文で実装可能 |
