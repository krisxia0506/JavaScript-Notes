

# 查找字符串中的字符串

## indexOf(item,start)

`indexOf()` 方法返回字符串中指定文本**首次**出现的索引（位置），从0开始

使用方法是`字符串.indexOf()`

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China");//17
"The full name of China is the People's Republic of China.".indexOf("China");//17
var pos = str.indexOf("The");//0
```
设置起始位置

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("China", 18);//51
```

## lastIndexOf(item,start)

`lastIndexOf()` 方法返回指定文本在字符串中**最后**一次出现的索引

**从尾到头检索**

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.lastIndexOf("China");//51
```

如果未找到文本， `indexOf()` 和 `lastIndexOf()` 均返回 -1。

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.indexOf("USA");//-1
```

`lastIndexOf()` 方法从尾到头检索，这意味着：假如第二个参数是 50，则从位置 50 开始向前检索，直到字符串的起点。

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.lastIndexOf("China", 50);//17
```



## search()

`search()` 方法搜索特定值的字符串，并返回匹配的位置

```js
var str = "The full name of China is the People's Republic of China.";
var pos = str.search("locate");
```



## indexOf()和search()的区别

两种方法，`indexOf()` 与 `search()`，是*相等的*。

这两种方法是不相等的。区别在于：

+ search() 方法无法设置第二个开始位置参数。
+ indexOf() 方法无法设置更强大的搜索值（正则表达式）。



# 提取部分字符串

## slice(*start*, *end*)

`slice()` 提取字符串的某个部分并在新字符串中返回被提取的部分。

该方法设置两个参数：起始索引（开始位置），终止索引（结束位置）。返回的字符串不包括结束位置

```js
var str = "Apple, Banana, Mango";
var res = str.slice(7,13);//Banana
```

如果某个参数为负，则从字符串的结尾开始计数。

```js
var str = "Apple, Banana, Mango";
var res = str.slice(-13,-7);//Banana
```

如果省略第二个参数，则该方法将裁剪字符串的剩余部分

```js
var res = str.slice(7);//Banana, Mango
```

或者从结尾计数

```js
var res = str.slice(-13);//Banana, Mango
```



## substring(start, end) 方法

`substring()` 类似于 `slice()`。

不同之处在于 `substring()` 无法接受负的索引。



## substr(start, length) 方法

`substr()` 类似于 `slice()`。

不同之处在于第二个参数规定被提取部分的**长度**。

```js
var str = "Apple, Banana, Mango";
var res = str.substr(7,6);//Banana
```

如果首个参数为负，则从字符串的结尾计算位置。

```js
var str = "Apple, Banana, Mango";
var res = str.substr(-5);
```



# 替换字符串内容

## replace()

方法用另一个值替换在字符串中指定的值

`replace()` 方法不会改变调用它的字符串。它返回的是新字符串。对大小写敏感

默认地，`replace()` **只替换首个匹配**

```js
str = "Please visit Microsoft and Microsoft!";
var n = str.replace("Microsoft", "W3School");
```

如需执行大小写不敏感的替换，请使用正则表达式 `/i`（大小写不敏感）：

请注意正则表达式不带引号

```js
str = "Please visit Microsoft!";
var n = str.replace(/MICROSOFT/i, "W3School");
```

如需替换所有匹配，请使用正则表达式的 `g` 标志（用于全局搜索）：

```js
str = "Please visit Microsoft and Microsoft!";
var n = str.replace(/Microsoft/g, "W3School");
```



# 转换为大写和小写

## toUpperCase()

转大写

```js
var text1 = "Hello World!";       // 字符串
var text2 = text1.toUpperCase();  // text2 是被转换为大写的 text1
```



## toLowerCase()

转小写

```js
var text1 = "Hello World!";       // 字符串
var text2 = text1.toLowerCase();  // text2 是被转换为小写的 text1
```



# 连接字符串

## concat()

可用于代替加运算符。下面两行是等效的：

```js
var text = "Hello" + " " + "World!";
var text = "Hello".concat(" ","World!");
```



# 删除字符串两端的空白符

`trim()` 方法删除字符串两端的空白符：

```js
var str = "       Hello World!        ";
alert(str.trim());
```



# 提取字符串

这是两个提取字符串字符的*安全*方法：

+ charAt(*position*)
+ charCodeAt(*position*)

## charAt(*position*)

`charAt()` 方法返回字符串中指定下标（位置）的字符串：

```js
var str = "HELLO WORLD";
str.charAt(0);            // 返回 H
```



## charCodeAt() 方法

`charCodeAt()` 方法返回字符串中指定索引的字符 unicode 编码：

```js
var str = "HELLO WORLD";
str.charCodeAt(0);         // 返回 72
```



## 属性访问

```js
var str = "HELLO WORLD";
str[0];                   // 返回 H
```

使用属性访问有点不太靠谱：

+ 不适用 Internet Explorer 7 或更早的版本
+ 它让字符串看起来像是数组（其实并不是）
+ 如果找不到字符，`[ ]` 返回 `undefined`，而 `charAt()` 返回空字符串。
+ 它是只读的。`str[0] = "A"` 不会产生错误（但也不会工作！）

```js
var str = "HELLO WORLD";
str[0] = "A";             // 不产生错误，但不会工作
str[0];                   // 返回 H
```



# 把字符串转换为数组

可以通过 `split()` 将字符串转换为数组：

```js
var txt = "a,b,c,d,e";   // 字符串
txt.split(",");          // 用逗号分隔
txt.split(" ");          // 用空格分隔
txt.split("|");          // 用竖线分隔
```

如果省略分隔符，被返回的数组将包含  index [0] 中的整个字符串。

如果分隔符是 ""，被返回的数组将是间隔单个字符的数组：

```js
var txt = "Hello";       // 字符串
txt.split("");           // 分隔为字符，一个一个
```





















































