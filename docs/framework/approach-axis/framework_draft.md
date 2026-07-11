# Approach Axis Framework — 骨子ドラフト

- 生成: Sonnet（Executor）
- 生成日: 2026-07-11
- 手順書: `sonnet_work_procedure.md`
- ステータス: ドラフト（人間レビュー待ち）

---

## 序文候補（動機）

> AIとの対話が「ガチャを引いている感覚」から脱却できている時、何が起きているか。
>
> 人間が「何を求めるか」を決めてから来る。用語を先に固める。主体とスコープを宣言する。ズレたら即修正する。
>
> うまくいく時は必ず「何を、どこまで、どの方向に」が決まっている。
> Approach Axisはその「決め方」を再現可能にする。

---

## 第1章: Approach Axisとは何か

**目的:** Approach Axisの定義・起源・命名理由を示し、何を解決するフレームワークかを明確にする。

- **定義の掲載**
  人間の判断軸の「範囲」とAIのベクトル場の「範囲」が近づき重なりうる領域を動的に探索・調整するための運用ツール。
  核：「近づくという動作を操作化」し、成功と失敗を明確に定義して再現可能な判断プロセスを作る。
  （参照: `axis-log-01/approach-axis-framework.md` §定義）

- **起源の一言の掲載**
  「人間の軸にも範囲があって、論理和の部分を作ろうぜってかんじから？」
  3要素: 人間の軸=範囲 / AI=ベクトル場 / Axis=両者の論理和（重なり領域）を扱う道具。
  （参照: `axis-log-01/approach-axis-framework.md` §起源）

- **「近づく動作の操作化」の説明**
  動詞を核に置いた設計: 動詞→操作できる・失敗を定義できる。
  Approach Failure = ハルシネーション という定義が自然に導かれる。
  動的調整（近づく/離れるのダイナミクス）を含む。
  （参照: `axis-log-01/approach-axis-framework.md` §命名の理由）

- **何を解決するか**
  AIは自律的軸生成不可（ベクトル空間は方向を持つが基準軸がない）。
  軸は構造的に人間が保持せざるを得ない。
  Approach Axisはこの構造的差異を前提とし、人間の軸をAIに伝えるための操作言語を提供する。
  解決する問題: AIへの指示が「なんとなく効いた呪文」のまま再現不能になること。
  （参照: `axis-log-01/gravity-tensor-model.md` §モデルの基本前提 / `axis-log-01/axis-words-magnet-map.md` §実務での使い方）

- **コアメッセージ（確定版）の掲載**
  > 「AIは全力でズレた答えを出す機械。
  >  何を求めているかを教えてあげないと、全力でズレる。
  >  教え方の設計 = AXIS」
  （参照: `axis-log-04/integrated_knowledge.md` §KN-MASTER-01）

- **CLEARとの差異（位置づけ明確化）**
  CLEAR: 何をどう書くか（形式層） / AXIS: どこへ向かわせるか（意味空間層）。
  競合なし。異なるレイヤー。
  （参照: `axis-log-04/integrated_knowledge.md` §KN-MASTER-02）

---

## 第2章: なぜ効くのか — 重力場テンソルモデル

**目的:** Approach Axisが機能する理由を「操作のための解釈モデル」として示す。実装の説明モデルではないことを明示する。

- **第一原理の掲載**
  「AIは高次元ベクトル空間で構築されている。この特性は消せない」
  この前提から導かれる構造的差異: 人間=条件付き自律軸生成可 / AI=自律的軸生成不可。
  → 軸は人間が保持せざるを得ない（価値観論ではなく構造論）
  （参照: `axis-log-01/gravity-tensor-model.md` §モデルの基本前提）

- **確立した3要素の表を掲載**
  多様体（AI内部の意味空間の形）/ 傾斜装置（軸語彙の作用）/ 地形崩壊（ハルシネーション）の3要素表。
  ポイント: 軸語彙は地形を「書き換える」のではなく「傾斜をつける」。
  傾斜が強すぎる → 地形崩壊（ハルシネーション）。
  （参照: `axis-log-01/gravity-tensor-model.md` §重力場テンソルモデル（確立した3要素））

- **「操作のための解釈モデルであり実装の説明モデルではない」の明示**
  AI研究者が扱うメカニズム層（Attention重み・確率分布の変形）とは目的が違う。
  精度基準: 「なぜ今これが崩れたか」を言語化し、操作の判断ができること。
  「測れないが方向は予測できる」——それがこの層の実用的な精度。
  （参照: `axis-log-01/gravity-tensor-model.md` §このモデルの位置づけ）

