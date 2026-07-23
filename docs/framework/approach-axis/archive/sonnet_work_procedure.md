# 作業手順書: Approach Axis Framework 章立て・骨子ドラフト生成（Sonnet実行用）

- 作成: Fable 5（Advisor役）
- 作成日: 2026-07-10
- 実行者: Sonnet（Executor役）
- 依頼元プロンプト: `opus_prompt_framework_draft.md`（本手順書はこれを実行可能な手順に分解したもの）

---

## 0. この手順書の位置づけ

「骨格→AI統合ルート」（axis-log-03 IK09）の実践。

```
Fable 5（Advisor役）: 骨格抽出 = 章立てスケルトン確定・判断基準の事前定義
    ↓
Sonnet（実行者）: 肉付け = 各章の骨子を参照素材から埋める
    ↓
人間: 確認 = 章立て承認・最終レビュー
```

**Sonnetは章構成の再設計をしない。** 本手順書の章立てスケルトンに従い、骨子の中身だけを素材から埋める。
章の追加・削除・並べ替えが必要と判断した場合は作業を止めて人間に提案する（勝手に変えない）。

---

## 1. 成果物定義

| 項目 | 内容 |
|------|------|
| ファイル | `docs/framework/approach-axis/framework_draft.md`（新規作成） |
| 形式 | `opus_prompt_framework_draft.md` の「出力形式」セクション準拠 |
| 分量 | 章立て + 各章骨子2〜5行。本文は書かない |
| 対象読者 | 実装者（AIプロンプト設計・システム設計の実務担当者） |
| 文体 | 通常の日本語（genshijin/caveman圧縮の適用外。成果物テキストのため） |

---

## 2. 絶対制約（違反したら成果物無効）

1. **参照素材に記載のない内容を追加しない。** 推測・一般知識による補完は禁止
2. 確定済みの命名を変えない: Approach Axis / Axis Words / Magnet Map / Model Profile / Templates / 地形磁力モデル / Approach Failure / おはじきモデル / ゆるてく語
3. `docs/chat-archives/` は参照禁止（未加工の生ログ）
4. 各骨子項目に **参照元ファイル名を必ず付記**（トレーサビリティ確保）
5. 素材間で記述が食い違う場合: **新しいログセット優先**（log-03 > log-02 > log-01）。ただし食い違い自体を「⚠矛盾メモ」として成果物末尾に記録する
6. 未確定・素材に情報がない箇所は `TODO:` マーカーで明示（自己判断で埋めない）
7. 成果物の上書き禁止。修正時は人間指示を待つ

---

## 3. Phase 0: Preflight（作業前確認）

以下を順に確認。1つでも失敗したら**停止して人間に報告**。

```bash
# 必須ファイル存在確認
ls docs/knowledge/axis-log-01/approach-axis-framework.md
ls docs/knowledge/axis-log-01/axis-words-magnet-map.md
ls docs/framework/approach-axis/drafts/terrain-magnetic-model.md
ls docs/knowledge/axis-log-01/cokes-design-philosophy.md
ls docs/knowledge/axis-log-02/integrated_knowledge.md
ls docs/knowledge/axis-log-03/integrated_knowledge.md

# 成果物が既存でないこと（既存なら停止。上書き禁止）
ls docs/framework/approach-axis/framework_draft.md 2>/dev/null && echo "STOP: 既存ファイルあり"
```

---

## 4. Phase 1: 素材読込（順序固定）

読込順序と抽出目的。全文読込は下記6ファイルのみ。

| 順 | ファイル | 抽出目的 |
|----|---------|---------|
| 1 | `docs/knowledge/axis-log-01/approach-axis-framework.md` | 定義・4層構造・プリミティブ7種・状態モデル・評価指標・テンプレート類 |
| 2 | `docs/knowledge/axis-log-01/axis-words-magnet-map.md` | 軸語彙5分類・磁力強度マップ・モデル別特性・実務での使い方 |
| 3 | `docs/framework/approach-axis/drafts/terrain-magnetic-model.md` | 第一原理・3要素・崩壊特性・研究層との3層関係 |
| 4 | `docs/knowledge/axis-log-01/cokes-design-philosophy.md` | Cokes側から見たAxisの位置づけ（第9章素材） |
| 5 | `docs/knowledge/axis-log-02/integrated_knowledge.md` | Axis三層構造（操作/説明/思想）・形式化の価値・Executor×Advisor |
| 6 | `docs/knowledge/axis-log-03/integrated_knowledge.md` | Cokes/Axis関係・Handoff=分岐点・運用ルール・AI誤認リスク（IK04のFable記述はframework用語として採用しない） |
| 7 | `docs/knowledge/axis-log-04/integrated_knowledge.md` | Axis 5軸確定版・論文裏付けマップ・比喩体系・日本語3原則・コアメッセージ確定版・画像生成拡張（第10章Tips素材） |

