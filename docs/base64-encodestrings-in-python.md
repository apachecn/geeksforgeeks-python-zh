# Python 中的 base64 . encoddestroing

> 原文:[https://www . geeksforgeeks . org/base64-encoddestrings-in-python/](https://www.geeksforgeeks.org/base64-encodestrings-in-python/)

借助`**base64.encodestring(s)**`方法，我们可以使用 base64 编码数据将字符串编码为二进制形式。

> **语法:** `base64.encodestring(string)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.encodestring(s)`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```
# import base64
from base64 import encodestring

s = b'GeeksForGeeks'
# Using base64.encodestring(s) method
gfg = encodestring(s)

print(gfg)
```

**输出:**

> b'R2Vla3NGb3JHZWVrcw==\n

**例 2 :**

```
# import base64
from base64 import encodestring

s = b'I love python'
# Using base64.encodestring(s) method
gfg = encodestring(s)

print(gfg)
```

**输出:**

> b ' ssbsb 3 zlihb 5 dghvbg== \ n