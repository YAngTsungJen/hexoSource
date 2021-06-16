---
title: JavaScript 的開發流程紀錄
date: 2021-04-28 20:35:06
categories: JavaScript
tags: JavaScript
---
[設計稿]: https://xd.adobe.com/view/a48b8617-4588-4817-9062-b62130dce916-f1d8/

## 待辦事項

[設計稿]
<!--more-->
1. 環境建立
    - 建立基本環境
    - 拉完成的設計稿到自己的桌面
    - 稍微觀看的 CSS 結構
    - 調整 js 結構
    - API config 設定確認
        - 將私密帳號密碼放在 config
2. 前台開發
    - 產品 get API 設計
    - 下拉選單（cheange 事件），在顯示畫面
        - 重構下拉選單與 get API 設計
    - 購物車 API 設計
    - 產生訂單 API 設計

3. 後台開發
    - 下面的訂單列表
    - 上面的 C3 圖表
4. 優化細節
    - 千分位設計
    - 使用者體驗
    - validation 優化
    - C3.js 優化

## 注意事項

> 先開發到客戶滿意程度，在私下重構、優化（錯誤回饋、UI 優化）⇒ 效能優化
> 零產出，比較容易做的功能先做一做
> 小步測試 ⇒ 寫開發 code ⇒ 小步測試 ⇒ 寫開發 code ⇒ 小小重構
> tdd 測試，先寫測試 code，在寫產品 code
> 把成果文字化，寫成自己筆記
