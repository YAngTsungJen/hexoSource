---
title: 搞懂 Git 分支五四三！
date: 2021-04-30 10:21:06
categories: GitHub
tags: 
  - GitHub
---

[Learn Git Branching]: https://learngitbranching.js.org/?locale=zh_TW

## Git 分支(branch)

搭配 [Learn Git Branching]。

在一開始接觸 git branch，總會疑問著，分支是什麼，可以運用在什麼地方？

- 多人協作時，不可能都在 master
- 可以讓 master 都是正式版資料，可以開分支來做測試或開發，藉此不影響正式主機分支
<!--more-->

## 試著想像～

- 分支就像是便利貼，貼在某個 commit 上
- 分支合併，主要是兩個 commit 進行合併

## 結論～開分支流程

1. 新增分支：

        ``` bash
        git branch 分支名稱
        ```

2. 查看分支：

        ``` bash
        git branch
        ```

3. 切換分支：

        ``` bash
        git checkout 分支名稱
        ```

4. 刪除分支：

        ``` bash
        git branch -d 分支名稱
        ```

    -D 是強制刪除

5. 還原上個版本：

        ``` bash
        git reset HEAD^
        ```

    開發情境：我有一個正式主機 master 分支，有一個開發分支叫做 develop

## 合併分支 && 快轉機制

1. 合併分支：

        ``` bash
        git merge 分支名稱
        ```

2. 取消快轉：

        ``` bash
        git merge 分支名稱 --no-ff
        ```

3. 觀看線圖：

        ``` bash
        git log —oneline -graph
        ```

4. 還原合併前狀態：

        ``` bash
        git reset —hard ORIG_HEAD
        ```

## 快轉機制

- 取消快轉：兩個不同任務分支合併時，取消快轉
- 預設使用快轉：本地與遠端兩條相同的任務分支時，可以用快轉

>判斷機制：

    1. 當 master 或 其他分支 其中一個還在源頭時，要使用取消快轉`git merge 分支名稱 --no-ff`

    2. 反之，當 master 或其他分支已經不在源頭時（都有commit過），就可以直接使用快轉`git merge 分支名稱`
