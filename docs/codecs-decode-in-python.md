# Python 中的编解码器. decode()

> 原文:[https://www.geeksforgeeks.org/codecs-decode-in-python/](https://www.geeksforgeeks.org/codecs-decode-in-python/)

借助`**codecs.decode()**`方法，我们可以使用`codecs.decode()`方法将二进制字符串解码成范式。

> **语法:** `codecs.decode(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`codecs.decode()`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```
# import codecs
import codecs

s = b'GeeksForGeeks'
# Using codecs.decode() method
gfg = codecs.decode(s)

print(gfg)
```

**输出:**

> 极客们

**例 2 :**

```
# import codecs
import codecs

s = b'I love python.'
# Using codecs.decode() method
gfg = codecs.decode(s)

print(gfg)
```

**输出:**

> 我喜欢蟒蛇。