**追加参照の許可条件**（`opus_prompt_framework_draft.md` §参照判断ルール準拠）:
- 骨子を書くのに knowledge の記述が1〜2行しかなく文脈不明な場合のみ
- 経緯が必要 → `docs/chat-summary/` / 議論詳細が必要 → `docs/distillation/`
- 追加参照したファイルは成果物の「生成メモ」に列挙すること

---

## 5. Phase 2: 章立てスケルトン（確定済み・変更禁止）

以下の10章構成で骨子を埋める。**[人間判断]** マークは人間確認が必要な箇所。

```
第1章: Approach Axisとは何か
  素材: approach-axis-framework.md（定義・起源・命名理由）
  骨子に含める: 定義 / 起源の一言 / 「近づく動作の操作化」/ 何を解決するか

第2章: なぜ効くのか — 地形磁力モデル
  素材: terrain-magnetic-model.md
  骨子に含める: 第一原理 / 人間・AIの軸生成能力差 / 3要素（多様体・傾斜・崩壊）/
                「操作のための解釈モデルであり実装の説明モデルではない」の明示

第3章: 3層構造の中での生息域
  素材: terrain-magnetic-model.md（研究層との関係）
  骨子に含める: 研究層/解釈層/操作層 / Activation Steering等との対応表 / 独自領域の明示
  [人間判断] arXiv:2601.02896等の2026年研究参照を実装ドキュメントに含めるか
             （鮮度が落ちる情報。含める場合は「2026年時点」の断り必須）

第4章: フレームワーク構成 — 4層構造
  素材: approach-axis-framework.md（4層構造・運用原理）
  骨子に含める: Layer1-4の役割 / 運用原理（L1命令→L2優先度→L3モデル適合→L4実行）

第5章: 軸語彙リファレンス
  素材: axis-words-magnet-map.md
  骨子に含める: 5分類+補助（順序）/ 磁力強度マップ / 「条件依存で変動」の注意 /
                モデル別磁力特性テーブル / 実務での使い方3点
  [人間判断] モデル別特性テーブル（Claude/GPT/Gemini/Copilot）は2026年時点の観察。
             バージョン追従の運用方針（誰がいつ更新するか）は素材に無い → TODO化

第6章: 操作プリミティブ7種
  素材: approach-axis-framework.md
  骨子に含める: 7種の表（Position/Magnitude/Constraint/Filter/Blend/Retry/Lock）/
                コマンド例の位置づけ
  [人間判断] コマンド例（setPosition(target: conceptual_explanation) / setMagnitude(tone: slight)等）は擬似コードか実装対象か。
             骨子では「内部座標・数値ではなく、自然言語の操作ニュアンスを記録する擬似コード」として扱う

第7章: 実行フローと状態モデル
  素材: approach-axis-framework.md
  骨子に含める: 実行フロー5段階 / 状態モデル（Idle→Plan→Execute→Evaluate）/
                評価指標3種 / Success/Partial/Failureの閾値
  [人間判断] 品質スコア閾値（90/70）の算出方法が素材に未定義 → TODO化

第8章: 失敗モードと診断
  素材: approach-axis-framework.md（失敗モード表）+ terrain-magnetic-model.md（崩壊特性）
  骨子に含める: Approach Failure=ハルシネーションの定義 / 即停止プロトコル /
                モデル別崩壊特性と対処 / 過剰適合・コスト超過

第9章: 運用ルールとCokes体系内での位置づけ
  素材: axis-log-03 integrated_knowledge.md + cokes-design-philosophy.md +
        axis-log-02 integrated_knowledge.md
  骨子に含める: Cokes/Axisの責任分担 / Handoff=分岐点 /
                外部ツール前Axis語彙必須ルール / AI自身によるフレームワーク誤認リスク /
                Axis三層構造（操作/説明/思想）

第10章: テンプレート集と実践Tips
  素材: approach-axis-framework.md + axis-log-04 integrated_knowledge.md
  骨子に含める:
    §10.1 運用カード / Handoffテンプレート / （Layer4 Templatesとの対応）
    §10.2 日本語3原則（主語明示 / 文末核心語彙 / 軸語彙前置）
    §10.3 画像生成へのAxis適用（3レイヤー設計 / Prompt Scheduling構文）
    §10.4 パーツ単位発注パターン（Executor×Advisor 実践）
```

