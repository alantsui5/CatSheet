---
title: Shoppy項目自我評價
tags: Angular, Firebase
category: Portfolio
excerpt: 介紹與評價自己的Shoppy項目
created: 2020-03-28
image: ./images/shoppy-screen-shot.jpg
image_caption: Photo by Josh Spires on Unsplash
author: author1
---

## 項目連結
https://github.com/alantsui5/Shoppy

## 動機

因為這是學校的項目，所以我想在交付功課的同時為自己建立一個基本的平台（Platform）框架，展望最終能實現登入登出系統，買賣管理，展示頁面，物流系統，郵件驗證系統等等，現在還在完善當中。

## 技術選型與心路歷程

### Svelte

剛開始（在2月）的時候我打算使用Svelte為我的核心框架(因為這是我的第一個學框架。而且這是最簡單的框架)，使用Firebase作為Database，並漸進使用Express 作為附加功能（例如agolia search）。但在一直完善的過程，我發現Svelte並沒有一個功能完整的組件庫，並且Svelte並沒有一個前端架構管理的規範，我只能現學現用Tailwind去編寫UI，在初中期的時候就發生了架構不穩的問題。我當時打算使用Sapper（一個Svelte框架）去規範我的項目，runtime和編譯速度很快，但卻發現缺少Firebase支援，最後無奈放棄。
#### Links
這是我第一期的項目Repo：https://github.com/alantsui5/Pizzara

### React + Hook Class

為了獲得完整的Firebase支援和組件支援，我決定第二期使用React + Hook Class（Hook Class是一個自創詞語，用意為利用Hook模擬Svelte Store 功能，讓所有組件可以訪問這個class，其實就是Custom Hooks），不使用Redux是因為Redux比較難和麻煩，不如自建一個Hook Class去管理。我這個Hook 使用unstated去縮減寫Consumer的一步，並且將每個Hook Class（包含變量和Function）組合成一個Global Source Expose到Provider當中。

初期這個項目是非常順利的，利用React Material漂亮的組件和Hook Class組合拳成功實現了貨品展示模塊和用戶驗證模塊，連結Database等等，但同樣面對了Svelte一樣的問題，就是Scale和Refactor的問題，雖然我是用TSX去寫，但React組件，邏輯和JSS在同一個組件的寫法令我感到非常頭疼，可能TSX當中的html改一點就整個組件爛掉。而且我的Hook Class 和 rxjs在Call Firebase的時候有一點性能不足問題導致大量render。我猜我的Hook設計有改善空間。

然後我測試了一個React 框架UMIJS，測試遷移到這個阿里框架的可行性，UMI擁有更完整的Hook Class支援（他們自己寫的），架構清晰。而且有Prettier進行Code Formatting和Less做style JSX split，但問題是在我剛用的時候UMI3正在Beta阪本，有對Antd 進行編譯（雖然我不用），缺少Firebase支援。即使到現在 umi 的block（generator/template）功能都未能正常使用，因此我就放棄了。
#### Links
Hook Class（Custom Hook實驗 Link）：https://codesandbox.io/s/global-pure-hooks-dbt4w

這是我第二期的Repo： https://codesandbox.io/s/react-prototype-wvd5v

### Angular

因為看了這個影片，最後選擇了Angular

`youtube:https://www.youtube.com/watch?v=QNW0nYaidDY`

Angular和React 或者 Svelte不同，他有Google完整的規範，而且因為Angular的特性，所有組件都只會在App.module那個File註冊，加上Angular有比較完整的Global State支援和generator支援，令到Refactor變得比較簡單。而Firebase支援也是比較全面。沒有以上兩個框架所遭遇的困難，所以最後就選Angular了，也不打算再換。

## 使用Angular所面臨的困難

### TypeScript

以往寫React TSX或者Svelte TS就只是使用了TypeScript的Template（generic）和Typing 功能，並沒有太多其他功能。而Angular有應用Decorator Pattern, interface 功能，而且還有TypeScript Param Constructor。這導致我需要重新再學一次TypeScript。

另外，Angular本身有Directive/Pipe的概念(與TS無關）去處理數據與interaction，這些都是其他framework沒有的東西

### Component Framework

Angular Material不知道為什麼，功能比React Material差很多，難以比擬。另外，Angular當中的Ionic或者Ant Design一者是純Mobile端，一者是純PC端，導致並不符合我這個App的需求。我最後使用Tailwind編寫整個UI，並且利用Antd配合，由於Angular的視圖邏輯分離，Code並不算亂，只是要重做輪子。

### Testing

由於Angular會為每個新創建的Component或者service配置一個unit test，這會令到test coverage達到100%，但在寫Angular test的時候分外吃力，尤其是我以前並沒有學過前端testing。但的確學了很多testing技巧，每逢一個test過了都會更有成功感。

### 重量，速度

把全部需要的Dependency裝完和配置完之後大概有500mb左右，這是前端framework最大的大小。而編譯速度也是最慢的，但我認為這並非一個最大問題。

## 展望未來

### Testing

把剩餘的testing 寫齊整，完善以後加上Github Action Pipeline

### Backend

我將會使用Cloud Function 去implement部分功能，包括使用agolia做全文搜索，使用Firebase Admin做Pagination等等。

### Frontend

我將會加上完整的CRM並加上User Profile，User Setting，Logistic，Checkout page，並且完善購物車

