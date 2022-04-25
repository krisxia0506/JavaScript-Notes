---
title: 对象
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 16:09
---

# 创建对象

```js
var car = {type:"porsche", model:"911", color:"white"};
```

# 对象中可以有方法

```js
var person = {
  firstName: "Bill",
  lastName : "Gates",
  id       : 678,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

# this关键词
在函数定义中，`this` 引用该函数的“拥有者”。
在上面的例子中，`this` 指的是“拥有” fullName 函数的 *person 对象*。
换言之，`this.firstName` 的意思是 *this 对象*的 firstName 属性。

# 访问对象属性

对象名.属性名

```js
person.lastName;
person["lastName"];
```

# 访问对象方法

对象名.方法名()

```js
name = person.fullName();
```

如果*不使用 ()* 访问 fullName 方法，则将返回*函数的内容*









