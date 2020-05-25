# リファクタリングカタログ

Martin Fowler 氏の書籍『 Refactoring: Improving the Design of Existing Code 』（ the second edition ）で紹介されているリファクタリングテクニックとバッドスメルの一覧です。

詳細は原典にあたることをおすすめします。

## リファクタリングとは

リファクタリング（ refactoring ）とは、プログラムの外部から見える挙動を変えずに内部の構造を改善することです。
その目的は、コードをわかりやすくすることと変更のコストを下げることです。
外から見える挙動を変える変更や内部構造を変更しない簡易なクリーンアップはリファクタリングとは呼びません。

公式サイト Refactoring には次のように説明されています。

> Refactoring is a disciplined technique for restructuring an existing body of code, altering its internal structure without changing its external behavior.
>
> Its heart is a series of small behavior preserving transformations. Each transformation (called a "refactoring") does little, but a sequence of these transformations can produce a significant restructuring. Since each refactoring is small, it's less likely to go wrong. The system is kept fully working after each refactoring, reducing the chances that a system can get seriously broken during the restructuring.

意訳:

> リファクタリングとは外部に対する挙動を変えずに既存のコードの内部構造を変更するための規律あるテクニックです。
>
> その神髄は、元の挙動を保ったまま行う小さな変形の積み重ねです。
> それぞれの変形（これを「リファクタリング」と呼びます）は小さなものですが、その変形を連続して行うことで大幅な構造の変更が達成できます。
> 各リファクタリングは小さいので、間違う可能性は低いです。
> 各リファクタリングを行った後のシステムを元のとおり完全に動作させつつ、変更の途中で深刻な破壊が起こってしまう可能性を減らすことができます。

