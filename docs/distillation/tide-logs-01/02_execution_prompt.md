# Chat Summary：AIチャットログ蒸留プロジェクト（Cokes）

## プロジェクト目的

AIとの対話ログ（Markdown）を、再利用可能な知識へ蒸留する。

最終成果物は以下の3段階とする。

```
Chat Log（一次資料） = chat-archives
        ↓
Distillation（判断・設計のためのルールの蒸留） = distillation
        ↓
Summary（意思決定が起きた流れ） = chat-summary
        ↓
Knowledge（再利用可能な成果物） = knowledge
```

最終的には、Knowledge を元に note 記事や README を作成する。

---

# ディレクトリ構成

```
cokes/
└─ docs
    ├─ chat-archives
    │   └─ tide-logs-01
    │
    ├─ chat-summary
    │   ├─ tide-logs-01_01
    │   └─ tide-logs-01_02
    │
    ├── distillation/
    │       └── tide-logs-01/
    │           ├── 01_tide-logs-01_distillation-workflow.md
    │           ├── 01_log_topics.md
    │           ├── 01_incident.md
    │           ├── 02_execution_prompt.md
    │           ├── 02_tide-logs-01_distillation-workflow.md
    │           ├── 02_log_topics.md
    │           └── 02_incident.md
    │
    ├─ knowledge
    │
    └─ note-draft
```

※以下のファイル名説明では「nn」と表記。例: 01_log_topics.md = nn_log_topics.md
```
tide-logs-01/
  ├─ 01
  ├─ 02
  ├─ 03
```

※ GitHub リポジトリURL は以下
   https://github.com/YuruTechLog/cokes

---

# 各フォルダの役割

## chat-archives

一次資料。

AIとの対話ログ（Markdown）。

ここは編集しない。

---
## distillation/tide-logs-01

蒸留するための設計・ワークフロー。

- nn_log_topics.md
ログ内でのテーマ・話題一覧

- nn_tide-logs-01_distillation-workflow.md
最終決定事項だけをまとめる

- nn_incident.md
「なぜこう決めたか」「何が失敗だったか」改善点を残す

- nn_execution_prompt.md
再実行時のLLM向けプロンプト記録

※今後の候補
- nn_tide-logs-01_distillation-design.md
設計思想まで含む

---
## chat-summary/tide-logs-01_nn

試行錯誤・失敗・設計変更・インシデント保存用。

例

* 要約方針の失敗
* ハルシネーション混入例
* 設計変更の経緯
* AIとの検討ログ

削除しない。

---

## chat-summary/tide-logs-01_nn_final

正式なSummary。

GitHub公開対象。

---

## knowledge

テーマ別に整理した知識。

記事・README・フレームワーク作成の元資料。

---

# Summary作成ルール

Summaryは**時系列を維持しつつ、テーマ単位で整理する。**

途中で同じテーマが再登場した場合は統合してよい。

思考整理やAIとの重複説明は大胆に圧縮する。

---

## Summaryの目的

目的は要約ではない。

**知識として再利用できる形へ整理すること。**

---

## Summaryへ残すもの

* 新しいテーマ
* 判断理由
* 最終結論
* 次のテーマへのつながり

---

## Summaryから削るもの

* AIの長い説明
* 同じ説明の繰り返し
* 思考整理だけの独り言
* 「なるほど」などの相づち

---

## 高校生でも理解できる文章を目標とする

専門用語は必要最低限。

必要なら簡単な説明を添える。

---

# LLM総括

Summaryの最後に以下を付けてよい。

```
## LLM総括（考察）

※ここから下はLLMによる整理・考察です。
```

ここでは

* テーマ同士の関係
* Cokesとの関係
* 記事化のヒント

などを書いてよい。

ただし、

ログに存在しない事実を書いてはいけない。

事実と考察は明確に区別する。

---

# 作業手順

## Phase1

全ログを横断して読む。

成果物

```
log_topics.md
```

ここでは文章を書かず、

テーマ一覧だけ作る。

---

## Phase2

Distillation内のテーマ一覧を基準に、

全ログを横断的に走査してLogTopicsを作成する。

LogTopicsごとに、DistillationWorkflow, Incidentを作成する。

重複する内容は統合する。

当該項目以前で説明済みなら引用のみでよい。

再処理を実施する際のプロンプトについても管理する。(nn_execution_prompt)
初回は不要。

---

## Phase3

Distillation内のテーマ一覧を基準に、

各ログSummaryを作成する。

重複する内容は統合する。

前ログで説明済みなら引用のみでよい。

---

## Phase4

Distillation + Summaryを横断して、

Knowledgeを作成する。

Knowledgeは完全にテーマ別とする。

---

# AIへの重要指示

最優先事項は**原文への忠実性**。

ハルシネーションを避けるため、

ログに書かれていない内容は書かない。

補足や考察を書く場合は、

必ず「LLM総括」として分離する。

設計を増やすことよりも、

蒸留作業を優先する。

オーバースペックな提案は不要。

成果物を着実に増やすことを最優先とする。
