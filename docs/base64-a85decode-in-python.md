# Python 中的 base64.a85decode()

> 原文:[https://www.geeksforgeeks.org/base64-a85decode-in-python/](https://www.geeksforgeeks.org/base64-a85decode-in-python/)

借助`**base64.a85decode()**`方法，我们可以将使用 Ascii85 字母的二进制字符串解码成范式。

> **语法:** `base64.a85decode(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.a85decode()`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```py
# import base64
from base64 import a85decode
from base64 import a85encode

s = b'GeeksForGeeks'
s = a85encode(s)
# Using base64.a85decode() method
gfg = a85decode(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```py
# import base64
from base64 import a85decode
from base64 import a85encode

s = b'Hello World'
s = a85encode(s)
# Using base64.a85decode() method
gfg = a85decode(s)

print(gfg)
```

**输出:**

> 《你好，世界》