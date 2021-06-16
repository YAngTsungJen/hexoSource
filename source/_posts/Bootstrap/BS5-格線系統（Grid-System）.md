---
title: BS5 格線系統（Grid System）
date: 2021-05-24 18:15:02
categories: bootstrap
tags: bootstrap
---

## 什麼是格線系統？

- 為優化過多的 `class` 、CSS 而發明
- 可減輕 magic number 的出現。什麼是 magic number？當設計稿寫：左邊 340 px、右邊 660 px，而你直接在 CSS 寫 `width: 340px`、 `width: 660px` ，就是 magic number
- 以前螢幕寬度大多是 1024*768，所以當時格線系統寬度設計是 [960](https://960.gs/demo.html)
- 格線系統是透過 column（欄）、gutter（間距）的數字加總而成
- gutter 會以 `margin` 或 `padding` 推擠產生
（Bootstrap 是用 `padding` 、[960](https://960.gs/demo.html) 是用 `margin`，使用前可先了解是用哪個推擠的，比較不會出錯）
- 格線系統使用 `float` 寫成，而 `float` 有一特性：超過滿版時，元素會另起一行，也就是掉到第二行（如同 flexbox 的 `flex-wrap: wrap` ）
- 格線系統設計成 12 欄的原因：能被比較多數字整除、在瀏覽上也較順利。除了 12 欄以外，也有 16、24 欄，但較少見
<!--more-->
## Bootstrap 上的格線系統

排版三劍客： .container 、 .row、 .col 1~12

- `.container` 是一個容器，可以把內容物居中
- `.container` 固定寬度、 `.container-fluid` 滿版
- `.row`： `no-gutters` 不需要 gutters

## 重要觀念

1. 最外層至少一定要有一個 `.container` ，不然 `.row` 會自適應螢幕解析度（滿版）
2. `.container` 的第一層不一定要是 `.row` ，可以放其他東西

    ```html
    <div class="container green">
            <h4>標題</h4>
            <div class="row yellow">
                <div class="col-3 red">col-3</div>
                <div class="col-9 red">col-9</div>
            </div>
    </div>
    ```

3. `.row` 裡面只能是 `.col`
4. `.col` 的外層只能是 `.row`
5. 網頁內容與元件請放在 .col 裡

> 記得：container > (xxx可有可無） > row > col > 內容

```html
<div class="container green">
       <div class="row yellow">
           <div class="col-6 red">
                <h3 style="margin-left: 20px">標題</h3>   <!--h3 不屬於格線系統的設定，可以調整左右寬度 -->
                <p>內容</p>
           </div>
           <div class="col-6 red">col-6</div>
           <div class="col-6 red">col-6</div>
       </div>
</div>
```

## 不能做的事

1. 不要在 `.col` 增加寬度：格線系統已設定好寬度了，不要再增加寬度的 class 自找麻煩
2. 不要在格線系統調整左右的 `margin` 與 `padding` ：預設都已設定好一致性，任意調整可能造成破版

## 可以做的事

1. 可以加上下的 margin 與 padding
2. 整體格線邏輯是一致
單純使用 .col 沒有數字，會按比例排列

## 錯誤示範

> `<h1>`不能單獨在外

``` html
    <div class="container">
      <div class="row">
        <h1>標題</h1>
        <div class="col-3">選單</div>
        <div class="col-8">內容</div>
      </div>
    </div>
```

> row之後只能有col（雙層格線除外），不能再一用一個div包起來

``` html
    <div class="container">
      <div class="row">
        <div>
          <div class="col-6">標題</div>
          <div class="col-6">標題</div>
        </div>
      </div>
    </div>
```

## 正確寫法

> row會自動換行，只要超過格線就會換去下一行

``` html
    <div class="container">
      <div class="row">
        <div class="col-6">card1</div>
        <div class="col-6">card2</div>
        <div class="col-6">card3</div>
      </div>
    </div>
```

> container後面不一定要直接接row，但row之後一定要接col

  ![ ](002.png)

-----
> 如果像下方的排版，請不要開兩行（row)，後端會瘋掉XD!!!

  ![ ](003.png)

-----
> 如果沒設定col-(x)，直接寫col，也是可以的，它會自適應去調整col的寬度。

  ![ ](004.png)

-----
> 下方header、footer滿版，content依照container，也可以的喔！

  ![ ](005.png)

## BS5 格線系統斷點（Breakpoint）設計

  ![ ](006.png)
  ![ ](007.png)

```html
<!-- 此 code 在手機版是兩欄上下排、PC 版則是並排-->

<div class="container">
       <div class="row">
           <div class="col-md-4">col-4</div>
           <div class="col-md-8">col-8</div>
       </div>
</div>
```

```css

.row>* {
 ~~flex-shrink: 0;~~
 ~~width: 100%;~~
 max-width: 100%;
 padding-right: calc(var(--bs-gutter-x)/ 2);
 padding-left: calc(var(--bs-gutter-x)/ 2);
 margin-top: var(--bs-gutter-y);
}

@media (min-width: 768px){
   .col-md-4 {
       flex: 0 0 auto;
       width: 33.3333333333%;
}
   .col-md-8 {
       flex: 0 0 auto;
       width: 66.6666666667%;
}
}
```

> 1. Bootstrap 格線系統預設六個斷點：極小（xs）、小（sm）、中（md）、大（lg）、特大（xl）、超級大（xxl），也可自定義。
> 2. 若想先做 PC 版，可用 md、lg 當起手式。

  ![ ](008.png)

``` css
/* Bootstrap5 的 media queries*/

/* small devices (landscape phone, 576px and up) */
@media (min-width: 576px){ ... }

/* medium devices (tablets, 768px and up) */
@media (min-width: 768px){ ... }

/* large devices (desktops, 992px and up) */
@media (min-width: 992px){ ... }

/* extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px){ ... }

/* extra large devices (extra large desktops, 1400px and up) */
@media (min-width: 1400px){ ... }
```

## 格線系統和元件的整合

- 容器回歸於容器，元件回歸於元件，不要混寫在一起。元件是小物件，可以放在任何容器裡。

    ```css
    /* --------不好的寫法，很難應用---------- */
  .col-4 .btn-dark{
    width: 100px;
    height: 100px;
    background-color: black;
  }

    /* --------好的寫法：把容器（.col-4）和元件（.btn-dark）分開寫，可以使它們應用更廣--------- */
  .col-4{
    width: 100px;
    height: 100px;
  }
  .btn-dark{
    background-color: black;
  }
    ```

## 網站範例是否有使用格線

- [IT 邦幫忙](https://ithelp.ithome.com.tw/)：手機版時隱藏右側內容

> 右欄紅框處，在手機版時隱藏，平板以上打開，用 Bootstrap 所下的語法是 d-none d-md-block

  ![ ](009.png)

- [六角學院](https://www.hexschool.com)：判斷哪些地方有用到 .row 哪些地方沒有

  ![ ](010.png)

❌

選單通常不做 column，因為選單的文字是不規則的，且項目可能新增、項目數量無法被 12 整除（比如 7 個）。選單通常會用 Navbar（導覽列）去設計

⭕  

```html
<div class="col-lg-4 col-11 pt-md-0 pt-3 mb-lg-0 mb-5">...</div>
<div class="col-lg-4 col-11 pt-md-0 pt-3 mb-lg-0 mb-5">...</div>
<div class="col-lg-4 col-11 pt-md-0 pt-3 mb-lg-0 mb-5">...</div>
```

  ![ ](011.png)

- col不一定都從最左開始，只要在row多下一個j-c-c就可以讓裡面的col都置中了
⭕  

```html
<div class="row d-flex justify-content-center">
    <div class="col-11 col-md-10 d-flex flex-column">...</div>
</div>

<div class="row d-flex justify-content-center pt-4">
    <div class="col-md-4 col-11">...</div>
    <div class="col-md-4 col-11 mt-md-0 mt-3">...</div>
</div>
```

- Navbar 選單通常不會用到row>column，因為文字內容不一樣，而且可能會新增或減少選單，很難對齊column，因此通常用「navbar」。

  ![ ](015.png)

- [甜點電商](https://wcc723.github.io/F2E-PK/products.html)：表尾設計 + `row` 裡面再加 `.col`

  ![ ](012.png)

```html
▲ 注意：設計時，格線不要寫得剛剛好，要多留一些距離，避免斷行，而且各個瀏覽器可能會有些許誤差

<!--紅框和黃框-->
<div class="row justify-content-center">
    <div class="col-md-5 d-flex flex-column justify-content-between">...</div>
    <div class="col-md-5 text-right d-none d-md-block">...</div>
</div>

<!--藍框和桃紅框-->
<div class="row justify-content-center mt-4">
    <div class="col-md-5 mt-2">...</div>
    <div class="col-md-5 text-md-right mt-2">...</div>
</div>
```

  ![ ](013.png)

```html
<!--左欄文字-->
<div class="col-md-5 d-flex align-items-center justify-content-center justify-content-md-start mb-4 mb-md-0">...</div>

<!--右欄輸入框-->
<div class="col-md-5">...</div>
```

## 格線裡面還可以有格線

  ![ ](014.png)

- 有很多 class的話，建議從小寫到大（手機 → 平板 → 電腦）
- 斷點呈現的先後順序：(類別)-(size)-(屬性) → eg. d-md-row、align-items-lg-center
- 斷點建議從小寫到大（sm>md>lg>xl）
- 最外層有一個container → 包著一個row → 左邊col-3是選單 → 右邊col-9是內容 → col-9裡面也想要跟格線系統，所以再加兩個col-6(total:col-12)

  ```html
  <div class="container d-none d-md-block d-md-inline">
      <div class="row">
          <div class="col-12 col-md-10">...</div>
      </div>
  </div>
  ```

## 總結 必須記起來地方

- col外層只能是row；row裡面只能放col
- container裡不一定是row；row外層不一定是container
- 網頁內容及元件要放在col裡面
- col不一定要加起來有12，但一定不可以加起來超過12
- 不要在col增加寬度！！！
- 不要在格線系統調整左右 margin 與 padding！！！
- 可以加上下 的 margin 與 padding
