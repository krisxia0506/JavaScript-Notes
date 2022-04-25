---
title: 数据类型
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 13:46
---
```js
var length = 7;                             // 数字
var lastName = "Gates";                      // 字符串
var cars = ["Porsche", "Volvo", "BMW"];         // 数组
var x = {firstName:"Bill", lastName:"Gates"};    // 对象
```

当数值和字符串相加时，JavaScript 将把数值视作字符串。
```js
var x = 911 + "Porsche";
var x = "911" + "Porsche";
```

JavaScript 从左向右计算表达式。不同的次序会产生不同的结果：
```js
var x = 911 + 7 + "Porsche";//918Porsche
var x = "Porsche" + 911 + 7;//Porsche9117
```

# JavaScript 拥有动态类型
JavaScript 拥有动态类型。这意味着相同变量可用作不同类型：
```js
var x;               // 现在 x 是 undefined
var x = 7;           // 现在 x 是数值
var x = "Bill";      // 现在 x 是字符串值
```

您可以在字符串内使用引号，只要这些引号与包围字符串的引号不匹配：
```js
var answer = "It's alright";             // 双引号内的单引号
var answer = "He is called 'Bill'";    // 双引号内的单引号
var answer = 'He is called "Bill"';    // 单引号内的双引号
```

# typeof 运算符
typeof 运算符对数组返回 "object"，因为在 JavaScript 中数组属于对象。
您可使用 JavaScript 的 `typeof` 来确定 JavaScript 变量的类型：
```js
typeof ""                  // 返回 "string"
typeof "Bill"              // 返回 "string"
typeof "Bill Gates"          // 返回 "string"
typeof 0                   // 返回 "number"
typeof 314                 // 返回 "number"
typeof 3.14                // 返回 "number"
typeof (7)                 // 返回 "number"
typeof (7 + 8)             // 返回 "number"
typeof {name:'Bill', age:62} // 返回 "object"
typeof [1,2,3,4]             // 返回 "object" (并非 "array")
typeof null                  // 返回 "object"
typeof function myFunc(){}   // 返回 "function"
typeof true                // 返回 "boolean"
typeof false               // 返回 "boolean"
typeof x                   // 返回 "undefined" (假如 x 没有值)
```

# Undefined
在 JavaScript 中，没有值的变量，其值是 `undefined`。typeof 也返回 `undefined`。
```js
var person;                  // 值是 undefined，类型是 undefined。
```
任何变量均可通过设置值为 `undefined` 进行清空。其类型也将是 `undefined`。
```js
person = undefined;          // 值是 undefined，类型是 undefined。
```

# 空值
空值与 `undefined` 不是一回事。
空的字符串变量既有值也有类型。
```js
var car = "";                // 值是 ""，类型是 "string"
```

# Null
不幸的是，在 JavaScript 中，`null` 的数据类型是对象。
您可以把 `null` 在 JavaScript 中是对象理解为一个 bug。它本应是 `null`。
您可以通过设置值为 `null` 清空对象：
```js
var person = null;           // 值是 null，但是类型仍然是对象
var person = undefined;           // 值是 undefined，类型是 undefined。
```

# Undefined 与 Null 的区别
`Undefined` 与 `null` 的值相等，但类型不相等：
```js
typeof undefined              // undefined
typeof null                   // object
null === undefined            // 等值等类型false
null == undefined             // 等值true
```