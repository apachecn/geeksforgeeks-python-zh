# Python 中的 base64 . standard _ b64 decode

> 原文:[https://www . geesforgeks . org/base64-standard _ b64 解码-in-python/](https://www.geeksforgeeks.org/base64-standard_b64decodes-in-python/)

借助`**base64.standard_b64decode()**`方法，我们可以将使用 base64 字母的二进制字符串解码成正常形式的字符串。

> **语法:** `base64.standard_b64decode(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.standard_b64decode()`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```py
# import base64
from base64 import standard_b64decode
from base64 import standard_b64encode

s = b'GeeksForGeeks'
s = standard_b64encode(s)
# Using base64.standard_b64decode() method
gfg = standard_b64decode(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```py
# import base64
from base64 import standard_b64decode
from base64 import standard_b64encode

s = b'Hello World'
s = standard_b64encode(s)
# Using base64.standard_b64decode() method
gfg = standard_b64decode(s)

print(gfg)
```

**输出:**

> 《你好，世界》