- **論文裏付けマップの掲載（axis-log-04確定版）**
  AXIS概念と対応理論の対応表: EBM（重力場テンソルモデル）/ 幾何学的深層学習（意味空間の構造）/ Scale-Space理論（抽象度軸）/ Diffusion Models Beat GANs - OpenAI 2021（構造先・雰囲気後）
  （参照: `axis-log-04/integrated_knowledge.md` §T01 §論文裏付けマップ）

- **比喩体系の使い分けガイドの掲載**
  7種のメタファーと各説明場面の対応表:
  重力場テンソル（傾斜・引力の方向説明時）/ 食紅（広がり・浸透の説明時）/ 電波フィルター（目的周波数選択の説明時）/ カラオケボーカル消し（ハルシネーション除去の説明時）/ mp3波形（AI内部ベクトルの説明時）/ 木構造（根→幹→枝の構造説明時）/ 露光メタファー（事前設計の必要性説明時）。
  （参照: `axis-log-04/integrated_knowledge.md` §T02）

> **[人間判断]** 比喩の使い分けガイドを第2章（理論）に置くか第10章（Tips）に置くか。
> 現状: 第2章に「ガイド表のみ」を掲載、第10章 §10.3 で実践的用法を展開する案で仮置き。

---

## 第3章: 3層構造の中での生息域

**目的:** Approach Axisが研究層・操作層に対してどの層に位置するかを示し、独自領域を明確にする。

- **研究層/解釈層/操作層の3層図を掲載**
  研究層（Activation Steering / SAE / Mechanistic Interpretability）→ 基板として存在。矛盾しないが使わなくても成立。
  解釈層（重力場テンソルモデル・Approach Axisの生息域）→ 研究層の事実を「操作の判断言語」に翻訳した層。
  操作層（実務）→ 軸語彙を選ぶ・プロンプトを設計する・失敗を診断する。
  （参照: `axis-log-01/gravity-tensor-model.md` §研究層との関係）

- **研究層との対応表を掲載（2026年時点）**
  Approach Axis概念と研究層の対応・一致度（★★★★★〜★★☆☆☆）の表。
  軸語彙が傾斜をつける ↔ Activation Steering（★★★★★）/ 地形崩壊=ハルシネーション ↔ Truthfulness Steering（★★★★☆）/ モデル別崩壊方向 ↔ モデル別Steering効果研究（★★★☆☆）/ 操作判断言語 ↔ 研究層では扱わない・独自領域（★★☆☆☆）。
  （参照: `axis-log-01/gravity-tensor-model.md` §研究層との関係 §研究層の対応概念）

- **独自領域の明示**
  「ユーザーの操作判断言語を作る」という設計は2026年時点で研究・実務ともに少数。
  Mechanistic Interpretability → Prompt Engineeringを橋渡しする論文が2026年に出始めたが、目的は「研究知見を実装に落とす」であり「解釈層の独立設計」ではない。
  Approach Axisはその空白を埋める位置にある。
  （参照: `axis-log-01/gravity-tensor-model.md` §研究層との関係 §結論）

> **[人間判断]** arXiv:2601.02896等の2026年研究参照を実装ドキュメントに含めるか。
> 素材の仮置き: 含める + 「2026年時点」の断り必須。
> 鮮度が落ちる情報のため、更新方針も合わせて検討が必要。

---

## 第4章: フレームワーク構成 — 4層構造

**目的:** Approach Axisの4層構造と運用原理を示す。各層の役割と連携を理解できるようにする。

- **4層構造の表を掲載**
  Layer1 Axis Words（操作を指示する言語語彙）
  Layer2 Magnet Map（各語彙の効力優先度）
  Layer3 Model Profile（モデル別語彙効力差の参照表）
  Layer4 Templates（実行シーケンスの雛形）
  （参照: `axis-log-01/approach-axis-framework.md` §4層構造）

- **運用原理の掲載**
  L1命令を作る → L2で優先度を決める → L3でモデル特性に合わせる → L4で実行。
  各層は独立ではなく流れとして機能する。
  （参照: `axis-log-01/approach-axis-framework.md` §4層構造 §運用原理）

- **Axis三層構造（操作/説明/思想）の掲載**
  操作層（Axis Words・Magnet Map・Templates）: 実務で直接使う層。
  説明層（重力場テンソルモデル）: なぜ効くかを言語化する層。
  思想層（Cokesとの接続）: Axisを生む設計思想の層。
  この3層はAxis全体の構造であり、上記4層（L1〜L4）とは別の切り口。
  （参照: `axis-log-02/integrated_knowledge.md` §KN43 Axis三層構造）

