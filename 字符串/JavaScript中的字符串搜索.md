# 字符串搜索

+ String.indexOf()
+ String.lastIndexOf()
+ String.startsWith()
+ String.endsWith()



## String.match(regexp)

match() 方法根据正则表达式在字符串中搜索匹配项，并将匹配项作为 Array 对象返回。

```js
let text = "The rain in SPAIN stays mainly in the plain";
text.match(/ain/gi)   // 返回数组 [ain,AIN,ain,ain]
```

| *regexp* | 必需。需要搜索的值，为正则表达式。                           |
| -------- | ------------------------------------------------------------ |
| 返回：   | 数组，包含匹配项，每个匹配项对应一个项目，若未找到匹配项，则为 null。 |

## String.includes(searchvalue, start)

如果字符串包含指定值，`includes()` 方法返回 true。

```js
let text = "Hello world, welcome to the universe.";
text.includes("world")    // 返回 true
```

| *searchvalue* | 必需。需要搜索的字符串。                            |
| ------------- | --------------------------------------------------- |
| *start*       | 可选。默认为 0. 开始搜索的位置。                    |
| 返回：        | 如果字符串包含该值则返回 `true`，否则返回 `false`。 |



## String.startsWith(searchvalue, start)

如果字符串以指定值开头，则 `startsWith()` 方法返回 `true`，否则返回 `false`：

| 参数          | 描述                             |
| ------------- | -------------------------------- |
| *searchvalue* | 必需。需要搜索的值。             |
| *start*       | 可选。默认为 0。开始搜索的位置。 |

```js
let text = "Hello world, welcome to the universe.";
text.startsWith("Hello")   // 返回 true
text.startsWith("H")   // 返回 true
text.startsWith("ello")   // 返回 false
text.startsWith("H1")   // 返回 false
text.startsWith("world", 6)    // 返回 true
```



## String.endsWith(searchvalue, length)

如果字符串以指定值结尾，则 `endsWith()` 方法返回 `true`，否则返回 `false`：

| 参数          | 描述                 |
| ------------- | -------------------- |
| *searchvalue* | 必需。需要搜索的值。 |
| *length*      | 可选。要搜索的长度。 |

```js
var text = "Bill Gates";
text.endsWith("Gates")    // 返回 true
let text = "Hello world, welcome to the universe.";
text.endsWith("world", 11)    // 返回 true
```





















