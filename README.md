シェルスクリプトマガジンVol.64 「はじめてのRust」
==========================================

著者によるリポジトリ
https://github.com/tatsuya6502/shellmag-2020-02

### Rustの特徴

- トレイト: Interfaceのようなもの。一番近いのはHaskellの型クラス
- ディスパッチ: 同種の複数の対象から一つを選ぶこと
  - 動的ディスパッチ: 動的にわかる型でディスパッチ
    - Javaなどの言語はこの方法だけをサポート
  - 静的ディスパッチ: 


### Part2 コマンドラインプログラムを作ろう

- クレート(crate): ライブラリ。crates.ioに登録されている
- Options型: 値がなければ `None`、あれば `Some(value)`
- Result型: 処理に成功したときは `Ok(T)` 、失敗したときは `Err(E)` を返す
- `?` 後置演算子: `Ok(T)`なら包んでいる値を取り出す。`Err(E)`なら関数をリターンし呼び出し元に`Err(E)`の値を返す
- `Box<dyn トレイト名>`: トレイトオブジェクト。具体的な型は実行時まで決まらないが、そのトレイトを実装している型を意味する
- 構造体
  - 名前付きフィールド構造体
  - タプル構造体
  - ユニット構造体

```rust
// 名前付きフィールド構造体
struct 構造体の名前 {
  フィールド0: 型,
  フィールド1: 型,
}

// タプル構造体
struct 構造体の名前 (フィールド1の型, フィールド1の型, ...);

// ユニット構造体
struct 構造体の名前;
```

- `|e| e.into()`: クロージャ。 `|e|` がクロージャの引数のリスト、`e.info()` がクロージャの本体


- 関連関数: `new()` など。 `構造体::関連関数()` で呼び出す。クラスメソッドに似ている
- `<Result型>.unwrap_or_else(クロージャ)`: Okなら値を取り出し、エラーなら引数として与えたクロージャを実行する


### わからなかったこと

- テストの書き方
- モジュールについて（ファイルをどう分割するのかという話）
