# Integrated Distillation Summary — axis-log-02

## データセット情報

- DATASET: axis-log-02
- 処理ログ: log01〜log11
- RUN_ID: 01
- 生成日: 2026-07-09

---

## 全ログ トピック統計

| ログ | 主要トピック数 | インシデント数 |
|-----|-------------|-------------|
| log01 | 7 | 3 |
| log02 | 5 | 3 |
| log03 | 5 | 2 |
| log04 | 5 | 2 |
| log05 | 5 | 2 |
| log06 | 5 | 2 |
| log07 | 5 | 2 |
| log08 | 5 | 2 |
| log09 | 5 | 2 |
| log10 | 5 | 2 |
| log11 | 7 | 2 |
| **合計** | **59** | **24** |

---

## 核心テーマ（全ログ横断）

### T-CORE-01: 比喩の変遷史
固体→自転車→流体→媒質→水槽→海（11本を通じた進化）

### T-CORE-02: Axis形式化の価値
研究者暗黙知 → 形式化 → 誰でも再現可能

### T-CORE-03: ゆるてく語の機能
深海語 ↔ 表層語の翻訳（構造保持+軽さ）

### T-CORE-04: Executor×Advisor構造
非対称協調（常時稼働 × オンデマンド）

### T-CORE-05: 人間固有能力の輪郭
断片→感情ベクトル→先読みはAI困難領域

### T-CORE-06: 整理屋・翻訳者としての自己定義
「世界再構築」ではなく「すでにある構造の形式化」

---

## 横断インシデントパターン

1. 比喩の主体設定ミス（log01: 自転車 / 共通リスク）
2. 正確さ vs アクセシビリティのトレードオフ（log02）
3. スケールアップによる性質変化（log03）
4. 定義の揺れ（log11: ゆるてく語 2表現）

---

## 出力ファイル一覧

### distillation/axis-log-02/

| ファイル | 内容 |
|---------|------|
| 01_log_topics.md〜11_log_topics.md | 各ログのトピック抽出 |
| 01_incident.md〜11_incident.md | 各ログのインシデント記録 |
| 01_distillation-workflow.md〜11_distillation-workflow.md | 各ログの処理フロー |
| integrated_distillation_summary.md | 本ファイル |

### chat-summary/axis-log-02_logXX/

| ディレクトリ | 内容 |
|-----------|------|
| axis-log-02_log01〜log11/summary.md | 各ログの意思決定履歴 |

### knowledge/axis-log-02/

| パス | 内容 |
|-----|------|
| log01〜log11/knowledge.md | 各ログの再利用知識（KN01〜KN45） |
| integrated_knowledge.md | 横断統合知識・核心知識インデックス |
