---
title: Boostrap 5 環境建立
date: 2021-05-24 09:16:48
categories: bootstrap
tags: bootstrap
---

## What is Bootstrap?

Bootstrap 是一個由 HTML、CSS 和 JavaScript 寫成的前端框架，核心的設計目標是達成RWD響應式與行動優先，也就是讓你的網站排版可以自動適應螢幕大小。它預先做好一套網站的基礎建設，讓你能在框架的基礎上進行開發，不需要再去煩惱瑣碎的設定。
<!--more-->
## 使用方法

1. 透過 cdn

    - CSS → 於`<head>`裡引入

      ``` html
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
      ```

    - JavaScript -> 於`</body>`的結尾處引入

        ``` html
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" crossorigin="anonymous"></script>
        ```

2. [本地下載（直接下載到本機）](https://getbootstrap.com/docs/5.0/getting-started/download/)

    - 看到「Compiled CSS and JS」，按下下載。解壓縮檔案後，嵌入以下檔案即可使用：
      - `css/bootstrap.min.css`
      - `js/bootstrap.bundle.min.js`

## 使用方式的優/缺點

1. 使用cdn的優/缺點
    - 載入速度快
    - 省流量
    - 掛掉就會跟著一起掛掉
    - 版本要更新

2. 使用本地的優/缺點
    - 可客製化
    - 太大包跑比較久
    補：也可以下載個別功能不用整包下載

## 如何確認 BootStrap 有安裝成功？

可以裝設一些 BootStrap 撰寫好的套件來玩玩，像是 按鈕、互動視窗或是卡片。

## CSS Reset

清除瀏覽器預設樣式，boostrap本身內就涵有使用[css reset](https://bootstrap5.hexschool.com/docs/5.0/content/reboot/)，因此不用另外去載入。

參考資料：[bootstrap新手實戰營](https://www.youtube.com/watch?v=WGu0F7nmQFQ)
