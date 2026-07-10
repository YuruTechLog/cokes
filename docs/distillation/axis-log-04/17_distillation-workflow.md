# Distillation Workflow: axis-log-04 / log17

## 基本情報
- DATASET: axis-log-04
- LOG: log17
- RUN_ID: 01

---

## 抽出した意味構造

### 構造1: 3レイヤー設計の詳細
```
Layer1 Skeleton:
  構図・ポーズ・大局的配置
  → ControlNetで物理固定可能

Layer2 Material & Lighting:
  素材感（金属/布/皮膚）・光源方向・影
  → Prompt Schedulingで前半配置

Layer3 Aesthetic Modulation:
  画風・雰囲気・スタイル（アニメ/写真/水彩等）
  → LoRAで後付け / Prompt Schedulingで後半配置
```

### 構造2: 「デッサンしてから色を塗れ」の構造
```
画家の直感: デッサン（構造）→ 色塗り（雰囲気）
AI数理:    前半ステップ（大局）→ 後半ステップ（細部）
Prompt設計: 構造語彙 → 雰囲気語彙
→ 3つが完全に一致 → 「世界初の言語化」として成立
```

### 構造3: Prompt Scheduling実装
```
[デッサン:色塗り:0.4]
→ 全ステップの前40%: 「デッサン」語彙が優先
→ 全ステップの後60%: 「色塗り」語彙が優先
→ 黄金律をコードレベルで実装する構文
```

---

## 再利用単位

- 「3レイヤー設計」: 実践的プロンプト設計フレームワークとして即使用可能
- 「デッサンから色塗り」: 記事タイトル・章見出し・SNSキャッチコピーとして最強候補
- 「Prompt Scheduling構文」: 実装コード付きのHow-to記事として使用可能