- **形式化の価値についての説明**
  Cokes/Axisの独自性は「発見」ではなく「形式化」。
  概念は学術領域に存在済み。暗黙知として実践済みの人もいる。
  価値: 誰でも再現可能な形にすること = 形式化。
  （参照: `axis-log-02/integrated_knowledge.md` §横断テーマ §2.「形式化の価値」）

---

## 第5章: 軸語彙リファレンス

**目的:** 軸語彙の5分類・磁力強度マップ・モデル別特性を参照可能な形で提供する。実務での使い方も示す。

- **5分類+補助（順序）の表を掲載（AXIS5軸確定版）**
  起点（Intent）/ 抽象度（Abstraction）/ 境界（Boundary）/ 優先順位（Priority）/ 方向性（Direction）/ 順序（Sequence・補助）。
  各分類の役割・例語彙を一覧化。
  「順序が補助の理由」: AIは複数軸語彙を同時処理しにくい。順序語で段階的に刺すと軸同士の衝突を防げる。
  （参照: `axis-log-01/axis-words-magnet-map.md` §軸語彙5分類 / `axis-log-04/integrated_knowledge.md` §T01 §確定5軸）

- **磁力強度マップの掲載**
  効力が強い順: 方向性 > 境界 > 抽象度 > 起点 > 優先順位 > 順序。
  （参照: `axis-log-01/axis-words-magnet-map.md` §磁力強度マップ）

- **「条件依存で変動」の注意書きの掲載**
  タスクの性質（抽象/具体）で優先度が入れ替わる。モデルのチューニング状態で特性が変わる。
  この順番は「傾向」であり固定ではない。
  （参照: `axis-log-01/axis-words-magnet-map.md` §磁力強度マップ §重要）

- **モデル別磁力特性テーブルを掲載（2026年時点観察）**
  Claude（最強軸: 抽象度 / 抽象度を高めに設定。具体的すぎると効果が落ちる）
  GPT（最強軸: 起点 / 目的を明確に。境界は弱めでいい）
  Gemini（最強軸: 境界 / 境界を明確に。目的は弱めでいい / 崩壊閾値が低い）
  Copilot（最強軸: 優先順位 / 優先順位を明確に。抽象方向が弱い）
  （参照: `axis-log-01/axis-words-magnet-map.md` §モデル別磁力特性）

- **実務での使い方3点の掲載**
  1. モデルを選ぶ基準として使う（概念設計→Claude / タスク完遂→GPT / 制約内→Gemini / コーディング→Copilot）
  2. プロンプト設計時の優先語彙をモデルで変える
  3. 磁力強度マップを使った優先度設定（方向性先固定→境界で範囲限定→抽象度で粒度調整）
  （参照: `axis-log-01/axis-words-magnet-map.md` §実務での使い方）

> **[人間判断]** モデル別特性テーブルは2026年時点の観察。バージョン追従の更新運用（誰がいつ更新するか）は素材に記述なし。
> TODO: 更新運用方針の定義が必要。

---

## 第6章: 操作プリミティブ7種

**目的:** Approach Axisの操作命令の基本単位（プリミティブ）を一覧化し、各プリミティブの使い方を示す。

- **7種の表を掲載**
  Position（AI出力を人の軸に対してどれだけ寄せるか）
  Magnitude（AI出力の重み付け）
  Constraint（不可侵領域・禁止ルールの適用）
  Filter（出力フィルタ適用）
  Blend（複数案の混合比率調整）
  Retry（再アプローチ戦略と回数）
  Lock（合意領域を固定して以降変更しない）
  （参照: `axis-log-01/approach-axis-framework.md` §操作プリミティブ（7種））

- **コマンド例の位置づけの明記**
  表中のコマンド例（`setPosition(offset: +0.2)` 等）は擬似コードとして掲載。
  実装時はプロジェクトごとに定義。
  （参照: `axis-log-01/approach-axis-framework.md` §操作プリミティブ）

> **[人間判断]** コマンド例（`setPosition(offset: +0.2)` 等）は擬似コードか実装対象か。
> 素材からは判断不能のため仮置き: 「表記は擬似コード。実装時はプロジェクトごとに定義」と注記。
> TODO: 実装対象として扱う場合の型・インターフェース定義が必要。

---

## 第7章: 実行フローと状態モデル

