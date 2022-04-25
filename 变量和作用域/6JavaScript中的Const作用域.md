---
title: Const作用域
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 12:53
---
# Const
通过 `const` 定义的变量与 `let` 变量类似，但不能重新赋值
`const` 变量必须在声明时赋值
### 实例
```js
const PI = 3.141592653589793;
PI = 3.14;      // 会出错
PI = PI + 10;   // 也会出错
```

## 不是真正的常数
关键字 `const` 有一定的误导性。
它没有定义常量值。它定义了对值的常量引用。
因此，我们不能更改常量原始值，但我们可以更改常量对象的属性。

## 常量对象可以更改
```js
// 您可以创建 const 对象：
const car = {type:"porsche", model:"911", color:"Black"};

// 您可以更改属性：
car.color = "White";

// 您可以添加属性：
car.owner = "Bill";
```
## 无法重新为常量对象赋值：
```js
const car = {type:"porsche", model:"911", color:"Black"};
car = {type:"Volvo", model:"XC60", color:"White"};    // ERROR
```

## 常量数组可以更改
```js
// 您可以创建常量数组：
const cars = ["Audi", "BMW", "porsche"];

// 您可以更改元素：
cars[0] = "Honda";

// 您可以添加元素：
cars.push("Volvo");
```

## 无法重新为常量数组赋值：
```js
const cars = ["Audi", "BMW", "porsche"];
cars = ["Honda", "Toyota", "Volvo"];    // ERROR
```


## 重新声明
在程序中的任何位置都允许重新声明 JavaScript `var` 变量：
```js
var x = 2;    //  允许
var x = 3;    //  允许
x = 4;        //  允许
```

在同一作用域或块中，不允许将已有的 `var` 或 `let` 变量重新声明或重新赋值给 `const`：
```js
var x = 2;         // 允许
const x = 2;       // 不允许
{
  let x = 2;     // 允许
  const x = 2;   // 不允许
}
```

在同一作用域或块中，为已有的 const 变量重新声明声明或赋值是不允许的：
```js
const x = 2;       // 允许
const x = 3;       // 不允许
x = 3;             // 不允许
var x = 3;         // 不允许
let x = 3;         // 不允许
{
  const x = 2;   // 允许
  const x = 3;   // 不允许
  x = 3;         // 不允许
  var x = 3;     // 不允许
  let x = 3;     // 不允许
}
```

在另外的作用域或块中重新声明 `const` 是允许的：
```js
const x = 2;       // 允许

{
  const x = 3;   // 允许
}

{
  const x = 4;   // 允许
}
```


## 提升
通过 `const` 定义的变量不会被提升到顶端。

`const` 变量不能在声明之前使用：

```js
carName = "Volvo";    // 您不可以在此处使用 carName
const carName = "Volvo";
```