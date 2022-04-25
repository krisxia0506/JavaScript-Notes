---
title: 变量提升
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 12:28
---

无论作用域的声明出现在任何地方，都将在代码被执行前首先处理。所有的声明（变量和函数）都会被“移动”到各自的作用域最顶端，这个过程被称为提升。js会把所有的变量先声明，在赋值。函数提升有些差别，只会提升函数声明，不会提升函数表达式。函数提升是将整个函数整体提升到作用域的最开始位置，相当于剪切过去的样子。隐式全局变量不会提升!

```js

var a = 1
b = 2
function c() {}
var d = 3

//实际js执行顺序
var a;
function c() {}
var d;
a = 1
b = 2
d = 3

```

```js
function foo() {
  console.log(a); // a(){}
  console.log(b); // is not undefined
  var a = 1;
  b = 2
  console.log(a); // 1
  function a() {}
  console.log(a); //1
  console.log(b); //2
}
foo();

//实际js执行顺序
function foo() {
  var a;
  function a() {}
  console.log(a);
  console.log(b);
  a = 1
  console.log(a)
  console.log(a)
  console.log(b);
}

```

通过 `let` 定义的变量不会被提升到顶端。
在声明 `let` 变量之前就使用它会导致 ReferenceError。
变量从块的开头一直处于“暂时死区”，直到声明为止：
### 实例
```js
// 在此处，您不可以使用 carName
let carName;
```