---
title: IT邦幫忙鐵人賽自我評價
tags: C++
category: Portfolio
excerpt: 介紹與評價自己IT邦幫忙鐵人賽參賽經歷
created: 2020-03-28
image: ./images/ithelp-screen-shot.jpg
image_caption: Photo by Josh Spires on Unsplash
author: author1
---

## 比賽連結
https://ithelp.ithome.com.tw/users/20120557/ironman/2670

## 動機

因為初期入門前端和後端的時候受過不少IT邦幫忙往期鐵人賽的幫助，因此我也想在第11屆鐵人賽的時候寫一些教學協助其他人接觸新技術。而我選擇C++是因為我當時認為自己Year2的時候在學校學過，而且當時IT幫幫忙沒有一個完整的C++教學，我希望可以貢獻一下。

## 編寫的Topic和困難

### 初期

我一開始是打算僅僅將C++2017年的新功能和C++的語法簡單介紹一次。但到達第10天左右發現一些入門級別的Syntax，例如Container/ variable/ 加減乘除/Class/ smart Pointer/func prog的欄目快介紹完了，簡單來說我的技術儲備快消耗光了。為了完成鐵人賽，我決定現學現用一些C++的流行欄目讓我可以繼續寫下去。

### Cmake /Xmake + Conan/vcpkg

C++的打包器非常難學，特別是對於我這個以前只是學過webpack和makefile的人，但在介紹其他流行欄目之前，這是必經之路，我當時配OpenCV環境就使用了幾個小時，最後看見我的圖片編修小項目能運行的時候，成就感是非常大的，而我也立即做deadline fighter，把測試成果和坑，配置方法分享在鐵人賽當中。當然這對我之後學gradle幫助很大。

### JSON

我講解這個欄目是是作為一個Data Structure去講解，就是比喻成一個類似於Map的Container，但卻是Dynamic Map，並且把JSON寫出到文件，輸入到C++等等，模擬出Persistent Store的架構。這是講OpenCV之前的一個小甜品。

### Async/OpenMP

C++本身有一個Async，但這個Async的性能比Goroutine的性能差很遠，應該是封裝線程API的新功能，多數是用來處理網絡請求或者重度運算需求。

OpenMP則是利用平行運算技術加速重度運算的需求。使用了C++ pragma syntax

### OpenCV / FFmpeg

CV在C++應該算是大Topic，我使用了OpenCV進行圖片編修，了解了CV幾個函數和Matrix Type，當時本想做一些更高階的應用，例如影片播放器，但因為功力不足和時間不允許，所以並沒有進行這個操作。

FFmpeg也是簡單介紹一下而已，並沒有更高端的應用，因為FFmpeg比CV更難，這是最遺憾的事情。

## 展望未來

### C++20

C++2020版本即將發佈了，我已經在了解Module，concept，generator等等新功能，希望能在正式推出的時候加推幾個章節。

### OpenCV

希望可以有機會學得更深入，加上Deepfake換臉的教學或者物件辨識/追的教學

### FFmpeg

希望可以應用smart pointer在FFmpeg當中，並且用C++的新語法進行Syntax簡化等等。當然最希望是可以有和OpenCV的整合

