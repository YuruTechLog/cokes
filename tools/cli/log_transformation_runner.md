# Cokes Skill: log_transformation_runner

# ■ Pre-Execution: Specification Load

最初に必ず以下を読み込む：

- cokes/specification.md
- tools/log_transformation/01_spec.md
- tools/log_transformation/02_rules.md
- tools/log_transformation/03_exec_template.md

---

## ■ 目的

この実行の基準ルールを固定するため。

---

## ■ ルール

- specの内容は最優先
- runnerの判断よりspecが上位
- Phase定義はspec準拠

## ■ 仕様衝突時のルール（重要）

spec / rules / exec template の間で矛盾がある場合：

1. specification.md を最優先
2. 01_spec.md はローカル補足として扱う
3. 02_rules.md は制約補助
4. 03_exec_template.md は実行順序定義のみ

いかなる場合も runner の判断で上書きしない

---

## ■ 目的

指定ログセット（01, 02, ...）を順に読み込み、
Cokes Execution Template に従って蒸留パイプラインを実行する。

---

## ■ 対象

- LOG_PATH: 実行時に対話で収集（下記「パラメータ収集」参照）
- DATASET: 実行時に対話で収集（下記「パラメータ収集」参照）
- RUN_ID: Phase0で自動生成

---

## ■ ID設計

- DATASET_ID: logセット単位（例：tide-logs-01）
- LOG_ID: 個別ログ（log01, log02）
- RUN_ID: 実行バージョン（01, 02, 03）

---

## ■ RUN_ID生成ルール（自動）

- RUN_IDはDATASET単位で管理する
- 既存RUN_IDを昇順で取得する
- 最大値 + 1 を次のRUN_IDとする
- 桁は2桁ゼロ埋め（01, 02, 03…）
- 自動付与できない場合は即時break、ユーザーに確認する

例：
- 01
- 02
- 03 → 次は 04

---

## ■ RUN_ID探索対象

RUN_IDは以下のいずれかから抽出する：

- docs/chat-summary/{DATASET_NAME}_*
- docs/distillation/{DATASET_NAME}/*
- knowledge/{DATASET_NAME}/*

優先順位：
1. distillation
2. summary
3. knowledge

---

## ■ ID使用ルール

- logXX は「入力データ識別子」
- RUN_ID は「出力バージョン識別子」

すべての出力ファイル名は RUN_ID を含める場合は
「再実行時のみ」使用する

通常の成果物は logXX 基準で命名する

---

## ■ 入力ログ構造

このデータセットには複数ログが含まれる：

例：
- log01.md
- log02.md
- log03.md

👉 必ず番号順、ファイル名昇順に処理する

---

# ■ 実行全体ルール

- ログ外情報は禁止
- 推測は禁止
- 必ずログ順を維持
- 01 → 02 → 03 の順で処理
- 各ログごとに Phase1〜4 を完結させる
- 統合は最後のみ行う

---

# ■ Phase構造（各ログごとに実行）

---

# ■ Phase0：Preflight（実行前準備）

## ■ パラメータ収集（Phase0冒頭・必須）

spec読込完了後、以下を順番にユーザーへ質問する：

**Step 1: LOG_PATH**
> 「ログのパスを入力してください（例: docs/chat-archives/tide-logs-01/）」

**Step 2: DATASET_NAME**
> 「データセット名を入力してください（例: tide-logs-01）」

**Step 3: 確認**
収集後、以下を表示してユーザー確認を求める：

```
--- 実行パラメータ確認 ---
LOG_PATH  : {入力値}
DATASET   : {入力値}
-------------------------
この内容で実行しますか？ [y/n]
```

- y → やること（必須）チェックリストへ進む
- n → Step 1 に戻る

---

## ■ やること（必須）

- [ ] specification.md を読む
- [ ] 01_spec / 02_rules / 03_exec_template を読む
- [ ] LOG_PATH の存在確認
- [ ] DATASET_NAME の確認
- [ ] RUN_ID を自動生成 or 既存確認
- [ ] 対象ログ一覧を取得（log01, log02…）
- [ ] 処理順序を確定（昇順）

---

## ■ 停止条件（重要）

以下が1つでも未確定なら実行停止：

- RUN_ID未確定
- ログ一覧が取得できない
- spec未読状態
- 対象パス不明

→ 必ずユーザー確認へ戻る、問題内容は収集してユーザーへ提示

---

## ■ 成功条件

- 実行対象・順序・IDがすべて確定している状態

---

## ■ Phase1：ログ解析（Log Scan）

対象：
- logXX.md（1ファイル単位）

やること：
- 全文読む
- テーマ抽出
- log_topics生成

出力：
- log_topics（そのログ単体）

完了後質問：

> 「logXX Phase1を確定しますか？」

---

## ■ Phase2：Distillation生成

やること：
- テーマ統合
- 重複削除
- 構造化

出力：
- {NN}_log_topics.md
- {NN}_incident.md
- {NN}_distillation-workflow.md

完了後質問：

> 「logXX distillationを確定しますか？」

---

## ■ Phase3：Summary生成

やること：
- 意思決定整理
- 時系列保持
- 重複統合

出力：
- chat-summary/{DATASET_NAME}_logXX

完了後質問：

> 「logXX summaryを確定しますか？」

---

## ■ Phase4：Knowledge生成

やること：
- distillation + summary を統合
- テーマ別に再構造化
- 再利用可能形式にする

出力：
- knowledge/{DATASET_NAME}/logXX

完了後質問：

> 「logXX knowledgeを生成しますか？」

---

# ■ ログセット全体処理（重要）

すべてのlogXX処理が完了した後に実行：

## ■ Cross-log Integration

やること：
- log01〜logNNを統合
- テーマ重複を整理
- 全体構造を再編成

出力：
- dataset-wide knowledge
- integrated distillation summary

---

# ■ 制約（絶対ルール）

- ログ外情報は禁止
- 推測は禁止
- 各ログ単位で完結させる
- 時系列は維持する
- 高校生でも読める表現
- 事実と考察は分離（LLM総括のみ許可）

---

# ■ 実行チェックリスト

開始前：

- [ ] log01〜logNNの存在確認
- [ ] 順序が明確か
- [ ] 各ログ単体で処理できるか

各ログ後：

- [ ] Phase0完了
- [ ] Phase1完了
- [ ] Phase2完了
- [ ] Phase3完了
- [ ] Phase4完了

最終：

- [ ] cross-log integration完了

---

# ■ 成功条件（White Star ⭐）

以下が揃った場合成功：

- 全ログがPhase0〜4完走
- distillation生成済み
- summary生成済み
- knowledge再構成済み
- cross-log統合完了

---

# ■ 補足

- このスキルは単発ログ処理ではなく「データセット処理」
- log01単体実行も可能だが、設計上は連続処理が前提
