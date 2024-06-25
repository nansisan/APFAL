# **任意精度浮動小数点演算ライブラリver0.3 使い方**
このライブラリは任意精度の浮動小数点演算をサポートするJavaScriptのクラスです。基本的な演算（加算、減算、乗算、除算）から、高度な数学関数（累乗、階乗、組み合わせ、順列）まで、幅広くサポートしています。
## 目次
 - 仕様
 - 関数の名称、解説
 - 例
 - 参考
 - ライセンス
## 仕様
|項目|値|
|:----------:|:-------------:|
|演算可能桁数|323228496.6桁|
|関数種類|22種|
|動作要件|ES2020対応のブラウザ(それ以外は知らん)|
|入力型|Number, String, BigInt|
|出力型|String, Boolean|
### コンストラクタ
- `constructor()`
  - 新しい `Calculator` オブジェクトを作成します。

### メソッド

#### 基本演算

- `add(a, b)`
  - 加算を行います。
  - 引数：
    - `a`: 任意精度の数値（数値、文字列、またはBigInt）
    - `b`: 任意精度の数値（数値、文字列、またはBigInt）
  - 戻り値： `a` と `b` の和

- `subtract(a, b)`
  - 減算を行います。
  - 引数：
    - `a`: 任意精度の数値（数値、文字列、またはBigInt）
    - `b`: 任意精度の数値（数値、文字列、またはBigInt）
  - 戻り値： `a` から `b` の差

- `multiply(a, b)`
  - 乗算を行います。
  - 引数：
    - `a`: 任意精度の数値（数値、文字列、またはBigInt）
    - `b`: 任意精度の数値（数値、文字列、またはBigInt）
  - 戻り値： `a` と `b` の積

- `divide(a, b, decimalPlaces)`
  - 除算を行います。
  - 引数：
    - `a`: 任意精度の数値（数値、文字列、またはBigInt）
    - `b`: 任意精度の数値（数値、文字列、またはBigInt）
    - `decimalPlaces`: 結果の小数点以下の桁数（数値）
  - 戻り値： `a` を `b` の商

#### 高度な演算

- `intpow(a, b)`
  - 整数の累乗を計算します。
  - 引数：
    - `a`: 底（数値、文字列、またはBigInt）
    - `b`: 指数（数値、文字列、またはBigInt）
  - 戻り値： `a` の `b` 乗

- `intpow(a, b)`
  - aが少数の場合の累乗を計算します。
  - 引数：
    - `a`: 底（数値、文字列、またはBigInt）
    - `b`: 指数（数値、文字列、またはBigInt）
  - 戻り値： `a` の `b` 乗

- `factorial(a)`
  - 階乗を計算します。
  - 引数：
    - `a`: 階乗を計算する数値（数値、文字列、またはBigInt）
  - 戻り値： `a` の階乗

- `product(a, b)`
  - aからbまでの積を計算します。
  - 引数：
    - `a`: 最小値（数値、文字列、またはBigInt）
    - `b`: 最大値（数値、文字列、またはBigInt）
  - 戻り値： `a` の階乗

- `product(a, b)`
  - aからbまでの和を計算します。
  - 引数：
    - `a`: 最小値（数値、文字列、またはBigInt）
    - `b`: 最大値（数値、文字列、またはBigInt）
  - 戻り値： `a` の階乗

- `nCr(n, r)`
  - 組み合わせを計算します。
  - 引数：
    - `n`: 母集団のサイズ（数値、文字列、またはBigInt）
    - `r`: 選択する要素の数（数値、文字列、またはBigInt）
  - 戻り値： `n` 個から `r` 個を選ぶ組み合わせの数

- `nPr(n, r)`
  - 順列を計算します。
  - 引数：
    - `n`: 母集団のサイズ（数値、文字列、またはBigInt）
    - `r`: 選択する要素の数（数値、文字列、またはBigInt）
  - 戻り値： `n` 個から `r` 個を選ぶ順列の数

- `sqrt(a, decimalPlaces)`
  - 平方根を計算します。
  - 引数：
    - `a`: 平方根を計算する数値（数値、文字列、またはBigInt）
    - `decimalPlaces`: 結果の小数点以下の桁数（数値）
  - 戻り値： `a` の平方根

#### 補助関数

- `inputCheck(a)`
  - 入力を検証し、適切な形式に変換します。
  - 引数：
    - `a`: 検証する数値（数値、文字列、またはBigInt）
  - 戻り値： 検証された数値

