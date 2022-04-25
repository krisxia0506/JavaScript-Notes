---
title: 改变内容
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-24 14:05
---
# 改变 HTML 内容
`getElementById()` 是多个 JavaScript HTML 方法之一。

`getElementByClassName()`

`getElementByName()`

`getElementsByTagName("a")[0]`

本例使用该方法来“查找” id="demo" 的 HTML 元素，并把元素内容（`innerHTML`）更改为 "Hello JavaScript"：
```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript 能做什么</h2>

<p id="demo">JavaScript 能够改变 HTML 内容。</p>

<button type="button" onclick='document.getElementById("demo").innerHTML = "Hello JavaScript!"'>点击我！</button>

</body>
</html>
提示：JavaScript 同时接受双引号和单引号
```
```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction() {
    document.getElementById("demo").innerHTML = "段落被更改。";
}
</script>
</head>

<body>

<h1>一张网页</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">试一试</button>

</body>
</html>
```

改变了其自身元素的内容

```html
<!DOCTYPE html>
<html>
<body>

<h1>JavaScript 事件</h1>

<button onclick="this.innerHTML=Date()">时间是？</button>

</body>
</html>

```



# 改变 HTML 属性

```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript 能做什么？</h2>

<p>JavaScript 能够改变 HTML 属性值。</p>

<p>在本例中，JavaScript 改变了图像的 src 属性值。</p>

<button onclick="document.getElementById('myImage').src='/i/eg_bulbon.gif'">开灯</button>

<img id="myImage" border="0" src="/i/eg_bulboff.gif" style="text-align:center;">

<button onclick="document.getElementById('myImage').src='/i/eg_bulboff.gif'">关灯</button>

</body>
</html>


```

# 改变 HTML 样式 (CSS)
```js
document.getElementById("demo").style.fontSize = "25px";
```

# 隐藏 HTML 元素
```js
document.getElementById("demo").style.display="none";
```

# 外部脚本
您可以在 `<head>` 或 `<body>` 中放置外部脚本引用。
```html
<script src="myScript.js"></script>
```