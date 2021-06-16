---
title: Bootstrap-元件介紹
date: 2021-06-02 13:55:54
categories: bootstrap
tags: bootstrap
---

## 互動式窗（Modal）

- 用在設計稿右上的登入註冊
- 按鈕的`data-bs-target`和 Modal 的 id 相同，就可以為一組互動式窗。
- 若在 Modal最外層加入 `data-bs-backdrop="static" data-bs-keyboard="false"`，可以將背景設置為靜態，互動視窗不會因為點擊背景而關閉。
<!--more-->
- 滾動長內容：透過在 `.modal-dialog` 中加入 `.modal-dialog-scrollable` 來創建一個 body 可滾動互動視窗
- 垂直置中：加入 .modal-dialog-centered 到 .modal-dialog 來使互動視窗垂直置中。
- 有 `aria`的標籤：是給無障礙人士是使用，通常做無障礙網站是必備的。
- [30篇好文連結](https://ithelp.ithome.com.tw/users/20108045/ironman/2454)

``` html
<!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" data-bs-backdrop="static" data-bs-keyboard="false" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
---
```

## 折疊（Collapse）

- 使用a連結：`data-bs-toggle="collapse" href="#collapseExample"`和內容的 `id="collapseExample"`為一組，可以產生折疊效果。
- 使用button：`data-bs-toggle="collapse" data-bs-target="#collapseExample"`和內容的 `id="collapseExample"`為一組，可以產生折疊效果。
- `role="button" aria-expanded="false" aria-controls="collapseExample"`為無礙障人士使用。

```html
<p>
  <a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
    問題一
  </a>
  <div class="collapse" id="collapseExample">
    <div class="card card-body">
      問題一答案
    </div>
  </div>
  <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample2" aria-expanded="false" aria-controls="collapseExample">
    問題二
  </button>
  <div class="collapse" id="collapseExample2">
    <div class="card card-body">
      問題二答案
    </div>
  </div>
</p>
```

## 導覽與頁籤（Navs and tabs）

- 使用button：`data-bs-toggle="tab" data-bs-target="#home"` 和 `id="home"`為一組
- 使用a連結：`data-bs-toggle="tab" href="#home"`和`id="home"`為一組
- active ：若要改變請上下都改。

```html
<!-- Nav tabs -->
<ul class="nav" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <a class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home" type="button" role="tab" aria-controls="home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile" type="button" role="tab" aria-controls="profile" aria-selected="false">Profile</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="messages-tab" data-bs-toggle="tab" data-bs-target="#messages" type="button" role="tab" aria-controls="messages" aria-selected="false">Messages</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="settings-tab" data-bs-toggle="tab" data-bs-target="#settings" type="button" role="tab" aria-controls="settings" aria-selected="false">Settings</button>
  </li>
</ul>

<!-- Tab panes -->
<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab">home</div>
  <div class="tab-pane" id="profile" role="tabpanel" aria-labelledby="profile-tab">profile</div>
  <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab">messages</div>
  <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab">settings</div>
</div>
```

## 卡片（Cards）

- 去除gutters：使用 .g-0 移除網格的 gutters
- 斷點設計：使用 .col-md-* 類別讓卡片在 md 斷點之後呈現水平
- 圖片部分可以使用背景圖 `background: url()`或是 img標籤來呈現

```html
  <div class="card mb-3" style="max-width: 540px;">
    <div class="row g-0">
      <div class="col-md-4">
        <img class="img-fluid" src="https://fakeimg.pl/180x250/">
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
        </div>
      </div>
    </div>
  </div>
  <div class="card mb-3" style="max-width: 540px;">
    <div class="row g-0">
      <div class="col-md-4" style="background: url(https://miro.medium.com/max/676/1*XEgA1TTwXa5AvAdw40GFow.png) center / contain;">
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
          <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
        </div>
      </div>
    </div>
  </div>
```