**目的:** Approach Axisを使った実際の作業手順（5段階フロー）と、各結果の判定基準を示す。

- **実行フロー5段階の掲載**
  1. マッピング（人の軸レンジ × AIプロファイルを可視化）
  2. プランニング（段階（小/中/大）と操作コマンド列を決定）
  3. 実行（操作プリミティブを適用してAI出力を取得）
  4. 評価（品質スコア + 人的レビューで判定）
  5. 記録とHandoff（判定ラベルと次アクションをドキュメント化）
  （参照: `axis-log-01/approach-axis-framework.md` §実行フロー（短縮））

- **状態モデルの図を掲載**
  ```
  Idle → Plan → Execute → Evaluate
                                ├─ Success（品質≥90 AND 人的レビュー合格）→ Lock → Handoff
                                ├─ Partial（70≤品質<90）→ 再アプローチ計画
                                └─ Failure（品質<70 OR ハルシネーション検出）→ 停止・原因分析・不可侵強化
  ```
  （参照: `axis-log-01/approach-axis-framework.md` §状態モデル）

- **評価指標3種の表を掲載**
  品質スコア（0–100 / 自動評価+人的レビューで算出）
  信頼度（0–1 / モデル内部確信度）
  判定ラベル（3種: Success / Partial Success / Approach Failure）
  （参照: `axis-log-01/approach-axis-framework.md` §評価指標）

> **[人間判断]** 品質スコア閾値（90/70）の算出方法が素材に未定義。
> TODO: 「自動評価+人的レビューで算出」の具体的な算出方法・評価基準の定義が必要。

---

## 第8章: 失敗モードと診断

**目的:** Approach Failureの定義と即停止プロトコル、モデル別崩壊特性と対処を示す。失敗を診断・回復できるようにする。

- **Approach Failure = ハルシネーションの定義の掲載**
  重力場テンソルモデルから自然に導かれる定義。
  軸語彙による傾斜が強すぎた結果の地形崩壊 = Approach Failure。
  状態モデルにおける Failure（品質<70 OR ハルシネーション検出）と対応。
  （参照: `axis-log-01/approach-axis-framework.md` §Approach Failure / `axis-log-01/gravity-tensor-model.md` §Approach Axisとの接続）

- **即停止プロトコルの掲載**
  即停止 → 根拠トレース → 不可侵領域の再強化 → 再設計の4ステップ。
  （参照: `axis-log-01/approach-axis-framework.md` §Approach Failure（ハルシネーション）の扱い）

- **失敗モード一覧表を掲載**
  ハルシネーション: AIのベクトルが人の軸外へ逸脱 → 即停止→根拠トレース→不可侵領域強化→再設計
  過剰適合: 過度なプロンプト制約で多様性喪失 → 制約緩和→複数案取得→人的評価導入
  コスト超過: 反復回数が多すぎる → 段階的閾値を厳格化→仕組み化検討
  （参照: `axis-log-01/approach-axis-framework.md` §失敗モードと対処）

- **モデル別崩壊特性と対処の表を掲載**
  Gemini（意図方向が崩れやすい → 境界重視・目的は弱め）
  Claude（具体すぎると効果減 → 抽象度を保つ）
  GPT（境界が弱くてもある程度機能 → 起点を明確にすれば十分）
  Copilot（抽象方向に弱い → 優先順位・局所指示で操作）
  補足: 崩壊閾値は測れないが方向は構造で予測できる。「測れない」と「予測できない」は別。
  （参照: `axis-log-01/gravity-tensor-model.md` §モデル別崩壊特性 / `axis-log-01/axis-words-magnet-map.md` §モデル別磁力特性）

- **AI誤認リスクの記載**
  AIがCokes/Axis説明を出力した場合、人間が必ず検証する。
  観察済みインシデント: 「Axisのプランフェーズ」ハルシネーション（Axisにフェーズ構造は存在しない）。
  対策: 固定事実を先に明示してから使用。
  （参照: `axis-log-03/integrated_knowledge.md` §IK12）

---

## 第9章: 運用ルールとCokes体系内での位置づけ

**目的:** Approach AxisをCokes体系の中で正しく使うための運用ルールと、Fable/Axis/Cokes三者関係を示す。

- **Fable/Axis/Cokes三者関係図の掲載**
  ```
  Cokes（上位体系 = 知識整理工学）
    ├─ Axis（AI側の未知を扱う操作体系）
    │    └─ 具体実践 → Fable本家
    └─ Fable（人間の未知を扱うTips集）
  ```
  役割分担: Fable=自分が何を知らないかを確認するTips集 / Axis=人間軸レンジ×AIベクトル場の操作体系 / Cokes=両者を包含する知識整理の全体論。
  （参照: `axis-log-03/integrated_knowledge.md` §IK04）

