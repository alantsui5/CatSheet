---
title: Visual Studio Code 與WSL強強聯合
tags: Visual Studio Code, VSCode, IDE, WSL
category: Configurations
excerpt: 在VSCode 中安裝WSL教學
created: 2019-09-03
image: ./images/sergio-souza-mvb51ThjvRA-unsplash.jpg
image_caption: Photo by Sergio Souza on Unsplash
author: author1
---


最近在思考如何讓[我的插件](https://marketplace.visualstudio.com/items?itemName=jaycetyle.vscode-gnu-global)能夠跑在 WSL 裡面，後來發現了 [Visual Studio Code Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl) 這個好東西，它可以讓 VS Code Server 實際執行在 WSL 裡面，只留 UI 介面在 Windows。

這對某些插件非常有用，因為有些東西跑在 Linux 環境是比較容易的。另外 Visual Studio Code Remote 系列還包含 Remote - SSH 模式，這東西就更猛了，如果你的 Build Machine 是遠端的 Linux Server ，他可以直接透過 SSH 跑在 Linux Server 端，像是檔案搜尋等動作，直接執行在遠端 Linux 就會比透過 Samba 或 NFS 快上很多。

# **環境安裝**

想要使用 VS Code Remote - WSL，你必須要安裝以下三個東西

1. Visual Stuio Code
2. WSL (Windows Subsystem Linux)
3. Visual Studio Code Remote - WSL 插件

嗯 … 非常直覺，不需要額外安裝什麼。WSL 的部分在 [Windows Subsystem for Linux 安裝](https://blog.jaycetyle.com/2018/01/win-subsys-linux/) 這篇文章有教學。插件安裝也很簡單，打開 Visual Studio Code Extensions 搜尋 Remote - WSL 就可以找到並安裝

![https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-1.png](https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-1.png)

# **在 Remote - WSL 中開啟專案**

按下 F1 ，執行 `Remote-WSL: New Window` 可以開啟一個執行在 WSL 的視窗，或是執行 `Remote-WSL: Reopen Folder in WSL`，直接將目前開啟的目錄改在 WSL 中執行。

![https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-2.png](https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-2.png)

成功開啟專案後，你會發現左下角多了 WSL 的圖示，另外開啟 Terminal 也會直接進到 WSL，真的非常方便！

![https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-3.png](https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-3.png)

# **在 Remote - WSL 中安裝插件**

如果有想安裝其他插件的話，Remote - WSL 環境內是需要另外安裝的，畢竟執行環境已經跑到 WSL 裡面了。

到插件中心會發現插件被分成了 Local 和 WSL 部分，要把插件安裝到 Remote 也很簡單，點擊綠色的 Install on WSL，他就會安裝在 WSL

![https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-4.png](https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-4.png)

Remote - WSL 的參數設定也是獨立的，從 File > Preferences > Settings 打開設定頁面，會發現多了 Remote[WSL] 部分，你可以針對 Remote - WSL 有獨立的設定。

![https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-5.png](https://blog.jaycetyle.com/images/2019/07/vscode-remote-wsl-5.png)

轉載自

[Visual Studio Code Remote - WSL 安裝教學](https://blog.jaycetyle.com/2019/07/vscode-remote-wsl/)