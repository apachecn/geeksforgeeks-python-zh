# Python 中的编解码器. encode()

> 原文:[https://www.geeksforgeeks.org/codecs-encode-in-python/](https://www.geeksforgeeks.org/codecs-encode-in-python/)

借助`**codecs.encode()**`方法，我们可以将字符串编码成二进制形式。

> **语法:** `codecs.encode(string)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`codecs.encode()`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```
# import codecs
import codecs

s = 'GeeksForGeeks'
# Using codecs.encode() method
gfg = codecs.encode(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```
# import codecs
import codecs

s = 'I love python.'
# Using codecs.encode() method
gfg = codecs.encode(s)

print(gfg)
```

**输出:**

> 我喜欢蟒蛇。'