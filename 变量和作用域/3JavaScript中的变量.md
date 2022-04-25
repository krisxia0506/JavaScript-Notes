---
title: 变量
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 10:14
---
# var关键词告知浏览器创建新的变量
JavaScript 不会把 _VAR_ 或 _Var_ 译作关键词 _var_。
```html
<!DOCTYPE html>
<html>
<body>

<h2>var 关键词创建变量</h2>

<p id="demo"></p>

<script>
var x, y;
x = 7 + 8;
y = x * 10;
document.getElementById("demo").innerHTML = y;//150
</script>

</body>
</html>

```

# 不使用var
在函数内部使用var声明变量时，声明的是局部变量，函数外部是无法访问的。没有用var声明的变量是全局变量，函数外部是可以访问到的。

# 注释
双斜杠 `//` 或 `/*` 与 _*/_ 之间的代码被视为 _注释_ 。

# 一条语句，多个变量
逗号分隔，可以换行
```js
var person = "Bill Gates", carName = "porsche", price = 15000;
var person = "Bill Gates",
carName = "porsche",
price = 15000;
```

# Value = undefined
不带有值的变量，它的值将是 `undefined`。

变量 carName 在这条语句执行后的值是 `undefined`

```js
var carName;
document.getElementById("demo").innerHTML = carName;//undefined
```

# 重复声明 JavaScript 变量
如果再次声明某个 JavaScript 变量，将不会丢它的值。
在这两条语句执行后，变量 carName 的值仍然是 "porsche"：

```js
var carName = "porsche";
var carName;
```

# 如果把要给数值放入引号中，其余数值会被视作字符串并被级联。
```js
var x = 3 + 5 + "8"//88
```