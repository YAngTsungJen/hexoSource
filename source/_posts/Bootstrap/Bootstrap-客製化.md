---
title: Bootstrap-客製化
date: 2021-06-03 17:01:39
categories: bootstrap
tags: bootstrap
---

## Bootstrap-客製化

> npm下載方式：

1. 首先，在桌面建立資料夾，再來到[官網下載區](https://bootstrap5.hexschool.com/docs/5.0/getting-started/download/)找到下載方法，回到vsCode 輸入指令 `npm install bootstrap`，即可安裝完成 node_modules。

2. 建立 __SCSS資料夾__ ，再資料夾下建立一個主要檔案，用來統整全部的scss檔案，建立 all.scss 。
3. all.scss 裡載入客製化程式碼。
4. 把 node_modules 裡SCSS資料夾複製一份並改名為 bootstrap 到 __SCSS資料夾__ 裡。
5. 在all.scss 的前三個是必要載入的檔案：functions 、variables、mixins。
6. `@import "./bootstrap/scss/bootstrap"`，這個檔案是直接概括全部的 scss 內容，若是只需要特定元件或是只要隔線系統，就載入自己想要的也可以。

<!--more-->
        ``` plain
            your-project/
            ├── scss
            │   └── all.scss
            │   └── helpers/variables
            │   └── base/base
            │   └── mixins/mixins
            │   └── components/card...
            │   └── utilities/utilities
            │   └── layout/navbar...
            │   └── pages/index...
            │   └── bootstrap/
            └── node_modules/bootstrap/scss
                                        ├── js
                                        └── scss
        ```

        ```scss
            // bootstrap Required
            @import "./bootstrap/scss/functions";
            @import "./helpers/variables";
            @import "./bootstrap/scss/mixins";
            // any optional Bootstrap components as you like
            @import "./bootstrap/scss/bootstrap";

            // base 全站設定
            @import "base/base";

            // mixins 自訂 mixins
            @import "mixins/mixins";

            // components 自訂 元件
            @import "components/card";
            @import "components/button";
            @import "components/pagination";

            // utilities 自訂 通用類別
            @import "utilities/position";

            // layout 
            @import "layout/navbar";

            // pages
            @import "pages/index";
        ```