- `normalize(a)`
  - 数値を正規化します。
  - 引数：
    - `a`: 正規化する数値（数値、文字列、またはBigInt）
  - 戻り値： 正規化された数値

- `mod(a, b)`
  - 剰余を計算します。
  - 引数：
    - `a`: 被除数（数値、文字列、またはBigInt）
    - `b`: 除数（数値、文字列、またはBigInt）
  - 戻り値： `a` を `b` で割った剰余

- `abs(a)`
  - 絶対値を計算します。
  - 引数：
    - `a`: 絶対値を計算する数値（数値、文字列、またはBigInt）
  - 戻り値： `a` の絶対値

#### 端数処理

- `floor(a, decimalPlaces)`
  - 数値を切り捨てます。
  - 引数：
    - `a`: 切り捨てる数値（数値、文字列、またはBigInt）
    - `decimalPlaces`: 小数点以下の桁数（数値）
  - 戻り値： `a` を切り捨てた結果

- `ceil(a, decimalPlaces)`
  - 数値を切り上げます。
  - 引数：
    - `a`: 切り上げる数値（数値、文字列、またはBigInt）
    - `decimalPlaces`: 小数点以下の桁数（数値）
  - 戻り値： `a` を切り上げた結果

- `round(a, decimalPlaces)`
  - 数値を四捨五入します。
  - 引数：
    - `a`: 四捨五入する数値（数値、文字列、またはBigInt）
    - `decimalPlaces`: 小数点以下の桁数（数値）
  - 戻り値： `a` を四捨五入した結果

#### 比較処理
- `greaterThan(a, b)`
  - 数値を比較します。
  - 引数：
    - `a`: 比較する数値
    - `b`: 比較する数値
  - 戻り値： `a` < `b` であるか。

- `lessThan(a, b)`
  - 数値を比較します。
  - 引数：
    - `a`: 比較する数値
    - `b`: 比較する数値
  - 戻り値： `a` < `b` であるか。

- `equals(a, b)`
  - 数値を比較します。
  - 引数：
    - `a`: 比較する数値
    - `b`: 比較する数値
  - 戻り値： `a` = `b` であるか。

これらのメソッドは、文字列または数値を引数として受け取ります。結果は文字列として返されます。このライブラリは、JavaScriptの数値型の精度制限を回避して、より正確な計算が可能になります。しかし、このコードは文字列の操作をかなり扱うため、計算速度が遅くなる可能性があります。したがって、高速な計算が必要な場合や精度がそれほど重要でない場合は、JavaScript の標準的な算術演算子を使用することをお勧めします。

>注:Product関数の引数及びpowのb引数は小数点に対応していません。また関数使用後に正規化関数を実行することを推奨します。

## 例
```js
calc.add(3,0.1415926535);
//->'3.1415926535'
calc.divide(22,7,20);
//->'3.14285714285714285714
//Normalize関数で正規化
calc.subtract(1.61,1.97)
//-> -.36
normalize(calc.subtract(1.61,1.97))
//->'-0.36'
```
### 円周率計算(ガウスルジャンドルの公式)
```js
function gaussLegendre(iterations) {
    let a = 1;
    let b = calc.divide(1, calc.sqrt(2, iterations), iterations+1);
    let t = calc.divide(1, 4, iterations);
    let p = 1;

    for (let i = 0; i < Math.log2(iterations); i++) {
        let a_next = calc.divide(calc.add(a, b), 2, iterations+2);
        let b_next = calc.sqrt(calc.multiply(a, b), iterations+2);
        let t_next = calc.subtract(t, calc.multiply(p, calc.pow(calc.subtract(a, a_next), 2)), iterations+1);

        a = a_next;
        b = b_next;
        t = t_next;
        p = calc.multiply(2, p);
    }

    let pi = calc.divide(calc.pow(calc.add(a, b), 2), calc.multiply(4, t), iterations);
    return calc.normalize(pi);
}

console.log(gaussLegendre(10));
```

## 参考
 - bing AI(乗算、除算の作成)
 - qiita(markdownの作成)
 - teratail(加算コードの修正)
 - MDN(仕様確認)

## ライセンス
[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed)
![](https://upload.wikimedia.org/wikipedia/commons/d/d3/Cc_by-nc_icon.svg)

