# azookey_tabs

azooKey 向けの QWERTY キーボードレイアウト定義と、ロングプレス候補の設計資料をまとめたリポジトリです。

英語（en）と日本語（ja）の両方に対応したレイアウト JSON と、候補選定の基準・一覧を公開しています。

## 内容

| パス | 説明 |
|------|------|
| `layouts/en/` | 英語 QWERTY レイアウト（lower / upper / numbers / symbols） |
| `layouts/ja/` | 日本語 QWERTY レイアウト（lower / upper / numbers / symbols） |
| `docs/design-criteria.md` | ロングプレス候補の設計基準（統合版） |
| `docs/en-qwerty-longpress-all.md` | 英語ロングプレス候補の完成一覧 |
| `docs/jp-qwerty-longpress-all.md` | 日本語ロングプレス候補の完成一覧 |
| `docs/azookey-key-inventory.md` | 物理キー一覧（実在キーの確認用） |

## レイアウト JSON について

各 JSON は azooKey の Custard 形式（`custard_version: 1.2`）に準拠しています。

- `en_*` : `input_style: direct`（直接入力）
- `ja_*` : `input_style: roman2kana`（ローマ字かな変換）

ロングプレス候補（`variations`）は設計資料に基づいて設定されています。

## 設計方針の概要

- 候補は原則として Unicode 上で単独のコードポイントを持つものを基準とする
- 不可視文字・制御文字・ゼロ幅文字は対象外
- 並び順は原則 Unicode コードポイント順
- 実機（iOS 等）の現行実装は参考情報として扱い、候補集合の母集団にはしない

詳細は [`docs/design-criteria.md`](docs/design-criteria.md) を参照してください。

## ライセンス

[MIT License](LICENSE)

Copyright (c) 2026 skt001
