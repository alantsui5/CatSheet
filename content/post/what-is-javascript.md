---
title: ❓What is JavaScript?
description: This tutorial help you understand and bootstrap JavaScript
slug: what-is-javascript
date: 2022-12-14 00:00:00+0000
image: 
categories:
    - JavaScript
tags:
    - frontend
weight: 1
---

## ❓ What is JavaScript？
✅ JavaScript is a client-side scripting language. This language can update HTML and CSS and can be run on the browser. JavaScript can __calculate, manipulate and validate data.__

## ❓ How to install JavaScript？
✅ Please reference [How to install NodeJS 18](/p/install-nodejs).

## ❓ What is the language characteristics of JavaScript?
✅ A language of High-Level, single-threaded, garbage-collected, interpreted(or just-in-time compiled), prototype-based, multi-paradigm, dynamic language with a non-blocking event loop

### ❓ What is mean by **High Level**?
✅ High-Level refers to the abstraction the language provides over the machine’s bare-metal hardware. JavaScript is considered high-level because it does not require direct interaction with the operating system, hardware. In addition, it does not require memory-management like C/C++ because the runtime always uses garbage-collection.

### ❓ What is mean by **Multi-Paradigm**?
✅ **Multi-Paradigm** means the language is general-purpose or flexible. JS can be used for declarative (functional) or imperative (object-oriented) programming styles.

### ❓ Is JavaScript __Interpreted__ or __Just-In-Time Compiled__?
✅ **Interpreted** means the source code is converted to **[bytecode](https://en.wikipedia.org/wiki/Bytecode)** and executed at runtime (as opposed to being compiled to a machine code binary at build time). This is also why JS is commonly called a “scripting language”.
 > It was only interpreted, but modern JS engines like V8, Spidermonkey, and Nitro use various techniques to perform _Just-in-Time Compilation_ or JIT for better performance. Developers still use JS like an interpreted language, while the engine magically compiles parts of source code to low-level machine code behind the scenes.

### ❓ What is mean by __prototype-based__?
✅ Prototypal Inheritance means that objects can inherit behaviours from other objects.
This differs from classical inheritance where you define a **`class`** or blueprint for each object and instantiate it.

### ❓ Why JS is a **Single-Threaded**?
✅ **Single-Threaded** means that JS can only run one instruction at a time, even if your CPU has multiple cores and available threads.

## ❓ How does JavaScript **handle jobs at the same time concurrently**?
✅ **Event Loop** refers to a feature implemented by engines like V8 that allow JS to offload tasks to separate threads.
1. Browser and Node APIs execute long-running tasks separately from the the main JS thread
2. Then enqueue a **`callback`** function (which you define) to run on the main thread when the task is complete.
3. This is why JS is called _**non-blocking**_ because it should only ever wait for synchronous code from your JS functions.
4. Think of the **[Event Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)** as message queue between the single JS thread and the OS.

### Blocking Event Loop Example
```javascript
// L1
console.log('🥪 Synchronous 1');

// L2
setTimeout(_ => console.log(`🍅 Timeout 2`), 0);

// L3
Promise.resolve().then(_ => console.log('🍍 Promise 3'));

// L4
console.log('🥪 Synchronous 4');

// Output
// 🥪 Synchronous 1
// 🥪 Synchronous 4
// 🍍 Promise 3
// 🍅 Timeout 2
```
**Explanation:** It will add **Sync**, **Promise**, **Timeout** Code to the event queue, and then check or pop the task with task priority: 
- **1. Sync Task**
- **2. Promise(Microtask)**
- **3. Timeout(Macrotask)**

**‼Particularly:** If the microtask can not be done in a event loop, it will switch order with macro task.

### Another Blocking Event Loop Example
`Promise.resolve(result)` without wrapping the task is still blocking
```jsx
// Pre-defined slow task
const codeBlocker = () => {

	return new Promise((resolve, reject) => {
		let i = 0;
		while(i < 1000000000) {i++;}
		
		resolve('🐷 billion loops done');
	})
}

// L1
console.log('🥪 Synchronous 1');

// L2
codeBlocker.then(log);

// L3
console.log('🥪 Synchronous 2');

// Output
// 🥪 Synchronous 1 <0ms>
// 🥪 Synchronous 2 <730ms>
// 🐷 billion loops done <731ms>
```
**Explanation:**: The only line in the above code treated as micro task is resolve`('🐷 billion loops done')`, not the time consuming task.


### Promise.resolve().then(result and task) is non-blocking finally
```jsx
// Pre-defined slow task
const codeBlocker = () => {

	return Promise.resolve().then(v => {
		let i = 0;
		while(i < 1000000000) {i++;}
		
		return('🐷 billion loops done');
	})
}

// L1
console.log('🥪 Synchronous 1');

// L2
codeBlocker.then(log);

// L3
console.log('🥪 Synchronous 2');

// Output
// 🥪 Synchronous 1 <0ms>
// 🥪 Synchronous 2 <4ms>
// 🐷 billion loops done <731ms>
```

## References
- [How JavaScript Works](https://fireship.io/courses/javascript/intro-how-js-works/)
- [What is JavaScript](https://www.w3schools.com/whatis/whatis_js.asp)