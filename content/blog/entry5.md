---
title: C++🐱貓紙(C++ CheatSheet)
tags: C++
category: Programming Languages
excerpt: C++🐱貓紙
created: 2019-05-05
image: ./images/phoenix-han-Nqdh0G8rdCc-unsplash.jpg
image_caption: Photo by Phoenix Han on Unsplash
author: author1
---

### 計算

計算機的本質是計算，所以我們會從四則運算開始,以下是一個 1 + 2 的例子

    #include<iostream>
    using namespace std;
    void main(){
    	cout << 1 + 2 << endl;
    }

- 大家可以將 1 + 2 變成 3 - 4, 5 * 6, 8 / 4，8 / 5 等等，就可以依次輸出 減乘除效果
- 要注意一點， `8 / 5` 會輸出1而不是 `1.6`，C++做除法就像我們小學除法一樣，那麼如果要輸出完整的小數，就要加 `.0`在後面

    #include<iostream>
    using namespace std;
    void main(){
    	cout << 8.0 / 5 << endl; // 1.6
    }

### 變數與輸入

以上的運算是基於確定的數值的，如果我們要計算1 + 2， 1 + 3，就需要編寫兩個程序，那我們可以讀取用戶的輸入獲取結果

    #inlcude<iostream>
    using namespace std;
    void main(){
    	int a, b;
    	cin >> a >> b;
    	cout << a << b;
    }

以上的程序輸入了2個數字並且輸出了

C++的變數就是讓C++ 在電腦中暫時儲存一個資料，像一個盒子一樣，並且貼一個標籤給他，例如說

- `int` 儲存整數
- double儲存小數
- string 儲存文字
- auto儲存任何類型，但需要立刻Assign 數值

例如我要儲存我的名字，那麼

    auto name = "Alan";
    auto age = 21;

`name` 就是 這個文字的標籤🏷️, "Alan" 就是資料了, `auto` 就是告訴C++我要建立一個新資料

類似於 JavaScript 中的 `let` , C# / Java 中的 `var` 。

其他cout例子

    cout << "My name is" << name; //記得寫在main裡面

或者如果要寫在文字中

    auto text = "My name is" << name << "\n Hi";

下面的const是告訴C++這個數據不會改變，就像我對鐵人賽的感覺一樣

    const auto feeling = "IT邦幫忙超正的";

圓柱體體積例子

    #include<iostream>
    #include<math>
    using namespace std;
    void main(){
    	const auto pi = acos(-1.0);
    	cin >> r >> h;
    	auto s1 = pi*r*r;
    	auto s2 = 2*pi*r*h;
    	auto s = s1*2.0 + s2;
    	cout << "Area = "<< s << endl;
    }

其他的小例子

如果你想加速的話可以用 `const` 啊

## If Else 條件公式

### If 與Else

如果我們拿到一個天氣資訊，然後要在“黑盒子”中輸出呢？

    auto temperature = 20;
    auto City = "Hong Kong";
    auto humidity = 81;
    
    if(temperature < 20){
    	cout << "The weather in " << City << " is cold";
    }else if(temperature < 30) {
    	cout << "The weather in " << City << " is OK";
    } else {
    	cout << "The weather in " << City << " is hot";

`<` 是左小於右邊， `>` 是左大於右邊

`<=` 是左小於或者等於右邊， `>=` 是左大於或者等於右邊

`==` 是兩邊等於， `!=` 是兩邊不等於

if 就是如果的意思

在 `if(temperature < 20)` 就是如果溫度 小於20

`else` 就是如果 `if` 不符合，才運行這行

`else if(temperature < 30)` 就是溫度在20 -30 之間

大家可以改動一下溫度🌡️和城市

那麼如果你想為變數加多一個標籤呢？

    auto name1 = "Alan";
    auto name2 = &name1;

這樣子，"Alan" 邊有兩個標籤了，無論閱讀name1還是name2 都會讀到 "Alan"。

當 裝著 "Alan" 的盒子改變時， `name1` 和 `name2` 都會改變

變數類型

在開始下一步之前，先了解一下C++有什麼常用變數類型吧

    int 整數
    float 短小數
    double 小數
    string 文字

### 一排排的變數

假如你想將自己的朋友儲存在C++中，但是你有很多朋友的話，那麼盆友標籤改名的確令人頭疼，例如

    auto friend1 = "Melody";
    auto friend2 = "Tony";
    auto friend3 = "Sally";
    ...
    auto friend300 = "Sam";

C++ 中有Vector這個神器幫你命名

    #include<vector> //先導入vector 庫
    vector<string> friends { "Melody", "Tony", "Sally", "Sam"};
    
    讀取不同的朋友
    cout << friends[0] << endl;
    cout << friends[1] << endl;
    cout << friends[2] << endl;
    cout << friends[3] << endl;

Vector 能將變數一個個加到後面

    friends.emplace_back("Alan");
    friends.emplace_back("Sammi");

當然也能將一個個變數從vector中刪除

    friends.pop_back("Alan");
    friends.pop_back("Sammi");

當然也能在中間加元素

    friends.emplace(friends.begin()+2,"Dummy");

當然也能刪除中間的元素

    friends.erase(friends.begin()+2,"Dummy");

### For Loop

C++ for loop 有兩種類型,第一種是Vector專用

    for (const auto& friend: friends){
    	cout << friend << endl;
    }

第二種是通用For

    // 這裏，for裡面的代碼會運行4 次， 範圍 0 - 4 
    for(int i = 0; i < 5; i++){
    	const << i << endl
    }
    
    // 這裏，for裡面的代碼會運行5 次， 範圍 0 - 5 
    for(int i = 0; i =< 5; i++){
    	const << i << endl
    }
    
    // 這裏，for裡面的代碼會運行 5 次， 範圍倒數 5 - 0 
    for(int i = 5; i >= 0; i++){
    	const << i << endl
    }

大家可能會問，那麼C++ 的vector是只能容納一種類型嗎？如下

    vector<int> {1,2,3,4,5};

其實在C++17也可以容納多種類型了，可以混合類型,像TypeScript,但讀取就比TypeScript困難多了

    #include <any>
    
    vector<any> {1,"Alan","Haha",4,5};
    
    for (const auto& a: v) {
        try {
            cout << any_cast<int>(a) << endl;
        } catch (const bad_any_cast&)
        {}
    
        try {
            std::cout << any_cast<string>(a) << endl;
        } catch (const bad_any_cast&)
        {}
      }

畢竟現在連前端都比較喜歡 `TypeScript`了，vector 只能容納一個類型的特性令到代碼的問題少很多。

### Vector 的變種

C++的Vector有很多種變種，但用法是差不多的，只是適用的情景不同，我列一下其他Vector的變種

    List ｜ 新增emplace_front, pop_front,增加數值性能比較高，讀取比較慢
    Deque | 新增emplace_front, pop_front,性能中庸
    Stack ｜ Vector弱化版，只能使用 pop 和 push

    //建立
    vector<int> numbers_v = {1,5,3,5,6,3,2};
    list<int> numbers_l = {1,5,3,5,6,3,2};
    deque<int> numbers_d = {1,5,3,5,6,3,2};
    string numbers{"1535632"}
    
    //建立 String
    string str = "hello";
    auto str = "hello"s;
    auto str = "hello"sv; //這是constant不變String
    
    // List 和 Deque 都有在前方插/刪除元素的功能
    numbers_l.emplace_front(2);
    numbers_d.emplace_front(4);
    numbers_l.pop_front(2);
    numbers_l.pop_front(2);