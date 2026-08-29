# Let's find max value!

## 最大値を求めよう @showdialog

![Let's find prime numbers!](/static/tutorials/image01.png)



## 最大値を求める考え方 @showdialog

**仮の最大値を max ** を配列先頭の値にする。

i が 0番目から (配列の長さ - 1)番目まで i を増やしながら、
max と 配列のi番目の要素を比較して、大きい方を max とする。

![操作の考え方](/static/tutorials/image02.png)


## STEP1-1 変数の作成
``||variables:変数を追加する||`` から、個の変数 i, max を作成します。

## STEP1-2 仮の数値の代入 
``||input:ボタン A が押されたとき||``を配置して、``||variables:変数 〜 を〜にする||`` ブロックを使って、``||variables:変数 max||`` を ``||array:配列の0番目の値||``にして、``||variables:配列||`` を``||variables:data||``  にします。
そして、``||variables:変数 i||`` を0にします。


```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
})
```

## STEP1-3 くり返しの設定
``||loop:もし <偽> ならくりかえし||`` を出して、  <偽> の部分に ``||logic: 論理||``にある「くらべるブロック」から ``||logic: ()<()||`` ブロックをセットして ``||logic: (i)<(配列の長さ(data))||`` にします。

```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
    	
    }
})
```


## STEP1-4 もし〜ならブロックの利用
``||logic: 論理||``の``||logic: もし〜なら||``ブロックを``||loop:くりかえし||``の中に入れます。

```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
        if (true) {
        	
        }
    }
})
```

## STEP1-4 もし〜ならブロックの利用（つづき）
``||logic: もし〜なら||``ブロックの条件に ``||variables:max||`` < ``||array:配列の i 番目の値||``  という条件を加えて、「配列」を「data」に変えます。
また、このとき``||variables: max||``を``||array: data の i 番目の値||``にします。

```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
        if (max < data[i]) {
            max = data[i]
        }
    }
})
```

## STEP1-7 i をひとつ増やす
``||loop: くりかえし||``ブロックの一番下に ``||variables: 変数||``から``||variables: 変数iを1増やす||`` をセットします。

```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
        if (max < data[i]) {
            max = data[i]
        }
        i += 1
    }
})
```

## STEP1-8 結果の表示
``||loop: くりかえし||``ブロックの下に ``||basic: 基本||``から``||basic: 数を表示||`` を使って、``||variables:変数||``の``||variables:max||``を表示します。

```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
        if (max < data[i]) {
            max = data[i]
        }
        i += 1
    }
    basic.showNumber(max)
})
```


## STEP1-9 実行
ここまできたら、ダウンロードして micro:bit で動かしてみよう。できたら、 data の中の数値をいろいろな値に変えて、試してみよう。


```blocks
input.onButtonPressed(Button.A, function () {
    max = data[0]
    i = 0
    while (i < data.length) {
        if (max < data[i]) {
            max = data[i]
        }
        i += 1
    }
    basic.showNumber(max)
})
let i = 0
let max = 0
let data: number[] = []
data = [
23,
58,
41,
76,
35
]
```

## 完成！@showdialog
![Let's Make a Function!](/static/tutorials/image03.png)