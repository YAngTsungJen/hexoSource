---
title: commit 衝突
date: 2021-05-04 16:41:54
categories: GitHub
tags: 
  - GitHub
---

## 本地 commit 衝突

1. 原因：
    >兩個 commit 在合併時，檔案裡的某一行有重複修改到時，就會觸發
2. 解決：
    * 因為分支修改到同一行的code，所以當 merge 時，會出現 commit 衝突。
    * 解決完在工作目錄的 commit 衝突，需要再`git add .` `git commit -m 'merge'`，才算完成。
<!--more-->

## 遠端 commit 衝突

* 故事理解：

    >1. A 跟 B 一起在同個 repo 開發，只有一條 master 線
    >2. A 先部署了一個 commit 到 master
    >3. B 更新了第六行程式碼，並在下班前立馬 push
    >4. A 也改了第六行，但他效率比較差，下班後 push 時才發現，B 這個ㄐ歪人先 push 了！
    >5. A 只好先 pull 下來，結果竟然跟自己的 commit 衝突
    >6. A 只好邊罵髒話，邊解決衝突，整理好後再 push

* 解決：
    因為 B 的檔案已在遠端上了，我們本地端的不是最新版的，因此我們要先輸入 `git pull` 把我們本地端檔案和遠端檔案合併，若有發生 遠端衝突時，要解決完成再`git add .` `git commit -m 'merge'`，才算完成
