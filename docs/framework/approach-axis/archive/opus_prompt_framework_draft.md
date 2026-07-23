# Opus分析プロンプト: Approach Axis Framework 章立て・骨子ドラフト生成

## 目的

axis-log-01〜03の蒸留知識を統合し、**Approach Axis Frameworkの実装ドキュメント**として機能する
章立て・骨子のドラフトを生成する。

---

## あなたへの指示

以下の「参照素材」を読んで、Approach Axis Frameworkの**章立てと骨子**を生成してほしい。

### 成果物の要件

1. **対象読者**: 実装者（AIプロンプト設計・システム設計の実務担当者）
2. **目的**: フレームワークを理解して実際に使えるようになること
3. **形式**: 章立て（H1/H2/H3レベル） + 各章の骨子（何を書くか・なぜその章が必要か）
4. **分量**: 章立てのみ。本文は書かない。骨子は各章2〜5行。

### 制約

- 参照素材に記載のない内容を追加しない（推測・補完禁止）
- 参照素材の確定判断・定義・モデル名称は正確に使う
- 著者の表現・命名（Approach Axis / Axis Words / 重力場テンソルモデル等）を変えない
- 「学術的に厳密に」はしない。実務で使える構造を優先
- 未解決議題（参照素材で「要継続」とされている事項）は未解決として明示する

---

## 参照素材

### 【Primary】axis-log-01 知識群

#### 1. Approach Axis Framework 定義（`docs/knowledge/axis-log-01/approach-axis-framework.md`）

```
[以下のファイルを全文読み込む]
docs/knowledge/axis-log-01/approach-axis-framework.md
```

**含む情報:**
- Approach Axisの定義・起源
- 4層構造（Axis Words / Magnet Map / Model Profile / Templates）
- 操作プリミティブ7種（Position / Magnitude / Constraint / Filter / Blend / Retry / Lock）
- 状態モデル（Idle → Plan → Execute → Evaluate）
- 評価指標（品質スコア / 信頼度 / 判定ラベル）
- 実行フロー
- 運用カード・Handoffテンプレート・失敗モード対処

#### 2. 軸語彙・磁力マップ（`docs/knowledge/axis-log-01/axis-words-magnet-map.md`）

```
[以下のファイルを全文読み込む]
docs/knowledge/axis-log-01/axis-words-magnet-map.md
```

**含む情報:**
- 軸語彙5分類（起点/抽象度/境界/優先順位/方向性）+ 補助（順序）
- 磁力強度マップ（全モデル共通傾向）
- モデル別磁力特性テーブル（Claude / GPT / Gemini / Copilot）

#### 3. 重力場テンソルモデル（`docs/knowledge/axis-log-01/gravity-tensor-model.md`）

```
[以下のファイルを全文読み込む]
docs/knowledge/axis-log-01/gravity-tensor-model.md
```

**含む情報:**
- 第一原理（AIは高次元ベクトル空間）
- 人間/AIの軸生成能力差
- 重力場テンソルモデル3要素（多様体 / 傾斜装置 / 地形崩壊）
- モデル別崩壊特性
- セメントスランプ比喩・子供/大人目線比喩

---

### 【Secondary】axis-log-02 知識群（axis-log-01より後の議論。発展・精緻化）

#### 4. axis-log-02 統合知識（`docs/knowledge/axis-log-02/integrated_knowledge.md`）

```
[以下のファイルを全文読み込む]
docs/knowledge/axis-log-02/integrated_knowledge.md
```

**含む情報（axis-log-01からの発展）:**
- 比喩の主体問題（「誰が操作するか」が比喩設計の先決）
- 形式化の価値（「発見」ではなく「形式化」が独自性）
- ゆるてく語の統合定義（構造保持+一般化翻訳装置）
- Axis三層構造最終版（操作/説明/思想）
- Executor×Advisor協調構造
- 2種類の抽象能力（実務抽象 vs 数理抽象）

---

### 【Tertiary】axis-log-03 知識群（Cokesとの関係・思想面）

#### 5. axis-log-03 統合知識（`docs/knowledge/axis-log-03/integrated_knowledge.md`）

**含む情報（Cokes体系内でのAxisの位置づけ）:**
- Axis = 意味空間歪曲装置（ワープモデル確定）
- 重力場テンソルモデル基本構造（再確認・精緻化）
- Cokes/Axisの責任分担
- Handoff = 分岐点（終点ではない）
- 外部ツール前Axis語彙必須ルール（運用ルール）
- AI自身によるフレームワーク誤認のリスク

---

### 【参照判断ルール】粒度が荒い場合の追加参照

knowledgeファイルで内容が薄い・断片的と判断した場合、以下を追加参照してよい:

**distillationファイル（テーマ別詳細）:**
- `docs/distillation/axis-log-01/01_distillation-workflow.md`
- `docs/distillation/axis-log-02/` 配下の該当テーマの `*_distillation-workflow.md`
- `docs/distillation/axis-log-03/` 配下の該当テーマの `*_distillation-workflow.md`

**chat-summaryファイル（意思決定の流れ）:**
- `docs/chat-summary/axis-log-01_01/` 配下
- `docs/chat-summary/axis-log-02_log*/summary.md` 配下
- `docs/chat-summary/axis-log-03_log*/summary.md` 配下

**追加参照の判断基準:**
- 「なぜこの設計になったか」の経緯が必要な場合 → chat-summaryを参照
- テーマの具体的な議論内容が必要な場合 → distillationを参照
- chat-archives（`docs/chat-archives/`）は参照禁止（未加工の生ログ）

---

## 出力形式

```markdown
# Approach Axis Framework — 章立て・骨子ドラフト

## 生成メモ（Opusによる設計判断）
- 章立ての根拠（なぜこの構成にしたか）
- 判断が難しかった箇所
- 未解決議題の扱い方

---

## 章立て・骨子

### 第N章: [章タイトル]
**目的:** [この章で読者が得るもの]
**骨子:**
- [書く内容1]
- [書く内容2]
- ...
**参照素材:** [使った参照元ファイル名]

（以下繰り返し）

---

## 未解決議題（本文に含めない・別途確認が必要）
- [事項1]: [どのログで未解決として記録されているか]
- ...
```

---

## 補足: 既存ドキュメントの位置づけ

axis-log-01の `approach-axis-framework.md` は「技術仕様書」として機能している。
今回の章立てドラフトは「実装者向け入門〜実践ドキュメント」として、
仕様書の内容を前提として読めるものを想定する。

重複は避けず、「使い方の文脈」を加えることを優先する。
