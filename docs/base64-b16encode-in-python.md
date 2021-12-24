# Python 中的 base64.b16encode()

> 原文:[https://www.geeksforgeeks.org/base64-b16encode-in-python/](https://www.geeksforgeeks.org/base64-b16encode-in-python/)

借助`**base64.b16encode()**`方法，我们可以用 base16 字母表将字符串编码成二进制形式。

> **语法:** `base64.b16encode(string)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.b16encode()`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```
# import base64
from base64 import b16encode

s = b'GeeksForGeeks'
# Using base64.b16encode() method
gfg = b16encode(s)

print(gfg)
```

**输出:**

> ' b'4765656B73466F724765656B73 '

**例 2 :**

```
# import base64
from base64 import b16encode

s = b'I love python'
# Using base64.b16encode() method
gfg = b16encode(s)

print(gfg)
```

**输出:**

> ' b'49206C6F766520707974686F6E '