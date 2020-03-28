---
title: 第一個C++程序（First C++ Program)
tags: C++
category: Programming Languages
excerpt: 第一個C++程序
created: 2019-04-01
image: ./images/menghan-zhang-gnoY8Z0umg4-unsplash.jpg
image_caption: Photo by Menghan Zhang on Unsplash
author: author1
---

在 Day 1 - Day 10當中我們會探討下 C++的基本用法，所以大家打開

[GDB online Debugger | Compiler - Code, Compile, Run, Debug online C, C++](https://www.onlinegdb.com/)

將Language 設定成C++17就可以了！！！

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ae3df19f-fa33-4e40-b95f-905340f76579/Screenshot_2020-03-12_at_7.43.16_PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ae3df19f-fa33-4e40-b95f-905340f76579/Screenshot_2020-03-12_at_7.43.16_PM.png)

並且我們將網頁中的代碼變成

    #include<iostram>
    using namespace std;
    int main(){
    
    	cout << "Hi!";
    	return 0;
    }

然後點擊run就可以見到“Hi”了！！！

先解釋一下這個程序的用途吧

    #include<iostram>
    

是用來導入 cout 和 cin 兩個功能了，沒有了這句，就不能用cout啦

下面的 `using namespace std`就是指預設使用 standard library

    using namespace std;

    cout << "Hi"

是用來在console（也是俗稱的黑盒子）中輸出（out） “Hi”的。

除了“HI”以外， `cout` 也也可以打印數字，甚至混合能數字和文字（string）的，例如說

    cout << "Hi" << 4; // "Hi4"
    cout << 4.12; // "4.12"

要換行的話，也有兩個方法，就是 `endl` 和 `"/n"`

    cout 4 << endl; // 方法1
    cout << "Hi" << "\n"; // 方法2

用什麼方法隨你喜歡啦，反正也一樣。

下面的 `main()` 就是一個函數，寫過Java/JavaScript 的人應該好熟悉了

    int main(){
    	//...
    	return 0;
    }

這個函數是用來告訴 C++：「這是你要運行的內容哦」。所以你要運行的代碼，基本上要寫進去。

main函數有兩種寫法

    // 方法1
    int main(){
    	//...
    	return 0;
    }
    
    //方法2
    void main(){
    	//...
    }

第一種方法有 int在前面，就是說main() 要輸出一個 數字給C++，所以就要 `return 0`, 至於 `void`，就是沒有輸出。所以沒有 `return`

功課：

你可以將黑盒子中的 “Hi”變成其他東西的，試試打印出自己的名字，年齡，和來看這個系列的原因吧，例如

    我是 Alan
    我 21 歲
    鐵人賽萬歲