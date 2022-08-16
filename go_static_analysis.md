# GOソースコードの静的解析
資料: https://github.com/gohandson/analysis-ja
https://yuroyoro.github.io/goast-viewer/
https://go.dev/play/

ファイルの位置や長さに関する情報を保持する構造体(token.FileSet型)を用意する

オブジェクトには、整数や実数など、いろいろな種類があります。オブジェクトの種類のことを、型 と呼びます。


1. 識別子からオブジェクトの取得
    - *types.Info型のObjectOfメソッドを使う

2.  スコープからオブジェクトの取得
    - *types.Scope型のLookupメソッドを使う
    - LookupParentメソッドを用いれば親を辿っていって見つける
3. スコープ内の識別子を取得
    - *types.Scope型のNameメソッドを使う
    - []string型で取得できる
    - types.Object型の値が欲しい場合はLookupメソッドを使う
4. パッケージ外のオブジェクトを取得
    - *types.Package型のImportsメソッドから探す
    - インポートしているパッケージのスコープから探す
## メモ
for expr, tv := range info.Types {
info.Typesはmap(ディクショナリ)であり, expr:tvに入る
### pythonでは
- モジュール = ファイル。拡張子が .py （あるいは .pyc 等）の Python ファイルのこと。モジュール = import 文でインポートすることができるもの 。
- パッケージ = ディレクトリ。 \_\_init__.py というファイルを格納したディレクトリのこと。パッケージ = モジュールのうち他のモジュールをサブモジュールとして格納したもの。
     