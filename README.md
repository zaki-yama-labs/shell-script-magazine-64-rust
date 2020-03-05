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
