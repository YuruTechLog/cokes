# Incident 001: replace_all によるパス誤置換

- 発生日: 2026-07-12
- 関連Lesson: `lessons/L001_path-replacement-verification.md`

---

## 何が起きたか

`gravity-tensor-model.md` → `terrain-magnetic-model.md` へのファイル名変更作業中、
`replace_all: true` で `gravity-tensor-model.md` を `terrain-magnetic-model.md` に全置換した。

結果、`docs/knowledge/axis-log-01/gravity-tensor-model.md`（knowledgeログ・触らない方針）への参照パスが
`docs/knowledge/axis-log-01/terrain-magnetic-model.md`（存在しないパス）に書き換えられた。

## なぜ起きたか

`replace_all` はファイル内の文字列パターンを機械的に全置換する。
「knowledgeのパスは触るな」という文脈・意図を持たない。

AIは「ファイル名だけ変えたい」という意図ではなく「文字列パターンに一致するものを全部変える」という操作を実行した。

## 影響範囲

- `archive/sonnet_work_procedure.md`（当時 L59・L78）: 存在しないパスへの参照が生成された
- ユーザー指摘で発覚 → 手動修正

## Approach Axisとの接続

「AIは全力でズレた答えを出す」の実例。
今回のズレ: コマンドの**意図**（ファイル名変更）ではなく**パターン**（文字列一致）に従った。

軸語彙が不足していた: 「knowledgeパスは不変」という制約をプロンプトに含めていなかった。