- **Handoff = 分岐点（終点ではない）の説明**
  定義: Handoffは知識移転の「終点」ではなく「分岐点」。
  知識が移転された瞬間に、次の処理（循環の次フェーズ）が始まる起点。
  「何をする/しない」が判断できる状態を渡す。
  （参照: `axis-log-03/integrated_knowledge.md` §IK07 / `axis-log-01/cokes-design-philosophy.md` §Cokes設計思想）

- **外部ツール前Axis語彙必須ルールの掲載**
  外部LLM/ツール使用前にAxis語彙を明示的に与える。
  語彙なし → 汎用地形走行 → Cokesの文脈外に逸脱（暴走）。
  適用: Gemini / Claude 以外のAIへの問い合わせ全般。
  観察済みインシデント: Gemini暴走×3回（すべてAxis語彙なしが原因）。
  （参照: `axis-log-03/integrated_knowledge.md` §IK10 §IK12）

- **AI自身によるフレームワーク誤認リスクの記載**
  AIが出力したCokes/Axis説明は人間が必ず検証する。
  CopilotがCokesとAxisを混同するインシデント発生 → 明示的な分離確定の経緯。
  （参照: `axis-log-01/cokes-design-philosophy.md` §CokesとApproach Axisの関係 / `axis-log-03/integrated_knowledge.md` §IK12）

- **Axis三層構造（操作/説明/思想）の掲載**
  操作層（Axis Words・Magnet Map・Templates）: 実務で直接使う層。
  説明層（重力場テンソルモデル）: なぜ効くかを言語化する層。
  思想層（Cokesとの接続）: Axisを生む設計思想の層。
  （参照: `axis-log-02/integrated_knowledge.md` §KN43）

- **「憲法と法律」の関係の説明**
  Cokes = 工学判断モデル（品質・コスト・人のバランスを設計する）。
  Axis = Cokesを実現するための道具。
  関係: 「憲法（Cokes）と法律（Axis）の関係に近い」。
  Axisを Cokesに吸収させると各体系の純度が下がる（NG）。
  （参照: `axis-log-01/cokes-design-philosophy.md` §CokesとApproach Axisの関係 / `axis-log-03/integrated_knowledge.md` §IK03）

- **設計者倫理の記載**
  「AIがバカだから」= 責任転嫁。
  正しい認識: 「自分の設計が不足していた」。AIの限界は仕様。設計者の責任は設計。
  （参照: `axis-log-04/integrated_knowledge.md` §KN-MASTER-03）

---

## 第10章: テンプレート集と実践Tips

**目的:** 運用カード・Handoffテンプレート・日本語3原則・画像生成AXIS適用・パーツ単位発注パターンをそのまま使える形で提供する。

### §10.1 運用カードとHandoffテンプレート

- **運用カードをそのまま掲載**
  ```
  目的：
  人の軸レンジ：
  AIプロファイル：
  操作コマンド：（例: applyFilter(factualOnly); setPosition(+0.1)）
  段階： 小／中／大
  評価指標： 品質スコア、信頼度
  判定： Success / Partial / Failure
  次アクション：
  ```
  （参照: `axis-log-01/approach-axis-framework.md` §運用カード）

- **Handoffテンプレートをそのまま掲載**
  7セクション構成（背景と目的 / 人の軸レンジ / AIプロファイル / 実施したApproach / 評価結果 / 次アクション / 履歴）。
  （参照: `axis-log-01/approach-axis-framework.md` §Handoffテンプレート）

- **Layer4 Templatesとの対応の説明**
  運用カード = Layer4 Templates の実践形式。
  Handoffテンプレート = Lock → Handoff フェーズで出力するドキュメント。

### §10.2 日本語3原則

- **日本語×AXISの構造的親和性の説明**
  日本語の3重問題（同音異義語 / 主語省略 / 文脈前提）によりAXIS必要性が高まる。
  （参照: `axis-log-04/integrated_knowledge.md` §T03）

- **日本語3原則の掲載**
  1. 主語明示（「私が」「AIが」省略しない）
  2. 文末核心語彙（最重要概念を文末に配置）
  3. 軸語彙前置（応答方向を決める語彙を文頭付近に置く）
  （参照: `axis-log-04/integrated_knowledge.md` §T03 §日本語3原則（AXIS実践））

