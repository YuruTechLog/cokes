# Distillation Workflow: axis-log-04 / log08

## 基本情報
- DATASET: axis-log-04
- LOG: log08
- RUN_ID: 01

---

## 抽出した意味構造

### 構造1: AXIS 5軸の定義（確定版）
```
Intent     （目的）   : この指示で何を達成したいか
Abstraction（抽象度） : どのレベルの詳細さで答えてほしいか
Boundary   （範囲）   : どこまでを対象にするか（含む/除く）
Priority   （優先順位）: 複数要素があるときどれを優先するか
Direction  （方向）   : どの方向に向かって進めるか（改善/批判/創造等）
補助Sequence（順序）  : ステップの順番が重要な場合に追加
```

### 構造2: 5軸×木構造の対応
```
根  = Intent（なぜやるか）
幹  = Direction（どこへ向かうか）
太枝 = Boundary + Priority（何を・どれから）
細枝 = Abstraction（どの粒度で）
葉  = Sequence（どの順番で）
```

---

## 再利用単位

- 「AXIS 5軸の定義（確定版）」: axis-log-04の最重要成果物。記事・ハンドブック・設計書の核心として使用
- 「5軸×木構造」: 視覚的説明図の設計基盤
