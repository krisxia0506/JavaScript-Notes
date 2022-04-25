---
title: 输出
categories:
  - JavaScript学习
  - /
tags:
  - JavaScript笔记
description: 
cover: 
abbrlink: 
date: 2022-04-25 09:29
---

## JavaScript 显示方案

JavaScript 能够以不同方式“显示”数据：

-   使用 `window.alert()` 写入警告框
-   使用 `document.write()` 写入 HTML 输出
-   使用 `innerHTML` 写入 HTML 元素
-   使用 `console.log()` 写入浏览器控制台

## 使用 document.write()
出于测试目的，使用 `document.write()` 比较方便：
```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张网页</h1>

<p>我的第一个段落</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```
注意：在 HTML 文档完全加载后使用 `document.write()` 将_删除所有已有的 HTML_ ：
```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张网页</h1>

<p>我的第一个段落</p>

<button onclick="document.write(5 + 6)">试一试</button>

</body>
</html>
```

## 使用 window.alert()
您能够使用警告框来显示数据：
直接出现
```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张网页</h1>

<p>我的第一个段落</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

点击按钮才会出现
```html
<!DOCTYPE html>
<html>
<body>

<h2>我的第一张网页</h2>
<p>我的第一个段落。</p>
<button onclick="a()">点击</button>

<script>
function a() {
window.alert(5 + 6);
}
</script>

</body>
</html>

```

## 使用 console.log()
```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张网页</h1>

<p>我的第一个段落</p>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```