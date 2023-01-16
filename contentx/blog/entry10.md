---
title: 本地環境配置（C++ Local Config）
tags: C++
category: Backend
excerpt: C++環境配置
created: 2019-10-31
image: ./images/sergio-souza-WU6K3Lmq9ok-unsplash.jpg
image_caption: Photo by Sergio Souza on Unsplash
author: author1
---

## Windows 前置配置

* [安裝WSL連結🔗](/blog/wsl/)

* [安裝VSCode 與配置WSL連結🔗](/blog/visual-studio-code-wsl/)

## C++ 安裝

Ubuntu & WSL(Windows)
```
    sudo apt update 
    sudo apt install build-essential
```
macOS
```
    xcode-select --install
```
## Xmake

Ubuntu & WSL(Windows)
1. Download xmake `.deb` install package from **[Releases](https://github.com/xmake-io/xmake/releases)**
2. Run `dpkg -i xmake-xxxx.deb`
macOS
```
brew install xmake
```


## Conan
Ubuntu & WSL(Windows)
```
sudo apt install python3-pip
pip install conan
```
macOS
```
brew install conan
```
