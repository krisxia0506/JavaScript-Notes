

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

`lastIndexOf()` 方法返回指定文本在字符串中*最后*一次出现的索引

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