---

## 6. Phase 3: 骨子執筆ルール

- 各章: **目的（1行）+ 骨子（2〜5項目）+ 参照素材（ファイル名）** の3点セット
- 骨子は「何を書くか」の指示であり本文ではない。文はいらない、項目でよい
- 素材の表・図はコピーしない。「〜の表を掲載」と指示として書く
- [人間判断] 箇所は成果物内で `> **[人間判断]** ...` の引用ブロックで目立たせる
- 章間の重複が生じたら: 主たる章に置き、他章からは「第N章参照」と書く

---

## 7. Phase 4: セルフチェック（提出前必須）

- [ ] 10章すべてに 目的/骨子/参照素材 がある
- [ ] 参照素材のないコンテンツ（一般知識由来）が混入していない
- [ ] 命名が素材と一字一句一致（§2の固定命名リスト照合）
- [ ] [人間判断] 4件（§5記載）がすべて成果物に反映されている
- [ ] TODO: マーカーの箇所がすべて「未解決議題」セクションにも列挙されている
- [ ] 未解決議題に axis-log-02 の4件（深海型セルフケア設計 / プロンプト文化通史 / 「世界初」表現の検証 / 片栗粉2段構造）のうち **Axis実装に関係するもののみ** 記載されている（関係しないものは書かない）
- [ ] chat-archives を参照していない
- [ ] 生成メモに追加参照ファイル一覧がある（追加参照した場合）

チェック失敗 → 自己修正は2回まで。3回目失敗で停止して人間報告（リトライ上限ルール準拠）。

---

## 8. Phase 5: 完了処理

1. `framework_draft.md` を書き出し
2. `README.md` のファイル一覧表の `framework_draft.md` 行を「未作成」→「ドラフト（人間レビュー待ち）」に更新
3. **git commit は人間の承認後のみ**（mainブランチのため。破壊的操作ルール準拠）
4. 人間への報告に含めること:
   - [人間判断] 4件への回答依頼
   - TODO残存箇所の一覧
   - ⚠矛盾メモ（あれば）

---

## 9. 人間判断ポイント一覧（サマリー）

| # | 箇所 | 判断内容 | 仮置き |
|---|------|---------|--------|
| 1 | 第3章 | 2026年研究参照（arXiv等）を含めるか | 含める+時点断り |
| 2 | 第5章 | モデル別特性テーブルの更新運用 | TODO化 |
| 3 | 第6章 | プリミティブのコマンド例は擬似コードか実装対象か | 擬似コードと仮置き |
| 4 | 第7章 | 品質スコア閾値90/70の算出方法 | TODO化 |
| 5 | Phase 5 | git commit 実行可否 | 承認待ち |

仮置きのまま作業は最後まで進めてよい（ブロックしない）。ただし成果物とレポートに必ず明記。

Cokes正本層に関わる判断（C1〜C9）は §11.3 参照。全件スコープ外・人間承認後に別タスク化。

---

## 10. 停止条件（即停止→人間報告）

- Preflight失敗（素材ファイル欠損・成果物既存）
- 章立てスケルトンの変更が必要と判断した場合（提案のみして停止）
- 素材間の矛盾が骨子の書き分けで吸収できない場合
- セルフチェック3回失敗
- 参照素材に「確定」記述がなく章の骨子が半分以上 TODO になる場合

---

## 11. Cokesとの接続 — Doc依存関係マップ

### 11.1 リポジトリ内ドキュメント階層と依存方向

