# azookey_tabs

azooKey 向けの QWERTY キーボードレイアウト定義と、ロングプレス候補の設計資料をまとめたリポジトリです。

英語（en）と日本語（ja）の QWERTY レイアウト JSON、およびロングプレス候補の設計基準・完成候補一覧を公開しています。

## 内容

### レイアウト JSON

レイアウトは `tabs/` 以下に、英語・日本語それぞれのディレクトリへ整理しています。

| パス | 説明 |
|------|------|
| `tabs/en_qwerty/en_lower.json` | 英語 QWERTY・小文字 |
| `tabs/en_qwerty/en_upper.json` | 英語 QWERTY・大文字 |
| `tabs/en_qwerty/en_numbers.json` | 英語 QWERTY・数字 |
| `tabs/en_qwerty/en_symbols.json` | 英語 QWERTY・記号 |
| `tabs/jp_qwerty/ja_lower.json` | 日本語 QWERTY・小文字 |
| `tabs/jp_qwerty/ja_upper.json` | 日本語 QWERTY・大文字 |
| `tabs/jp_qwerty/ja_numbers.json` | 日本語 QWERTY・数字 |
| `tabs/jp_qwerty/ja_symbols.json` | 日本語 QWERTY・記号 |

### 設計資料

| パス | 説明 |
|------|------|
| `docs/design-criteria.md` | ロングプレス候補の設計基準（統合版） |
| `docs/en-qwerty-longpress-all.md` | 英語ロングプレス候補の完成一覧 |
| `docs/jp-qwerty-longpress-all.md` | 日本語ロングプレス候補の完成一覧 |
| `docs/azookey-key-inventory.md` | azooKey の物理キー一覧（実在キーの確認用） |

## レイアウト JSON について

各 JSON は azooKey の Custard 形式（`custard_version: 1.2`）に準拠しています。

- `en_*` : `input_style: direct`（直接入力）
- `ja_*` : `input_style: roman2kana`（ローマ字かな変換）
- キー配置は `grid_fit` を使用しています。
- ロングプレス候補は各レイアウトの `variations` に定義されています。

英語と日本語では入力方式が異なるため、ロングプレス候補の設計方針にも意図的な差があります。詳細は設計資料を参照してください。

## 設計方針

ロングプレス候補は、単に既存キーボードの見た目を再現することを目的とせず、基本キーから利用価値のある文字・記号へ直接到達できる候補集合として設計しています。

主な方針は次のとおりです。

- 候補は原則として Unicode 上で単独のコードポイントを持つものを基準とする
- 不可視文字・制御文字・ゼロ幅文字は対象外とする
- 候補の採否基準と並び順を分離する
- 並び順は原則 Unicode コードポイント順とする
- 実機（iOS 等）の現行実装は参考情報として扱い、候補集合の母集団にはしない
- 英語と日本語では、`direct` / `roman2kana` という入力方式の違いを設計に反映する

詳細な採否基準と候補一覧については、`docs/` 以下の資料を参照してください。

## ディレクトリ構成

```text
.
├── tabs/
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
├── docs/
│   ├── design-criteria.md
│   ├── en-qwerty-longpress-all.md
│   ├── jp-qwerty-longpress-all.md
│   └── azookey-key-inventory.md
├── LICENSE
└── README.md
```

## ライセンス

[MIT License](LICENSE)

Copyright (c) 2026 skt001
