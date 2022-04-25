---
title: 函数
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 15:25
---

# JavaScript 函数语法
```js
function name(参数1, 参数2, 参数3) {
    要执行的代码
}
```

## 函数调用
函数中的代码将在其他代码调用该函数时执行：
-   当事件发生时（当用户点击按钮时）
-   当 JavaScript 代码调用时
-   自动的（自调用）

## 函数返回
当 JavaScript 到达 `return` 语句，函数将停止执行。
如果函数被某条语句调用，JavaScript 将在调用语句之后“返回”执行代码。
函数通常会计算出 _返回值_。这个返回值会返回给调用者：
```js
var x = myFunction(7, 8);        // 调用函数，返回值被赋值给 x=56
function myFunction(a, b) {
    return a * b;                // 函数返回 a 和 b 的乘积
}
```

把华氏度转换为摄氏度：
```js
function toCelsius(fahrenheit) {
    return (5/9) * (fahrenheit-32);
}

document.getElementById("demo").innerHTML = toCelsius(77);
```

## () 运算符调用函数
使用上面的例子，`toCelsius` 引用的是函数对象，而 `toCelsius()` 引用的是函数结果。
```js
function toCelsius(fahrenheit) {
    return (5/9) * (fahrenheit-32);
}

document.getElementById("demo").innerHTML = toCelsius;
```
此时demo标签输出的是function toCelsius(f) { return (5/9) * (f-32); }

## 用作变量值的函数
函数的使用方法与变量一致，在所有类型的公式、赋值和计算中。
使用变量来存储函数的值：
```js
var x = toCelsius(77);
var text = "The temperature is " + x + " Celsius";
```
您能够把函数当做变量值直接使用：
```js
var text = "The temperature is " + toCelsius(77) + " Celsius";
```


## 局部变量
在 JavaScript 函数中声明的变量，会成为函数的_局部变量_。
局部变量只能在函数内访问。

```js
// 此处的代码不能使用 carName
function myFunction() {
    var carName = "Volvo";
    // 此处的代码可以使用 carName
}

// 此处的代码不能使用 carName
```
由于局部变量只能被其函数识别，因此可以在不同函数中使用相同名称的变量。
`局部变量在函数开始时创建，在函数完成时被删除。`



# 匿名函数

**在javascript中，函数可以没有名字**

```js
function(a, b) { //匿名函数
    return a + b;}
```

```js
//把函数作为一个值直接赋值给变量 f
var f = function (a, b) {  
    return a + b;};
console.log(f(1,2));  //返回值3
```

```js
console.log( //把函数作为一个操作数进行调用  
    (function (a,b) {return a + b; })(1, 2)); //返回数值3
```