```
【Cokes正本層】（リポジトリルート）
  philosophy.md ────── Cokes設計思想（品質/コスト/人の3軸・Handoff）
  specification.md ─── 旧CQSE期の問題提起・仕様（Cokes改訂前）
  glossary.md ──────── 用語集（Approach Axis / Cokes関連語を反映中）
  README.md ────────── 入口（frameworkへの導線を確認・更新）
        ▲
        │ 上位概念を参照（AxisはCokesの道具。憲法と法律の関係）
        │
【Framework層】（docs/framework/approach-axis/）← 今回の作業対象
  framework_draft.md（生成予定）
        ▲
        │ 蒸留知識を素材として参照
        │
【Knowledge層】（docs/knowledge/）
  axis-log-01/: approach-axis-framework.md / axis-words-magnet-map.md /
                terrain-magnetic-model.md / cokes-design-philosophy.md
  axis-log-02/: integrated_knowledge.md
  axis-log-03/: integrated_knowledge.md
        ▲
        │ テーマ抽出・意思決定記録
        │
【中間層】docs/distillation/ + docs/chat-summary/（粒度不足時のみ参照）
        ▲
【原本層】docs/chat-archives/（参照禁止・改変禁止）
```

**依存ルール:**
- framework_draft.md は Knowledge層のみを直接素材とする（正本層はリンク参照のみ。内容コピー禁止）
- 正本層とKnowledge層で記述が食い違う場合: **正本層優先**。ただし `specification.md` は旧CQSE期の問題提起を残した改訂前の文書であるため、現行Cokes定義との不一致は §11.3 の移行課題として記録する
- framework → Cokes方向の参照はOK。Cokes正本 → framework方向の参照は人間が正本を更新するときのみ

### 11.2 framework_draft.md 第9章とCokes正本の対応

第9章（運用ルールとCokes体系内での位置づけ）で参照する概念と正本の対応:

| 概念 | Knowledge層の根拠 | Cokes正本での状態 |
|------|------------------|------------------|
| Cokes/Axis分離（憲法と法律） | axis-log-01 cokes-design-philosophy.md | framework側で整理済み。正本追記は未実施 |
| Handoff = 条件付き出口・分岐点（終点ではない） | axis-log-03 IK07 + approach-axis glossary | glossary側で反映済み。philosophy.md追記は未実施 |
| Cokes三原則 | axis-log-01（草案） | 正本未確定 |
| 品質階層構造（品質>人>コスト） | axis-log-03 IK01 | philosophy.mdは3軸バランス表現 |

**Sonnetへの指示:** 上記の「正本での状態」ギャップは埋めない。第9章骨子はKnowledge層の記述で書き、
対応する正本更新は下記11.3のCokes側作業として分離する。

### 11.3 Cokes側に必要な作業（今回のスコープ外・人間承認後に別タスク化）

framework_draft.md 完成後、Cokes正本層との整合のため以下が必要になる。
**全件人間判断必須**（正本層の変更 = 憲法改正に相当）。

| # | 作業 | 対象 | 種別 | 優先度 |
|---|------|------|------|--------|
| C1 | CQSE→Cokes更新。⚠単純な名称置換ではなく、旧CQSEの問題提起・現行Cokesの一言定義・判断原則を分離して再構成する。`cokes_definition_layer_proposal.md` の承認を前提とする | specification.md | 改名+定義再構成 | 高（C9承認後） |
| C2 | Axis関連用語のglossary追加（Approach Axis / Axis Words / Magnet Map / 地形磁力モデル / Approach Failure） | glossary.md | **反映済み。以後はglossaryを上位語彙として参照** | 完了 |
| C3 | Handoff定義の更新（条件付き出口・分岐点・再評価条件の反映） | glossary.md / philosophy.md | glossary反映済み。philosophy.md追記は未実施 | 中 |
| C4 | Cokes三原則の確定（草案→確定 or 破棄の判断） | philosophy.md | 意思決定 | 中 |
| C5 | Cokes/Axis分離（憲法と法律の関係）の正本明記 | philosophy.md | 追記 | 中 |
| C6 | Cokes/Axis責任分担の正本化（Fable 5は作業履歴上のAdvisor役モデルとしてのみ記録） | philosophy.md or README.md | 追記 | 中 |
| C7 | README.md に docs/framework/ への導線追加 | README.md | 導線 | 低（framework_draft承認後） |
| C8 | **品質モデルの矛盾解消**。philosophy.md「大切にするもの」= 対等3軸バランス vs axis-log-03 IK01 = 階層（品質>人>コスト）。構造差であり表現差ではない。品質セクション「妥協しない/過剰品質も目指さない」はIK01と整合済み → 「大切にするもの」側を階層モデルで補強する方向（人間承認必須） | philosophy.md | 矛盾解消 | 高（品質部分の補強として認識済み） |
| C9 | **Cokes一言定義の確定**。philosophy.md=バランス設計工学 / axis-log-03 IK02=知識整理工学 / specification.md=CQSE認知・品質システム工学 の三者不一致。C1と同時判断。**→ 解決案提案済み: `cokes_definition_layer_proposal.md`（4レイヤー分離統合）** | philosophy.md / specification.md | 意思決定 | 高（C1の前提） |