### §10.3 画像生成AXIS適用

- **黄金律「構造が先、雰囲気は最後」の説明**
  3重一致: 画家の直感（デッサン→色塗り）/ AI数理（前半ステップ→後半ステップ）/ Prompt設計（構造語彙→雰囲気語彙）。
  （参照: `axis-log-04/integrated_knowledge.md` §T04 §黄金律の3重一致）

- **3レイヤー設計の掲載**
  Layer1 Skeleton: 構図・ポーズ → ControlNetで物理固定
  Layer2 Material & Lighting: 素材感・光源 → Prompt Scheduling前半
  Layer3 Aesthetic Modulation: 画風・スタイル → LoRA後付け / Prompt Scheduling後半
  （参照: `axis-log-04/integrated_knowledge.md` §T04 §3レイヤー設計）

- **Prompt Scheduling構文の掲載**
  ```
  [構造語彙:雰囲気語彙:0.4]
  ```
  （参照: `axis-log-04/integrated_knowledge.md` §T04 §実装構文）

- **インシデントパターンの掲載**
  「構造が先」を無視したLoRA適用 → Layer1未完成でLoRA（Layer3）を先に適用すると出力が崩れる。
  対策: 3レイヤー設計の順序を厳守。
  （参照: `axis-log-04/integrated_knowledge.md` §I03）

### §10.4 パーツ単位発注パターン（Executor×Advisor実践）

- **Executor×Advisor協調構造の説明**
  Executor（Sonnet等）: 実行・生成担当。
  Advisor（Fable5等）: 骨格抽出・判断基準の事前定義担当。
  Axis = AIの理解を人間側に寄せる唯一の構造。
  （参照: `axis-log-02/integrated_knowledge.md` §KN18 §Phase C: 協調構造発見期）

- **「指揮する人」モデルの掲載**
  作る人 → 指揮する人。最適ツールを配置・監督する設計者ポジション。
  AIを使うことが目的でなく、結果を出すことが目的。
  （参照: `axis-log-04/integrated_knowledge.md` §KN-MASTER-04）

- **ハイブリッド最強モデルの掲載**
  推論・分析: Claude Pro（クラウド）/ 画像素材: Stable Diffusion（ローカル）/ バナー合成・テキスト配置: Python+Playwright（コード）。
  原則: 「決定権はコードに」「素材だけAIに」。
  （参照: `axis-log-04/integrated_knowledge.md` §T06）

- **骨格→AI統合ルートの掲載**
  1. 人間が骨格を抽出（必要十分条件・判断基準・転換点・疑問点）
  2. AIが骨格に肉付け（統合・言語化・構造化・整形）
  3. 人間が確認（品質チェック・過剰品質除去・正確性検証）
  問題の根拠: AIは言語パターンを圧縮する → 非言語の構造は捨象される → 外殻のみ残る（骨格欠落）。
  （参照: `axis-log-03/integrated_knowledge.md` §IK09）

---

## 未解決議題

- **TODO-1** [第5章] モデル別特性テーブルの更新運用方針（誰がいつ更新するか）の定義が必要。
- **TODO-2** [第6章] 操作プリミティブのコマンド例が擬似コードか実装対象かの確定。実装対象とする場合の型・インターフェース定義が必要。
- **TODO-3** [第7章] 品質スコア閾値（90/70）の具体的な算出方法・評価基準の定義が必要。
- **Axis実装関連（継続議題）:** プロンプト文化通史の体系的記録（Cokes/Axisが担い手として機能できるか）。（参照: `axis-log-02/integrated_knowledge.md` §未解決議題）

---

## ⚠ 矛盾メモ

素材間の記述食い違いなし。

ただし以下はKnowledge層と正本層（Cokes正本）の間の差異（このドキュメントのスコープ外。`sonnet_work_procedure.md` §11.3参照）:
- Cokes一言定義の3ドキュメント不一致（M2）
- 品質モデルの対等3軸 vs 階層構造の表現差（M1）
これらは framework_draft.md 生成後にCokes正本層の更新（C8・C9）で解消する人間判断事項。

---

## 生成メモ

- 追加参照ファイル: なし（手順書 §4 テーブルの7ファイルのみで骨子を完結）
- [人間判断]件数: 5件（§3 研究参照 / §5 更新運用 / §6 擬似コード確認 / §7 閾値算出 / §2 比喩配置）
- TODO件数: 3件（TODO-1〜3）
- chat-archives 参照: なし
