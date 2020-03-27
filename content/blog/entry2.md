---
title: React貓紙
tags: JavaScript, React
category: Frontend
excerpt: 歡迎來到React世界
created: 2020-03-28
image: ./images/lukasz-szmigiel-jFCViYFYcus-unsplash.jpg
image_caption: Photo by Luasz Szmigiel on Unsplash
author: author1
---

## React
[React REPL Lab Link](https://codesandbox.io/s/template-qbd66)
### 展示HTML
```jsx=
import React from 'react'
function App(){
    return (
        <h1>Hello World</h1>
    )
}
```
### 展示2個html內容
```jsx=
import React from 'react'
function App(){
    return (
        <>
        <h1>Hello World</h1>
        <p>Hello Adrain</p>
        </>
    )
}
```
### 使用變數，處理Data
我們先新建一個 `counter.jsx`，然後把這些貼上
```jsx=
import React,{useState} from 'react'
//導出這個Counter，將他變成一個組件庫
export default function Counter(){
    // 建立變量
    const [count, setCount] = useState(0);

    return (
        // 展示變量
        <button>{count}</button>
    )
}
```

### Import 組件
想在`App.js`當中展示我們的`counter`,我們就需要把他導入
```jsx=
import React,{useState} from 'react'
// 導入我們的Counter
import Counter from './counter'
function App(){
    return (
        <>
        <h1>Hello World</h1>
        <p>Hello Adrain</p>
        <Counter />
        </>
    )
}
```

### 人機交互

在react當中有很多人機交互方法，最常用的就是按按鈕了，
就是`onClick`動作，當按住一個有`onClick`的按鈕的時候，語法是 `onClick={想在按住時運行的函數}`，這樣我們就可以在console看到`count` 了
`Counter.js`
```jsx
import React,{useState} from 'react'
function App(){
    const [count, setCount] = useState(0);
    function logCount(){
        console.log(count)
    }
    return (
        <button onClick={logCount}>{count}</button>
    )
}
```

### 變數加減
React會使用`setCount`函數(就是變量旁邊那個）改動數值,`setCount(新數值)`，這樣一個有減法的計算器就完成了！！
`Counter.js`
```jsx
import React,{useState} from 'react'
function App(){
    const [count, setCount] = useState(0);
    function logCount(){
        console.log(count);
    }
    function increase(){
        setCount(count++);
    }
    function decrease(){
        setCount(count--);
    }
    return (
    <>
        <button onClick={increase}>Increase</button>
        <button onClick={logCount}>{count}</button>
        <button onClick={decrease}>Decrease</button>
    </>    
    )
}
```

### React Hook Class
有時，我們會希望logic和UI分開，這時候，我們可以使用一個custom hook的功能
```jsx
import React,{useState} from 'react'

function useCounter(){
    let [count, setCount] = useState(0);
    function logCount(){
        console.log(count);
    }
    function increase(){
        setCount(count++);
    }
    function decrease(){
        setCount(count--);
    }
    return {count, increase, decrease};
}
function App(){
    let counter = useCounter();
    
    return (
    <>
        <button onClick={counter.increase}>Increase</button>
        <button onClick={counter.logCount}>{counter.count}</button>
        <button onClick={coutner.decrease}>Decrease</button>
    </>    
    )
}
```

### React 處理連結是一個不少的問題，那麼
我們可以在`App.js`當中建立路由管理器，然後將頁面當成是 Component一樣放進路由管理器，這和Vue/Angular是相似的
```jsx
import {useRoutes, A} from 'hookrouter'
imoort Counter from './Counter.js'

//這些是模擬頁面
const Home =  () => "我是主頁";
const Product = ()=> "我是貨品頁";
const NotFound =  () => "我不存在";
const ProductDetails = (id)=>"我是貨品,編號是{id}";

const pages = {
    '/':()=> <Home />,
    '/Counter':()=> <Counter />,
    '/home':()=> <Home />,
    '/product': ()=> <Product />,
    '/product/:id': ({id})=> <ProductDetails id={id} />
}

const App(){
    const pageResult = useRoutes(pages);
    return (
        <div>
            <A href="/counter"><Counter /></A>
            <A href="/">Return Home</A>
            <A href="/product">Product Page</A>
            <A href="/product/1dsdwe3eg">Single Product</A>
            pageResult || <NotFound />
        </div>
        
    )
}