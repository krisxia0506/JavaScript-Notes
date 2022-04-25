

# 字符串长度

内建属性 `length` 可返回字符串的*长度*：

```js
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```



# 转义字符

| 代码 | 结果 |  描述  |
| :--: | :--: | :----: |
| \ '  |  '   | 单引号 |
| \ "  |  "   | 双引号 |
| \ \  |  \   | 反斜杠 |

# 在字符串中换行

```js
document.getElementById("demo").innerHTML = "Hello \
Kitty!";
```



# 字符串可以是对象

```js
var x = "Bill";
var y = new String("Bill");

// typeof x 将返回 string
// typeof y 将返回 object
```

`请不要把字符串创建为对象。它会拖慢执行速度`















