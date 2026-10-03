# azookey_tabs

azooKey 向け QWERTY レイアウトの設計案と、その実装例をまとめたリポジトリです。

このリポジトリでは、**設計資料（Markdown）**と**実装例（Custard JSON）**を明確に分けています。

- `docs/` — ロングプレス候補やキー構成についての設計アイデア・検討資料
- `examples/` — 設計案を azooKey の Custard JSON に落とし込んだ実装例
- `LICENSE` — MIT License

設計資料に記載された候補がすべて実装例へ反映されているとは限りません。

## ディレクトリ構成

```text
.
├── docs/
│   ├── design/
│   │   ├── criteria.md
│   │   ├── en-qwerty-longpress.md
│   │   └── jp-qwerty-longpress.md
│   └── reference/
│       └── azookey-key-inventory.md
├── examples/
│   ├── en_qwerty/
│   │   ├── en_lower.json
│   │   ├── en_upper.json
│   │   ├── en_numbers.json
│   │   └── en_symbols.json
│   └── jp_qwerty/
│       ├── ja_lower.json
│       ├── ja_upper.json
│       ├── ja_numbers.json
│       └── ja_symbols.json
├── LICENSE
└── README.md
```

## 設計資料

`docs/design/` は、ロングプレス候補をどう設計するかについての資料です。

ここにある候補集合は、実装済みキーの一覧ではなく、候補を検討・比較するための設計案です。

主な考え方は次のとおりです。

- Unicode 上で単独のコードポイントを持つ文字を基本単位とする
- 不可視文字・制御文字・ゼロ幅文字などは対象外とする
- 候補の採否基準と並び順を分離する
- 実機の実装は参考情報として扱い、設計候補の母集団そのものにはしない
- `en_qwerty` と `jp_qwerty` では入力方式の違いを設計に反映する

## 実装例

`examples/` は、設計案を azooKey の Custard 形式へ具体化した実装例です。

JSON は `custard_version: 1.2` を使用します。

- `en_*` — `input_style: direct`
- `ja_*` — `input_style: roman2kana`
- レイアウトは `grid_fit`
- ロングプレス候補は `variations` に定義

実装例は設計資料の検証・試用を目的とするものであり、設計資料との完全一致を保証するものではありません。

## 設計と実装の関係

```text
設計アイデア
    │
    ├── docs/design/criteria.md
    ├── docs/design/en-qwerty-longpress.md
    └── docs/design/jp-qwerty-longpress.md
    │
    ▼
具体化・試作
    │
    └── examples/
        ├── en_qwerty/
        └── jp_qwerty/
```

設計上の候補を追加・削除・変更しても、それが自動的に JSON の実装へ反映されるわけではありません。

## ライセンス

[MIT License](LICENSE)

Copyright (c) 2026 skt001
