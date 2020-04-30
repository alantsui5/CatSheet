---
title: WSL貓紙
tags: Windows, WSL, Windows Sub System Of Linux, Linux
category: Configurations
excerpt: 在Windows中簡易安裝WSL
created: 2019-08-02
image: ./images/sadanand-lowanshi-6AnDyJ10_iQ-unsplash.jpg
image_caption: Photo by Sadanand Lowanshi on Unsplash
author: author1
---

![https://img1.xenby.com/226/61ed3ff9.jpg](https://img1.xenby.com/226/61ed3ff9.jpg)

在Windows環境中有許多好用的視窗程式工具(例如微軟的office系列)，可是如果是指令工具在Windows 下功能就比較缺乏，而現在 Windows 支援在系統上執行 linux 子系統 (Windows Subsystem for Linux)，可以直接在 windows 環境下直接快速使用 linux 指令，達到兩全其美的效果，本篇教學如何安裝與使用 Windows Subsystem for Linux。

點[開始]功能旁邊的搜尋按鈕 (放大鏡圖示)

![https://img1.xenby.com/226/be3362c6.jpg](https://img1.xenby.com/226/be3362c6.jpg)

並且搜尋 Windows PowerShell

![https://img1.xenby.com/226/c9773cd9.jpg](https://img1.xenby.com/226/c9773cd9.jpg)

對 Windows PowerShell 點選右鍵 => 以系統管理員身分執行

![https://img1.xenby.com/226/1f111312.jpg](https://img1.xenby.com/226/1f111312.jpg)

輸入以下指令後

    Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux

之後會詢問是否要重新開啟，輸入 Y 後重新開機

![https://img1.xenby.com/226/da7ea1f3.jpg](https://img1.xenby.com/226/da7ea1f3.jpg)

接著就可以到 Microsoft Store 安裝自己習慣使用的 Linux 版本

以下為連結:

- [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
- [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
- [OpenSUSE Leap 15](https://www.microsoft.com/store/apps/9n1tb6fpvj8c)
- [OpenSUSE Leap 42](https://www.microsoft.com/store/apps/9njvjts82tjx)
- [SUSE Linux Enterprise Server 12](https://www.microsoft.com/store/apps/9p32mwbh6cns)
- [SUSE Linux Enterprise Server 15](https://www.microsoft.com/store/apps/9pmw35d7fnlx)
- [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
- [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
- [適用于 WSL 的 Fedora Remix](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
- [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
- [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
- [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

這邊以 Ubuntu 18.04 LTS 為例

點選連結後，按下 [取得]

![https://img1.xenby.com/226/61ed3ff9.jpg](https://img1.xenby.com/226/61ed3ff9.jpg)

等待下載安裝完成

![https://img1.xenby.com/226/796d06e3.jpg](https://img1.xenby.com/226/796d06e3.jpg)

安裝完後點 [啟動]

![https://img1.xenby.com/226/fe67b9c2.jpg](https://img1.xenby.com/226/fe67b9c2.jpg)

![https://img1.xenby.com/226/19d794da.jpg](https://img1.xenby.com/226/19d794da.jpg)

第一次啟動時需要建立使用者帳號與密碼

![https://img1.xenby.com/226/950b43ca.jpg](https://img1.xenby.com/226/950b43ca.jpg)

成功後就能夠開始使用了

![https://img1.xenby.com/226/03917893.jpg](https://img1.xenby.com/226/03917893.jpg)

### 如何在 WSL 中安裝套件?

在 linux 下安裝方式相同，使用該系統安裝指令就可以了

例如 ubuntu 的安裝方式:

    sudo apt install [package-name]

### 如何從 Powershell 直接轉換至 WSL 環境

直接輸入指令 wsl 便可

    wsl

### 如何直接在 Windows PowerShell 中執行 linux 的指令?

只要在 PowerShell 輸入 linux 指令前加上 wsl 就可以了

    wsl [command]

### 如何在 WSL 中存取 windows 系統中的檔案?

windows 的檔案系統會被 mount 在 /mnt/ 下，例如 D槽 就會是對應在 /mnt/d，可以到該路徑下使用

### WSL 中的檔案會存在 Windows 中的哪個位置?

WSL 系統中的檔案會存在下面路徑中 (其中的[****]會依據安裝的Linux系統版本而有所不同)

    C:\Users\%UserName%\AppData\Local\Packages\CanonicalGroupLimited.[****]\LocalState\rootfs

轉載自此網站

[[推薦] WSL (Windows Subsystem for Linux) 安裝與使用教學 | 辛比誌](https://xenby.com/b/226-%E6%8E%A8%E8%96%A6-wsl-windows-subsystem-for-linux-%E5%AE%89%E8%A3%9D%E8%88%87%E4%BD%BF%E7%94%A8%E6%95%99%E5%AD%B8)