**実施順の提案:** `cokes_definition_layer_proposal.md` の人間承認 → C9・C8（philosophy.mdの一言定義・判断原則を確定）→ C1（`specification.md` をCokes仕様へ改訂）→ C3〜C6（正本のHandoff・関係・原則を更新）→ C7（導線確認）。C2（glossary）は反映済み。

`specification.md` を先に機械的にCQSE→Cokes置換してはならない。現行定義との関係を人間が確定した後、旧文書の問題提起を継承する改訂として扱う。

### 11.4 philosophy.md（原典）とKnowledge層の整合分析（2026-07-10 Advisor実施）

**矛盾あり2件・整合4件・原典に不在3件。**

**⚠矛盾（人間判断必須）:**

| # | philosophy.md（原典） | Knowledge層 | 判定 |
|---|---------------------|------------|------|
| M1 | 品質・コスト・人は**対等3軸**「ちょうどいいバランス」 | axis-log-03 IK01: **階層**（品質最上位→人が過剰品質ライン判断→コスト制約内最小化） | 構造的矛盾。ただし品質セクション「妥協しない+過剰品質NG」は階層モデルと同じ思想 → 原典の「大切にするもの」だけが古い可能性。**品質部分の補強=ここ**（→C8） |
| M2 | Cokes = 3軸バランスを探す道具（工学） | axis-log-03 IK02: Cokes = **知識整理工学**（暗黙知の形式化）/ specification.md: CQSE=認知・品質システム工学 | 一言定義が3ドキュメントで別物。進化の各時点が凍結された状態（→C9） |

**✓整合（そのまま使える）:**

| 項目 | 両者の記述 |
|------|-----------|
| 過剰品質NG | 原典「過剰品質も目指しません」= IK01「過剰品質は悪」 |
| AI=手段 | 原典「AIを使わない判断も正解」= IK02「AIは契機。主体は人間」 |
| 新理論を作らない | 原典「借りられるものは借りる」= axis-log-02「発見ではなく形式化」 |
| 最終成果=判断可能状態 | 原典「自ら判断し次へ受け渡せる」= cokes-design-philosophy.md「判断可能な状態が目標」 |

**△原典に不在（矛盾ではない。追記候補）:**

| 項目 | Knowledge層の根拠 | 対応 |
|------|------------------|------|
| Handoff=分岐点（終点ではない） | axis-log-03 IK07 | 原典Handoffセクションは「受け渡し状態」のみで方向は無矛盾。「分岐点」視点の追記のみ（→C3） |
| Cokes/Axis分離（憲法と法律） | axis-log-01 | 原典はAxisに一切言及なし（→C5） |

**結論:** 原典と蒸留知識の間に致命的な思想対立はない。M1は「品質部分の補強」（認識済み）として、
M2は名称・定義の時系列進化の未反映として、いずれも**原典の更新**で解消する方向。
framework_draft.mdはKnowledge層基準で書き、原典更新（C8・C9）は人間承認後の別タスク。

**Sonnetの禁止事項:** C1・C3〜C9の正本改訂をこの作業中に実施しない。framework_draft.md生成と、正本更新の依存関係・未解決点の記録のみを行う。
glossary.md は今回の作業で反映済みのため、以後の章ではその語彙を上位定義として扱う。`philosophy.md` / `specification.md` / `README.md` の改訂は、§11.3の人間承認後に別タスクとして実施する。
