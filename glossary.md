# Cokes Glossary

> Cokesで使用する用語の正本。
> 背景となる価値観は `philosophy.md`、Cokes版の仕様は `specification.md` を参照する。
> Approach Axis固有の用語は `docs/framework/approach-axis/glossary.md` を正本とする。

---

## 1. Cokesの中核用語

### Cokes

**Cokes（Cognitive Key-Output Engineering System）**は、人間が道具・仕組みを選択して用いる工程で、目的に必要なKey-Outputを、人・品質・コストの関係を保って設計・運用する実践体系。

AIは利用手段の一つであり、CokesそのものをAI活用に限定しない。

### Key-Output

目的達成に必要なKey-Qualityを満たし、過剰な品質・作業・認知負荷を増やさず、次の判断または工程で利用できる成果。

最終成果だけでなく、次の意思決定を左右する工程成果も含む。一般英語の *key output* ではなく、Cokes内の定義語としてハイフン付きで表記する。

### Key-Quality

Key-Outputの受入れ可否を決める、目的に対して必要十分な品質条件。

品質を無条件に最大化することではない。コストを理由に黙って下げることもせず、人が目的に照らして定める。

### Handoff

責任を持つ人が実行の手を離しても、定めた目標・Key-Quality・前提を維持したまま工程を任せられる状態。

成果物や判断記録の受渡しは、その状態をつくるための一部であり、Handoffそのものではない。前提が変われば、Handoff条件を再評価する。

### Human（人）

目的、評価軸、前提の採否、リスク受容を決め、最終的な責任を持つ主体。

人への負荷は下げる対象であり、許容量を超えてオーバーフローする状態は許容しない。

---

## 2. 知識と成果物

### Knowledge Asset

再利用可能な知識資産。記事、テンプレート、設計資料、チェックリスト、会話ログの蒸留結果、判断記録などを含む。

### Distillation

会話・試行錯誤・経験から、再利用可能なKnowledge Assetを抽出・整理するプロセス。

### Repository

Knowledge Asset、Skill、テンプレート、設定、コード、判断記録などを管理する保存構造。

### Knowledge Management

知識を生成・蓄積・共有・再利用するための体系。

Cokesは知識管理の考え方を活用するが、Cokes自体をKnowledge Management Frameworkと同義にはしない。

### Abstraction（抽象化）

複数の具体例から本質を抽出し、再利用可能な知識へ変換する行為。

### External Memory

人間の外部に存在する記憶。ノート、Repository、Skill、Knowledge Assetなどを含む。

Cokesでは、Repositoryは判断・前提・成果物を後から参照できる外部記憶として機能する。

### Versioning

成果物、前提、設定、判断記録などの変更履歴を管理し、ある時点の状態を復元可能にすること。

### Traceability

目的、前提、用語、判断、成果物、評価結果の関係を追跡可能にすること。

---

## 3. 工程と実行単位

### Skill

選んだ道具・仕組みで再利用可能な実行単位。入力、参照正本、出力、適用範囲、制約、受入条件、失敗時の扱いを明確にする。

AIを利用するSkillは**AI向けSkill**と呼ぶ。AI向けSkillは、AIへの入力、実行、評価、Handoffを担うが、Skill全体をAI専用とはしない。

### Workflow

人と、選択した道具・仕組みが、判断・例外・再試行・Handoffを含めて成果を作る作業の流れ。

### Pipeline

入力・参照正本・実行手段・成果物をつなぐ処理の流れ。

Workflowが運用と判断を含む視点であるのに対し、Pipelineは成果物と処理の流れに注目する。

---

## 4. AI利用時の概念

### AI

推論、生成、抽出、変換、実行などを支援する利用手段の一つ。Cokesでは、Key-Outputをより確実に満たし、人への追加負荷が許容量を超えない場合に選択する。

### LLM

自然言語を扱い、指示に従って推論・生成・変換などを行う大規模言語モデル。

### Context

AIがタスクを実行するために参照する情報の総体。Promptだけでなく、Skill、Knowledge Asset、Memory、実行条件など、AIの出力に影響する情報を含む。

### Context Engineering

AIを利用手段として選んだ場合に、目的に応じたContextを設計・構築・供給する設計手法。

Cokes全体の定義ではなく、AI利用時の重要な設計手法として扱う。

### Prompt

AIへ直接与える自然言語による指示。PromptはContextを構成する一要素であり、Context全体を表すものではない。

### Context Window

AIが一度に参照・処理できる入力範囲。Context Engineeringにおける重要な制約条件。

---

## 5. 認知に関する概念

### Cognitive Load（認知負荷）

人が情報を理解・処理する際に必要となる認知資源の量。

Cokesでは、人への負荷を設計対象として扱う。負荷を下げる一方、許容量を超えてオーバーフローする状態を許容しない。

### Working Memory（ワーキングメモリ）

人が短時間に保持・処理できる情報領域。

### Cognitive Offloading（認知的オフローディング）

記憶や思考の一部を外部の道具・仕組みへ委ね、人の認知負荷を軽減する考え方。

RepositoryやKnowledge Assetは、そのための仕組みとして機能する。

### Distributed Cognition（分散認知）

人・道具・環境を含めた全体で認知活動を行うという考え方。

Cokesでは、人、Repository、選択した道具・仕組みを含む全体を設計対象として捉える。
