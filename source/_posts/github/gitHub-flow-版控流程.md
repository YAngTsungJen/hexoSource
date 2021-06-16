---
title: gitHub flow 版控流程
date: 2021-05-04 17:01:56
categories: GitHub
tags: 
  - GitHub
---
[gitHub flow]: https://guides.github.com/introduction/flow/
[git flow]: https://nvie.com/posts/a-successful-git-branching-model/

## 常見合作流程

1. [git flow]
2. [gitHub flow]
3. gitlab flow

## gitHub flow 流程

    1. 在 master 建立分支來新增功能
    2. 開始開發功能
    3. 發 PR (Pull Request) 申請合併
    4. 討論與檢視程式碼
    5. 部署(Deploy)
    6. 合併(Merge)

<!--more-->
## gitHub flow 規範

- 任何在 master 上的 commit 都是可以部署的
- 假使程式碼需要討論，請 PR 後在 comment 進行討論

## 協作流程

1. 本地建立 node 、Git 環境，增加 (.gitignore)
2. commit 1：建立環境 `git commit -m '建立環境'`
3. commit 2：修改 title `git commit -m '修改 title'`
4. 新增 dev branch。    `git branch dev`  在master時，先創立一個分支
5. 新增 GitHub Repo，並 push    連接github
6. 新增 heroku Repo，並 push.   連結heroku
7. B 抓 GitHub dev 分支，並開 feature 分支
 `git clone` `git branch feature` `git push origin feature`  
8. commit 兩個後，push feature 分支，並開 pr 請求合併 dev
9. 管理員 A 合併
10. C 抓 GitHub dev 分支，並開 feature 分支
11. commit 兩個後，push feature 分支，並開 pr 請求合併 dev
12. 管理員 A 合併，並抓下來看內容都 ok
13. 管理員 A fetch 下來，用 master 合併 origin/dev 分支，並 push 到 GitHub
用git fetch把遠端資料全部桌下來
