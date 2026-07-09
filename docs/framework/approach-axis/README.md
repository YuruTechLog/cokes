# docs/framework/approach-axis/

Approach Axis Frameworkの実装ドキュメント群。

## このディレクトリの位置づけ

```
docs/knowledge/      ← 蒸留成果物（ログから抽出した知識。ログ単位）
docs/distillation/   ← 蒸留中間成果物（テーマ別・incident）
docs/chat-summary/   ← 意思決定サマリー（ログ単位）
docs/framework/      ← ← ここ。知識を統合した実装向けドキュメント
```

知識の流れ:
```
chat-archives（生ログ）
  → distillation（テーマ抽出）
  → knowledge（再利用可能な知識ユニット）
  → framework（実装ドキュメント）  ← このディレクトリ
```

## ファイル一覧

| ファイル | 内容 | 状態 |
|---------|------|------|
| `opus_prompt_framework_draft.md` | Opusへの分析依頼プロンプト（章立て・骨子ドラフト生成用） | 完成 |
| `framework_draft.md` | Opusが生成した章立て・骨子ドラフト | 未作成（Opus実行後に生成） |

## 参照ソース（axis-log-01〜03）

**Primary（axis-log-01）:**
- `docs/knowledge/axis-log-01/approach-axis-framework.md`
- `docs/knowledge/axis-log-01/axis-words-magnet-map.md`
- `docs/knowledge/axis-log-01/gravity-tensor-model.md`

**Secondary（axis-log-02）:**
- `docs/knowledge/axis-log-02/integrated_knowledge.md`

**Tertiary（axis-log-03）:**
- `docs/knowledge/axis-log-03/integrated_knowledge.md`
