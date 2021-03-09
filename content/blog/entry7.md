---
title: C++📦管理器與打📦器（C++ Package Management）
tags: C++
category: Backend
excerpt: 讓C++在本地運行與安裝OpenCV
created: 2019-07-29
image: ./images/riccardo-chiarini-2VDa8bnLM8c-unsplash.jpg
image_caption: Photo by Riccardo Chiarini on Unsplash
author: author1
---

一個編譯型語言（Java 和JavaScript ES9在我眼中算編譯型啦）都會有一個打包📦器去將C++基準庫和外來庫黏在一起。例如JavaScript有大名鼎鼎的 `Webpack` ， Java 有 `Gradle` 和 `Maven` ,那麼C++ 有什麼呢？最有名的就是 `Cmake`,但我今天想介紹一個更好用的 `Xmake` .而 `JavaScript` 當中有一個非常有名的包管理器 `npm`. 我們今天會用 `Conan`

## 安裝教學

[環境配置📦](/blog/c-local-config/)

## 介紹

Xmake

[xmake](https://xmake.io/#/guide/installation)

Conan

[conan-io/conan](https://github.com/conan-io/conan)

## 新Project

建立一個新Project

    xmake create -l c++ -P <project_name>

文件架構大概是這樣

    porject_1
    ├── src
    │   └── main.cpp
    └── xmake.lua

將你之前在網上打的Code複製進 `main.c`試試吧。然後運行

    xmake run

你的C++ Code還能運行出Android， iOS，Windows，Linux呢

    xmake f -p iphoneos; xmake
    xmake f -p android --ndk=<你的NDK地址>; xmake
    xmake f -p linux -a i386
    xmake f -p linux -a x86_64
    xmake f -p windows -a x64

### 安裝OpenCV

打開配置文件 `xmake.lua` 並添加OpenCV