出典: [Refactoring](https://refactoring.com/)

## リファクタリングのメリット

リファクタリングを行うことにはいくつかのメリットがあります。

- 設計が改善される
- コードのわかりやすさが向上する
- バグの発見が進む
- その後のプログラミングが速くなる

## リファクタリングのタイミング

リファクタリング行うべきタイミングには次のようなものがあります。

- 同じ処理を 3 箇所以上で書いている
- コードがわかりづらい
- 機能追加を行う前
- 機能追加を行った後

## リファクタリングテクニック

次のようなリファクタリングテクニックがあります。

- Change Function Declaration: 関数宣言の変更
- Change Reference to Value: 参照の値への変更
- Change Value to Reference: 値の参照への変更
- Collapse Hierarchy: ヒエラルキーの圧縮
- Combine Functions into Class: 複数の関数のクラス化
- Combine Functions into Transform: 複数の関数の変換関数化
- Consolidate Conditional Expression: 条件式の集約
- Decompose Conditional: 条件の分割
- Encapsulate Collection: コレクションのカプセル化
- Encapsulate Record: レコードのカプセル化
- Encapsulate Variable: 変数のカプセル化
- Extract Class: クラスの抽出
- Extract Function: 関数の抽出
- Extract Superclass: スーパークラスの抽出
- Extract Variable: 変数の抽出
- Hide Delegate: デリゲートの隠蔽
- Inline Class: クラスのインライン化
- Inline Function: 関数のインライン化
- Inline Variable: 変数のインライン化
- Introduce Assertion: アサーションの導入
- Introduce Parameter Object: パラメータオブジェクトの導入
- Introduce Special Case: スペシャルケースの導入
- Move Field: フィールドの移動
- Move Function: 関数の移動
- Move Statements into Function: 文の関数への移動
- Move Statements to Callers: 文の呼び出し側への移動
- Parameterize Function: 関数のパラメータ化
- Preserve Whole Object: オブジェクト全体の保持
- Pull Up Constructor Body: コンストラクタのボディの引き上げ
- Pull Up Field: フィールドの引き上げ
- Pull Up Method: メソッドの引き上げ
- Push Down Field: フィールドの引き下げ
- Push Down Method: メソッドの引き下げ
- Remove Dead Code: デッドコードの削除
- Remove Flag Argument: フラグ引数の削除
- Remove Middle Man: ミドルマンの削除
- Remove Setting Method: セッターメソッドの削除
- Remove Subclass: サブクラスの削除
- Rename Field: フィールド名の変更
- Rename Variable: 変数名の変更
- Replace Command with Function: コマンドの関数への置き換え
- Replace Conditional with Polymorphism: 条件のポリフォーミズムへの置き換え
- Replace Constructor with Factory Function: コンストラクタのファクトリ関数への置き換え
- Replace Derived Variable with Query: 導出された変数のクエリへの置き換え
- Replace Function with Command: 関数のコマンドへの置き換え
- Replace Inline Code with Function Call: インラインコードの関数呼び出しへの置き換え
- Replace Loop with Pipeline: ループのパイプラインへの置き換え
- Replace Nested Conditional with Guard Clauses: ネストされた条件のガード節への置き換え
- Replace Parameter with Query: 引数のクエリへの置き換え
- Replace Primitive with Object: プリミティブのオブジェクトへの置き換え
- Replace Query with Parameter: クエリの引数への置き換え
- Replace Subclass with Delegate: サブクラスのデリゲートへの置き換え
- Replace Superclass with Delegate: スーパークラスのデリゲートへの置き換え
- Replace Temp with Query: 一時変数のクエリへの置き換え
- Replace Type Code with Subclasses: タイプコードのサブクラスへの置き換え
- Separate Query from Modifier: クエリのモディファイアからの分割
- Slide Statements: 文の前後への移動
- Split Loop: ループの分割
- Split Phase: フェーズの分割
- Split Variable: 変数の分割
- Substitute Algorithm: アルゴリズムの置き換え

## バッドスメル

リファクタリングを行うべき箇所の兆候として次のようなコードのバッドスメル（悪臭）があります。
各項目の後に書かれているのは、そのバッドスメルに対処するためのリファクタリングテクニックです。

- Alternative Classes with Different Interfaces: インタフェースが異なる代替クラスたち
    - Change Function Declaration
    - Move Function
    - Extract Superclass
- Comments: コメント
    - Extract Function
    - Change Function Declaration
    - Introduce Assertion
- Data Class: データクラス
    - Encapsulate Record
    - Remove Setting Method
    - Move Function
    - Extract Function
    - Split Phase
- Data Clumps: データのかたまり
    - Extract Class
    - Introduce Parameter Object
    - Preserve Whole Object
- Divergent Change: まばらな変更
    - Split Phase
    - Move Function
    - Extract Function
    - Extract Class
- Duplicated Code: 重複コード
    - Extract Function
    - Slide Statements
    - Pull Up Method
- Feature Envy: フィーチャーエンヴィ
    - Move Function
    - Extract Function
- Global Data: グローバルデータ
    - Encapsulate Variable
- Insider Trading: インサイダー取引
    - Move Function
    - Move Field
    - Hide Delegate
    - Replace Subclass with Delegate
    - Replace Superclass with Delegate
- Large Class: 大きなクラス
    - Extract Class
    - Extract Superclass
    - Replace Type Code with Subclasses
- Lazy Element: レイジーエレメント
    - Inline Function
    - Inline Class
    - Collapse Hierarchy
- Long Function: 長い関数
    - Extract Function
    - Replace Temp with Query
    - Introduce Parameter Object
    - Preserve Whole Object
    - Replace Function with Command
    - Decompose Conditional
    - Replace Conditional with Polymorphism
    - Split Loop
- Long Parameter List: 長い引数リスト
    - Replace Parameter with Query
    - Preserve Whole Object
    - Introduce Parameter Object
    - Remove Flag Argument
    - Combine Functions into Class
- Loops: ループ
    - Replace Loop with Pipeline
- Message Chains: メッセージチェイン
    - Hide Delegate
    - Extract Function
    - Move Function
- Middle Man: ミドルマン
    - Remove Middle Man
    - Inline Function
    - Replace Superclass with Delagate
    - Replace Subclass with Delegate
- Mutable Data: ミュータブルデータ
    - Encapsulate Variable
    - Split Variable
    - Slide Statements
    - Extract Function
    - Separate Query from Modifier
    - Remove Setting Method
    - Replace Derived Variable with Query
    - Combine Functions into Class
    - Combine Functions into Transform
    - Change Reference to Value
- Mysterious Name: 奇妙な名前
    - Change Function Declaration
    - Rename Variable
    - Rename Field
- Primitive Obsession: プリミティブオブセッション
    - Replace Primitive with Object
    - Replace Type Code with Subclasses
    - Replace Conditional with Polymorphism
    - Extract Class
    - Introduce Parameter Object
- Refused Bequest: 拒絶された遺産
    - Push Down Method
    - Push Down Field
    - Replace Subclass with Delegate
    - Replace Superclass with Delegate
- Repeated Switches: 繰り返しスイッチ
    - Replace Conditional with Polymorphism
- Shotgun Surgery: ショットガンサージェリ
    - Move Function
    - Move Field
    - Combine Functions into Class
    - Combine Functions into Transform
    - Split Phase
    - Inline Function
    - Inline Class
- Speculative Generality: 投機的な汎用性
    - Collapse Hierarchy
    - Inline Function
    - Inline Class
    - Change Function Declaration
    - Remove Dead Code
- Temporary Field: 一時フィールド
    - Extract Class
    - Move Function
    - Introduce Special Case

## 参考

- [Refactoring](https://refactoring.com/)
- [The Second Edition of "Refactoring"](https://martinfowler.com/articles/refactoring-2nd-ed.html)
