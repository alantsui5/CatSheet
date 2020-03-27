---
title: JavaScript貓紙
tags: JavaScript
category: Programming Languages
excerpt: 本篇將帶你們了解JavaScript的語法部分
created: 2020-03-28
image: ./images/josh-spires-dronenr-sQalFlXIsLs-unsplash.jpg
image_caption: Photo by Josh Spires on Unsplash
author: author1
---

## 變數(Variable)

```javascript=
let age = 17
let name = `Tony`
```
## 常數(Constant)
```javascript=
const pi = 3.14
```
## 普通函數(Function)
```javascript=
function sayHello(){
    console.log(`Hello`);
}

function GreetWith（name）{
    console.log(`Hello ${name}`)
}
sayHello()
GreetWith('CCL')
```
## 函數式(Arrow function)
```javascript=
const sayHello = () => console.log(`Hello`);

const GreetWith = name => console.log(`Hello ${name}`)

sayHello()
GreetWith('CCL')
```

## 矩陣（Array)
```javascript=
let numbers = [1,2,3,4,5]
```
Array Manipulation
```javascript=
numbers = [1.345,...numbers]

numbers = [...numbers,2.765]

numbers.splice(index,numberOfElementToBeRemoved)
```
## Dictionary / Object
```javascript=
let person = {
    name:'Tony',
    age: 21,
    displayDetails(){
        console.log(`${this.name} ${this.age}`)
    }
}

person.name

person.age

person.displayDetails()
```

## 更改物件
```javascript=
// Eg: change the age of Tony
person = {...person,age:20}
```

## JSON ( Array of Dictionary)
```javascript=
let persons = [
    {
        name:'Tony',
        age: 21
    },
    {
        name:'Michael',
        age: 20
    }
]
```

## Array Operators
```javascript=
// Iterate and read Array
persons.forEach( function(person){
    console.log(`${person.name} `{person.age}`)
    }
}

//Iterate and modify array, this is adding age by 1 for each object
persons.map( person => {
        person.age++
    }
}

persons.filter( person => {
    person.age >= 20
    }
}
```

## Export
```javascript=

// Private data
export let age = 30

//Public Data
let name = `Alan`
```
## Class
```javascript=
class Person {
    constructor(name,age){
        this.name = name
        this.age = age
    }
    getName(){
        return this.name
    }
    getAge(){
        return this.age
    }
}
let tony = new Person('Tony',21)
```
