# Approach Axis Framework — インデックス

- 生成: Sonnet（Executor）
- 生成日: 2026-07-11
- ステータス: **全章本文レビュー済み・昇格済み（Cokes側定義承認待ち）**
- 本文の正本候補: `prologue.md`、`ch01.md`〜`ch10.md`

## 基本姿勢

Approach Axisは、AI内部の機構を断定する理論ではなく、観測可能な入力と出力の関係から、人間の意図に近づきやすい操作を設計・評価・再利用する体系として整理する。プロンプト操作と内部アクティベーションへの直接介入が同じ内部表現変化を生むとは仮定しない。

---

## 章構成

| 章 | タイトル | 本文 | ステータス |
|----|---------|------|---------|
| プロローグ | AIの内側——意味の地形 | [prologue.md](prologue.md) | 承認・昇格済み |
| 第1章 | Approach Axisとは何か | [ch01.md](ch01.md) | 承認・昇格済み |
| 第2章 | なぜ効くのか——地形磁力モデル | [ch02.md](ch02.md) | 承認・昇格済み |
| 第3章 | 3層構造の中での位置づけ | [ch03.md](ch03.md) | 承認・昇格済み |
| 第4章 | Approach Axis運用アーキテクチャ（4層） | [ch04.md](ch04.md) | 承認・昇格済み |
| 第5章 | 軸語彙リファレンス | [ch05.md](ch05.md) | 承認・昇格済み |
| 第6章 | 操作プリミティブ7種 | [ch06.md](ch06.md) | 承認・昇格済み |
| 第7章 | 実行フローと状態モデル（実務パターン） | [ch07.md](ch07.md) | 承認・昇格済み |
| 第8章 | 失敗モードと診断 | [ch08.md](ch08.md) | 承認・昇格済み |
| 第9章 | 運用ルールとCokes体系内での位置づけ | [ch09.md](ch09.md) | 承認・昇格済み |
| 第10章 | テンプレート集と実践Tips | [ch10.md](ch10.md) | 承認・昇格済み |

**管理ルール:**
- 本文は直下、骨子・旧版は `archive/drafts/`、補助資料は `references/` に置く。
- Cokes側定義の承認後、必要な定義変更を本文へ反映する。

---

## 参照ファイル

| ファイル | 役割 |
|---------|------|
| [glossary.md](glossary.md) | 用語・比喩定義の正本 |
| [references/terrain-magnetic-model.md](references/terrain-magnetic-model.md) | 地形磁力モデル（第2章・第3章の詳細。旧: knowledge/axis-log-01/gravity-tensor-model.md） |
| [references/model_comparison_axis.md](references/model_comparison_axis.md) | 製造元比較軸（第5章・第8章の詳細） |
| [references/metaphor_catalog.md](references/metaphor_catalog.md) | 比喩カタログ |
| [incidents/](incidents/) | AIオペレーションインシデント記録 |
| [lessons/](lessons/) | インシデントから抽出した運用ルール |

---

## 未解決議題

- **Axis実装関連（継続議題）:** プロンプト文化通史の体系的記録（Cokes/Axisが担い手として機能できるか）
- **完稿後の外部フィードバック（TODO）:** Cokes／Axisと、AI delegation・cognitive load・harness、embedding／semantic space・vector index・RAG研究を接続した1枚図を作成する。新理論の主張ではなく、既存研究との対応・不一致を示す接続図としてReddit等へ公開し、反応を観測する。

### 確定済み（クローズ）
- 擬似コード確定。実装はプロジェクト側。
- 品質スコア削除。3段階ラベル+人的レビューに置換。
- 比喩配置: 第10章§10.3に集約。
- 研究参照: 含める。アーキテクチャ刷新時のみ更新。
- 比較軸4本確定・製造元別特性テーブル完成（2026-07-11）。詳細: `references/model_comparison_axis.md`

---

## ⚠ 矛盾メモ

2026-07-23 の10章横断レビューで、重なり領域の論理積化、旧名称の置換、Approach Failureの定義拡張、Handoff／責務放棄の第7章集約を反映済み。

ただし以下はKnowledge層と正本層（Cokes正本）の間の差異（このドキュメントのスコープ外）:
- Cokes一言定義の3ドキュメント不一致（M2）
- 品質モデルの対等3軸 vs 階層構造の表現差（M1）
これらはCokes正本層の更新（C8・C9）で解消する人間判断事項。
