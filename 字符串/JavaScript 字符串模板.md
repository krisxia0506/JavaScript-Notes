# Back-Tics 语法

*模板字面量*使用反引号 (``) 而不是引号 ("") 来定义字符串



# 字符串内的引号

通过使用*模板字面量*，您可以在字符串中同时使用单引号和双引号：

```js
let text = `He's often called "Johnny"`;
```



## 多行字符串

*模板字面量*允许多行字符串

实际显示时不会换行

```js
let text =
`The quick
brown fox
jumps over
the lazy dog`;
```



## 变量替换

*模板字面量*允许字符串中的变量：

```js
let firstName = "Bill";
let lastName = "Gates";

let text = `Welcome ${firstName}, ${lastName}!`;
```



## 表达式替换

*模板字面量*允许字符串中的表达式：

```js
let price = 10;
let VAT = 0.25;

let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;
```

## HTML 模板

```js
let header = "Templates Literals";
let tags = ["template literals", "javascript", "es6"];

let html = `<h2>${header}</h2><ul>`;
for (const x of tags) {
  html += `<li>${x}</li>`;
}

html += `</ul>`;
```









































