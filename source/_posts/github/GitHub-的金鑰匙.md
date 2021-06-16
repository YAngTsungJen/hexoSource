---
title: GitHub 的金鑰匙
date: 2021-04-28 19:54:46
categories: GitHub
tags: GitHub
---

## 到底如何設定GitHub 的 SSH 呢？
<!--more-->
步驟一：
首先，要先用終端機移動到本機（也就是你這台電腦）的 .ssh上
例如：我終端機前面那行字為`yang@yangcongrendeMacBook-Air`，所以輸入
`cd /Users/yang/.ssh`，移動到.ssh上。

步驟二：在`yang@yangcongrendeMacBook-Air .ssh`的位置上，再輸入
`cat id_rsa.pub`這串指令，會跑出一段密碼。將這段密碼貼到gitHub的設定上面（最前面ssh-rsa不用貼）。
所以簡單來說，只要輸入兩行指令(yang是我的電腦名字，要自己改掉哦)

``` bash
cd /Users/yang/.ssh
cat id_rsa.pub
```
