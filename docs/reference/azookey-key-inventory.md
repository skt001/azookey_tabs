# azooKey 実装例キー一覧

この資料は `examples/` 以下の JSON に実際に存在するキーを確認するための補助資料です。

設計資料とは異なり、こちらは**実装例側の状態を確認するための資料**です。

`[+var]` は、そのキーにロングプレス候補（`variations`）が実装されていることを示します。

## en_qwerty

### lower

- y=0: q w e r t y u i o p
- y=1: a s d f g h j k l
- y=2: z x c v b n m

### upper

- y=0: Q W E R T Y U I O P
- y=1: A S D F G H J K L
- y=2: Z X C V B N M

### numbers / symbols

数字、句読点、記号、通貨記号などを配置します。個々の候補の実装状態は対応する JSON の `variations` を参照してください。

## jp_qwerty

### lower / upper

標準的な QWERTY 配列をベースに、ローマ字かな入力に対応するキーを配置します。

### numbers / symbols

日本語入力で使用する全角記号、句読点、かな入力関連のキーを配置します。

## 設計資料との関係

このファイルは設計候補を列挙するものではありません。

- 「何を候補にするか」→ `docs/design/`
- 「実際に何を JSON に入れたか」→ `examples/`
- 「実装例にどのキーが存在するか」→ このファイル

という役割分担です。
