---
title: Git 遠端數據庫
date: 2021-04-29 16:13:30
categories: GitHub
tags: 
  - GitHub
---

## 遠端儲存庫(Repository)操作

我們可以在已經上傳的數據庫，再增加一個遠端存儲庫

步驟為：
> 註冊 -> git remote add 第二個數據庫名稱 遠端儲存庫網址 -> 更新資料到遠端 master 分支：`git push -u 第二個數據庫名稱 master`
<!--more-->
- 註冊遠端儲存庫：`git remote add origin 遠端儲存庫網址`
- 更新資料到遠端 master 分支：`git push -u origin master`
- u 是指他預設會推到哪個遠端數據庫服務
- origin 可以改它的遠端數據庫名稱，例如 : `git push -u github master`

## Git 版本細節

- branch ：分支，預設分支叫做 master
- HEAD：指標
- origin：預設遠端儲存庫名稱
- 回頭觀看版本內容：git checkout 編號
- 返回最新的版本：git checkout master(分支名稱)
