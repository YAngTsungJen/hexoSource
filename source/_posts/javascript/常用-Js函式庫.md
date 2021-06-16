---
title: 常用 Js函式庫
date: 2021-04-19 19:51:14
categories: JavaScript
tags:
  - JavaScript
---

## 函式庫整理

### 千分位

``` javascript
function toThousands(x) {
  var parts = x.toString().split(".");
  parts[0] = parts[0].replace(/\B(?=(\d{3})+(?!\d))/g, ",");
  return parts.join(".");
}
```
<!--more-->

### 手機驗證

``` javascript
function phoneIsValid (phone) {
  if(/^[09]{2}\d{8}$/.test(phone)){
    return true;
  }else{
    return false
  }
}
```

### 信箱驗證(email)

``` javascript
function emailIsValid (email) {
  if(/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)){
    return true;
  }else{
    return false
  }
}
```

### 排列順序

``` javascript
function sort(item){
  item.sort((a,b) => b[1] - a[1]);
}
```

``` javascript
function sort(item){
  item.sort((a,b) => b - a);
}
```
