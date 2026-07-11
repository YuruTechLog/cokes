# Approach Axis Framework — インデックス

- 生成: Sonnet（Executor）
- 生成日: 2026-07-11
- ステータス: ドラフト（人間レビュー待ち）
- **昇格条件**: 全章確定 → `framework.md` にリネーム

---

## 章構成

| 章 | タイトル | 骨子ファイル | ドラフト | ステータス |
|----|---------|------------|--------|---------|
| プロローグ | AIの内側——意味の地形 | — | [prologue_draft_v3.md](drafts/prologue_draft_v3.md) | 作業中 |
| 第1章 | Approach Axisとは何か | [ch01.md](drafts/ch01.md) | — | 骨子のみ |
| 第2章 | なぜ効くのか——地形磁力モデル | [ch02.md](drafts/ch02.md) | [ch02_draft_v1.md](drafts/ch02_draft_v1.md) | 作業中 |
| 第3章 | 3層構造の中での生息域 | [ch03.md](drafts/ch03.md) | — | 骨子のみ |
| 第4章 | フレームワーク構成——4層構造 | [ch04.md](drafts/ch04.md) | — | 骨子のみ |
| 第5章 | 軸語彙リファレンス | [ch05.md](drafts/ch05.md) | — | 骨子のみ |
| 第6章 | 操作プリミティブ7種 | [ch06.md](drafts/ch06.md) | — | 骨子のみ |
| 第7章 | 実行フローと状態モデル | [ch07.md](drafts/ch07.md) | — | 骨子のみ |
| 第8章 | 失敗モードと診断 | [ch08.md](drafts/ch08.md) | — | 骨子のみ |
| 第9章 | 運用ルールとCokes体系内での位置づけ | [ch09.md](drafts/ch09.md) | — | 骨子のみ |
| 第10章 | テンプレート集と実践Tips | [ch10.md](drafts/ch10.md) | — | 骨子のみ |

**昇格ルール:**
- 骨子のみ → 文章化ドラフト作成 → レビュー・修正 → 確定 → `chXX.md`（drafts/から直下に移動）
- 全章確定 → `framework_draft.md` → `framework.md`

---

## 参照ファイル

| ファイル | 役割 |
|---------|------|
| [glossary.md](glossary.md) | 用語・比喩定義の正本 |
| [drafts/model_comparison_axis.md](drafts/model_comparison_axis.md) | 製造元比較軸（第5章・第8章の詳細） |
| [drafts/metaphor_catalog.md](drafts/metaphor_catalog.md) | 比喩カタログ |

---

## 未解決議題

- **Axis実装関連（継続議題）:** プロンプト文化通史の体系的記録（Cokes/Axisが担い手として機能できるか）

### 確定済み（クローズ）
- 擬似コード確定。実装はプロジェクト側。
- 品質スコア削除。3段階ラベル+人的レビューに置換。
- 比喩配置: 第10章§10.3に集約。
- 研究参照: 含める。アーキテクチャ刷新時のみ更新。
- 比較軸4本確定・製造元別特性テーブル完成（2026-07-11）。詳細: `drafts/model_comparison_axis.md`

---

## ⚠ 矛盾メモ

素材間の記述食い違いなし。

ただし以下はKnowledge層と正本層（Cokes正本）の間の差異（このドキュメントのスコープ外）:
- Cokes一言定義の3ドキュメント不一致（M2）
- 品質モデルの対等3軸 vs 階層構造の表現差（M1）
これらはCokes正本層の更新（C8・C9）で解消する人間判断事項。
