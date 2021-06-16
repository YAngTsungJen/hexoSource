---
title: git 還原技巧
date: 2021-04-29 16:40:26
categories: GitHub
tags: 
  - GitHub
---

## 還原技巧

[參數介紹]: https://gitbook.tw/chapters/using-git/reset-commit.html

新增檔案時

1. 檔案還沒加追蹤時（untracked），清空工作目錄
    * 顯示此次清除的檔案（預期要刪掉的檔案）：`git clean -n`
    * 強制清除檔案：`git clean -f`
2. 檔案已加入追蹤，清空工作目錄
    * 還原工作目錄上已更改的檔案（已在commit過的檔案）：`git checkout -- files(你要還原的檔案)`
    <!--more-->
3. 檔案加入到索引，退到工作目錄
    * 加入索引的檔案還原到工作目錄：`git reset HEAD`

    ![檔案](reset.png)

4. 版本還原(reset)
    * 索引檔案>還原到工作目錄：`git reset HEAD`
    * 還原前兩個版本：`git reset HEAD^^`
    * 還原前兩個版本，所有更新檔案都放棄：`git reset HEAD^^ --hard`
    * 還原到特定 commit：`git reset commit編號 --hard`
    * git reset [參數介紹]
    * 觀看詳細歷史紀錄：`git reflog`
    >可以使用`git reflog`查看已經被刪除的檔案 commit編號，再用`git reset commit編號 --hard`找回來

5. 查看版本(checkout)
    * 回頭觀看版本內容：`git checkout 編號`
    * 返回最新的版本：`git checkout master(分支名稱)`
    * 還原工作目錄上已更改的檔案 ：`git checkout -- <file>`

## checkout 與 reset 差異

    - checkout 是移動 HEAD
    - reset 是移動 branch 及HEAD
