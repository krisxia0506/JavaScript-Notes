---
title: let作用域
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 11:33
---
# 全局作用域
_全局_（在函数之外）声明的变量拥有 _全局作用域_
如果在块外声明声明，那么 `var` 和 `let` 也很相似。
通过 `var` 关键词定义的全局变量属于 window 对象
加`var`的局部变量不会作为window的属性。
通过 `let` 关键词定义的全局变量不属于 window 对象
```js
var carName = "porsche";
var x = 10;       // 全局作用域
let y = 6;       // 全局作用域

// 此处的代码可以使用 carName
function myFunction() {
  // 此处的代码也可以使用 carName
  document.getElementById("demo").innerHTML = "我可以显示 " + window.carName;
  document.getElementById("demo").innerHTML = "我不能显示 " + window.y;//undefined
}
```

# 函数作用域
_局部_（函数内）声明的变量拥有 _函数作用域_。
在函数内声明变量时，使用 `var` 和 `let` 很相似。
```js
// 此处的代码不可以使用 carName
function myFunction() {
  var carName = "porsche";
  // code here CAN use carName
}

function myFunction() {
  let carName = "porsche";   // 函数作用域
}

// 此处的代码不可以使用 carName
```


# 块作用域
通过 `var` 关键词声明的变量没有块_作用域_。
在块 _{ }_ 内声明的变量可以从块之外进行访问。
```js
{ 
  var x = 10; 
}
// 此处可以使用 x
```

在 ES2015 之前，JavaScript 是没有块作用域的。
可以使用 `let` 关键词声明拥有块作用域的变量。
在块 _{}_ 内声明的变量无法从块外访问：
```js
{ 
  let x = 10;
}

// 此处不可以使用 x
```

# 循环作用域
在循环中使用 `var`：
```js
var i = 7;
for (var i = 0; i < 10; i++) {//执行完内容后i++，再次循环判断i < 10
  // 一些语句
}
// 此处，i 为 10
```

在循环中使用 `let`：
```js
let i = 7;
for (let i = 0; i < 10; i++) {
  // 一些语句
}
// 此处 i 为 7
```


# 重新声明
允许在程序的任何位置使用 `var` 重新声明 JavaScript 变量
在相同的作用域，或在相同的块中，通过 `let` 重新声明一个 `var` 变量是不允许的
```js
var x = 10;       // 允许
var x = 6;        //允许，现在，x 为 10
let x = 6;       // 不允许
{
  var x = 10;   // 允许
  let x = 6;   // 不允许
}
```
在相同的作用域，或在相同的块中，通过 `let` 重新声明一个 `let` 变量是不允许的.
```js
let x = 10;       // 允许
let x = 6;       // 不允许
{
  let x = 10;   // 允许
  let x = 6;   // 不允许
}
```
在相同的作用域，或在相同的块中，通过 `var` 重新声明一个 `let` 变量是不允许的
```js
let x = 10;       // 允许
var x = 6;       // 不允许
{
  let x = 10;   // 允许
  var x = 6;   // 不允许
}
```
在不同的作用域或块中，通过 `let` 重新声明变量是允许的：
```js
let x = 6;       // 允许
{
  let x = 7;   // 允许
}

{
  let x = 8;   // 允许
}
```

# 提升
通过 `let` 定义的变量不会被提升到顶端。