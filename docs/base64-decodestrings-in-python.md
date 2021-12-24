# Python 中的 base64 .去破坏

> 原文:[https://www . geesforgeks . org/base64-python 中的去破坏/](https://www.geeksforgeeks.org/base64-decodestrings-in-python/)

借助`**base64.decodestring(s)**`方法，我们可以借助 base64 数据将二进制字符串解码成范式。

> **语法:** `base64.decodestring(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.decodestring(s)`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```
# import base64
from base64 import encodestring
from base64 import decodestring

s = b'GeeksForGeeks'
s = encodestring(s)
# Using base64.decodestring(s) method
gfg = decodestring(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```
# import base64
from base64 import encodestring
from base64 import decodestring

s = b'Hello World'
s = encodestring(s)
# Using base64.decodestring(s) method
gfg = decodestring(s)

print(gfg)
```

**输出:**

> 《你好，世界》