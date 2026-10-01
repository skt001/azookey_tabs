# azooKey 物理キー一覧

`donotedit/azookey/*.json` から機械抽出した、各ページに実在するキーの一覧。行(y)ごとに左(x)から並べてある。`[+var]`はvariations(ロングプレス候補)が1件以上既に実装済みであることを示す。付与されていないキーは、物理的に存在はするが候補が空であることを意味する。

候補を特定のキーに割り当てる前に、まずこの一覧で対象キーが対象ページに実在するかを確認する(存在しないキーには割り当てられない)。一覧に無いキーが必要な場合は、まず実機・JSON側の追加要否から検討する。

## en lower.json

- y=0: q  w[+var]  e[+var]  r[+var]  t[+var]  y[+var]  u[+var]  i[+var]  o[+var]  p[+var]
- y=1: (system)  a[+var]  s[+var]  d[+var]  f[+var]  g[+var]  h[+var]  j[+var]  k[+var]  l[+var]  (system)
- y=2: ⇧  z[+var]  x  c[+var]  v[+var]  b[+var]  n[+var]  m[+var]  delete.left
- y=3: textformat.123  (system)  (system)

## en upper.json

- y=0: Q  W[+var]  E[+var]  R[+var]  T[+var]  Y[+var]  U[+var]  I[+var]  O[+var]  P[+var]
- y=1: (system)  A[+var]  S[+var]  D[+var]  F[+var]  G[+var]  H[+var]  J[+var]  K[+var]  L[+var]  (system)
- y=2: ⇧  Z[+var]  X  C[+var]  V[+var]  B[+var]  N[+var]  M[+var]  delete.left
- y=3: textformat.123  (system)  (system)

## en numbers.json

- y=0: 1  2  3  4  5  6  7  8  9  0
- y=1: -[+var]  /[+var]  :[+var]  ;  (  )  ¥[+var]  &[+var]  @  "[+var]
- y=2: #+=  .[+var]  ,  ?[+var]  ![+var]  '[+var]  delete.left
- y=3: ABC  (system)  (system)

## en symbols.json

- y=0: [  ]  {  }  #  %[+var]  ^  *  +  =[+var]
- y=1: _  \  |  ~  <[+var]  >[+var]  $[+var]  €  £  •
- y=2: textformat.123  .[+var]  ,  ?[+var]  ![+var]  '[+var]  delete.left
- y=3: ABC  (system)  (system)

## ja lower.json

- y=0: q  w  e  r  t  y  u  i  o  p
- y=1: a  s  d  f  g  h  j  k  l  ー[+var]
- y=2: ⇧  z  x  c  v  b  n  m  delete.left
- y=3: textformat.123  (system)  (system)

## ja upper.json

- y=0: Q  W  E  R  T  Y  U  I  O  P
- y=1: A  S  D  F  G  H  J  K  L  ー[+var]
- y=2: ⇧  Z  X  C  V  B  N  M  delete.left
- y=3: textformat.123  (system)  (system)

## ja numbers.json

- y=0: １  ２  ３  ４  ５  ６  ７  ８  ９  ０
- y=1: －  ／  ：  ＠  （  ）  「  」  ￥  ＆
- y=2: ＃＋＝  。  、  ？  ！  ^^  delete.left
- y=3: あいう  (system)  (system)

## ja symbols.json

- y=0: ［  ］  ｛  ｝  ＃  ％  ＾  ＊  ＋  ＝
- y=1: ＿  ＼  ；  ｜  ＜  ＞  ＂  ＇  ＄  €
- y=2: textformat.123  。  、  ？  ！  ・  delete.left
- y=3: あいう  (system)  (system)

## 既知の留意点

- en側はA–Z(Q, Xを除く)・ハイフン・通貨・句読法記号等に`[+var]`が実装済みで、設計資料とほぼ一致する。
- ja側は`ー`キーの1件を除き、英字・数字・記号キーは全て`[+var]`無し(候補未実装)。jp-qwerty-longpress-all.mdの英字・特殊かな・数字節の候補は、実機側にまだ反映されていない。
- `~`(チルダ)はen symbols.jsonには存在するが、ja numbers.json/ja symbols.jsonのどちらにも独立キーとして存在しない(jp_qwerty READMEの記載通り)。
