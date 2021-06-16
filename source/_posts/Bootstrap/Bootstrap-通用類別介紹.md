---
title: Bootstrap-通用類別介紹
date: 2021-06-02 17:21:54
categories: bootstrap
tags: bootstrap
---

## 位置（Position）

- 定位值：`<div class="position-sticky">...</div>`
- 排列元素：格式為 {property}-{position}
- property 為以下的其中一種:
  - top - 用於垂直定位 top
  - start - 用於水平定位 left (LTR)
  - bottom - 用於垂直定位 bottom
  - end - 用於水平定位 right (LTR)
- position 為以下的其中一種:
  - 0 - 用於 0 的邊界定位
  - 50 - 用於 50% 的邊界定位
  - 100 - 用於 100% 的邊界定位
<!--more-->
```html
<button type="button" class="btn btn-primary position-sticky top-0">
  Mails <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-secondary">+99 <span class="visually-hidden">unread messages</span></span>
</button>

<button type="button" class="btn btn-dark position-sticky top-0">
  Marker <svg width="1em" height="1em" viewBox="0 0 16 16" class="position-absolute top-100 start-50 translate-middle mt-1 bi bi-caret-down-fill" fill="#212529" xmlns="http://www.w3.org/2000/svg"><path d="M7.247 11.14L2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z"/></svg>
</button>

<button type="button" class="btn btn-primary position-sticky top-0">
  Alerts <span class="position-absolute top-0 start-100 translate-middle badge border border-light rounded-circle bg-danger p-2"><span class="visually-hidden">unread messages</span></span>
</button>
```

## 溢出 (Overflow)overflow-y : scroll
