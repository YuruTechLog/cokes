# Approach Axis Framework

Approach Axis の実装ドキュメントです。本文1〜10章はレビューを経て直下へ昇格済みです。
Cokes側の定義承認と、外部公開前の最終レビューは別タスクとして残します。

**現在の状態:** プロローグと第1〜10章の本文はレビュー済み・昇格済み。Cokes正本との整合、用語候補の判断、外部公開前の最終確認を行います。

## まず読む順番

1. [framework.md](framework.md) — 章構成、未解決議題、参照資料
2. [glossary.md](glossary.md) — 用語の正本。本文を書く・レビューする前に参照する
3. [prologue.md](prologue.md) と [ch01.md](ch01.md) — 導入部本文
4. [ch02.md](ch02.md) と [references/terrain-magnetic-model.md](references/terrain-magnetic-model.md) — 第2章本文と説明モデル詳細

## このディレクトリの位置づけ

```text
chat-archives（生ログ）
  → distillation（テーマ抽出）
  → knowledge（再利用可能な知識ユニット）
  → framework（知識を統合した実装ドキュメント） ← ここ
```

| 区分 | 役割 | 主なファイル |
|---|---|---|
| 本文・正本候補 | レビュー済みの本文・定義 | `framework.md` / `glossary.md` / `prologue.md` / `ch01.md`〜`ch10.md` |
| レビュー保留 | 判断待ちの用語候補 | `review/glossary_candidates.md` |
| 補助資料 | 本文の根拠・説明補助 | `references/terrain-magnetic-model.md` / `references/model_comparison_axis.md` / `references/metaphor_catalog.md` |
| 運用知見 | 事故の事実と、そこから抽出したルール | `incidents/` / `lessons/` |
| 作業履歴・終結記録 | 過去の作業手順、終了した設計・用語検討 | [archive/README.md](archive/README.md) / [sonnet_work_procedure.md](archive/sonnet_work_procedure.md) / [opus_prompt_framework_draft.md](archive/opus_prompt_framework_draft.md) / [knowledge-organization-engineering-closure.md](archive/knowledge-organization-engineering-closure.md) |

## 現在の執筆状況

| 範囲 | 現在の主ファイル | 状態 | 次の扱い |
|---|---|---|---|
| プロローグ | [prologue.md](prologue.md) | 承認・昇格済み | 外部公開前に最終レビュー |
| 第1章 | [ch01.md](ch01.md) | 承認・昇格済み | 外部公開前に最終レビュー |
| 第2章 | [ch02.md](ch02.md) | 承認・昇格済み | 外部公開前に最終レビュー |
| 第3章 | [ch03.md](ch03.md) | 承認・昇格済み | 外部公開前に最終レビュー |
| 第4章 | [ch04.md](ch04.md) | 承認・昇格済み | 外部公開前に最終レビュー |
| 第5章 | [ch05.md](ch05.md) | 承認・昇格済み | 用語候補は別管理 |
| 第6章 | [ch06.md](ch06.md) | 承認・昇格済み | 実装化は別タスク |
| 第7章 | [ch07.md](ch07.md) | 承認・昇格済み | Handoff定義の正本 |
| 第8章 | [ch08.md](ch08.md) | 承認・昇格済み | 第7章を参照 |
| 第9章 | [ch09.md](ch09.md) | 承認・昇格済み | Cokes定義TODOは別管理 |
| 第10章 | [ch10.md](ch10.md) | 承認・昇格済み | 実務テンプレート |
| 用語 | [glossary.md](glossary.md) | 作成済み | 本文と照合して継続更新 |
| インシデント・教訓 | [incidents/](incidents/README.md) / [lessons/](lessons/README.md) | 継続記録 | 事実と運用ルールを分けて追記 |

骨子・旧版・比較用ドラフトは [archive/drafts/](archive/drafts/) に保存しています。新規編集は、上表の本文ファイルを起点にしてください。

## 整理・執筆のルール

- Approach Axis内の用語は、このディレクトリの [glossary.md](glossary.md) を正本とする。本文・骨子・補助資料は、この用語定義に合わせる。
- 新語や定義変更は、まず `review/glossary_candidates.md` に置き、レビュー後に `glossary.md` へ昇格する。
- リポジトリ直下の `glossary.md` はCokes全体の上位用語集であり、Approach Axis固有語の詳細は本ディレクトリの `glossary.md` が担当する。
- 章の構成・状態が変わったら `framework.md` とこの README を同時に更新する。
- 事実記録は `incidents/`、そこから一般化した再発防止策は `lessons/` に分ける。
- ファイルの移動・削除は、参照リンクを確認し、内容の確定先が決まってから行う。
- 確定版は直下、骨子・旧版は `archive/drafts/`、補助資料は `references/` に置く。

## 全章共通のガードレール

Approach Axisは、AI内部の機構を断定する理論ではなく、観測可能な入出力関係を操作・評価・再利用する体系として整理する。

- **機構非依存:** プロンプト操作と内部アクティベーションへの直接介入が、同じ内部表現変化を生むとは仮定しない。
- **3つの層を分ける:** 観測された事実、理解のための解釈モデル、人間が行う操作判断を混同しない。
- **外部参照の位置づけ:** 論文・技術レポート・公式資料は「参考となる学術理論・研究上の視点・公開資料」として扱い、Axisの実装証明とは書かない。
- **仮説の明示:** 効力順位、モデル別傾向、内部原因の推定は、普遍則ではなく作業仮説・観察仮説として記載する。
- **出力中心の評価:** 隠れた内部状態を推測して成否を決めず、出力をSuccess / Partial Success / Approach Failureで人間が判定する。
- **人間の責任:** AIの内部を知らないことを、設計・評価・Handoffの責任放棄の理由にしない。

本文をレビューするときは、各節について「これは観測事実か、解釈モデルか、操作上の判断か」を確認する。

## 次の整理順

1. 全10章の本文を正本候補として運用し、用語集を含む章間整合を維持する。
2. Cokes版仕様候補とリポジトリ直下の用語集を参照し、上位体系との整合を維持する。
3. Cokes第1版との整合を維持し、必要な定義変更を本文へ反映する。

## 参照ソース

本文の一次資料は `docs/knowledge/axis-log-01/`、統合・補強資料は `axis-log-02`〜`axis-log-04` です。
上位体系はリポジトリ直下の `philosophy.md`、`specification.md`（Cokes第1版）、`glossary.md` を参照します。旧CQSE期の `specification_cqse.md` は履歴です。

### 主な資料

- `docs/knowledge/axis-log-01/approach-axis-framework.md`
- `docs/knowledge/axis-log-01/axis-words-magnet-map.md`
- `docs/knowledge/axis-log-01/gravity-tensor-model.md`
- `docs/knowledge/axis-log-02/integrated_knowledge.md`
- `docs/knowledge/axis-log-03/integrated_knowledge.md`
- `docs/knowledge/axis-log-04/integrated_knowledge.md`
