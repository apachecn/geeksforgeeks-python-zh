# Python 中的 base64.a85encode()

> 原文:[https://www.geeksforgeeks.org/base64-a85encode-in-python/](https://www.geeksforgeeks.org/base64-a85encode-in-python/)

借助`**base64.a85encode()**`方法，我们可以用 Ascii85 字母表将字符串编码成二进制形式。

> **语法:** `base64.a85encode(string)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.a85encode()`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```py
# import base64
from base64 import a85encode

s = b'GeeksForGeeks'
# Using base64.a85encode() method
gfg = a85encode(s)

print(gfg)
```

**输出:**

> S7-1200 可编程控制器

**例 2 :**

```py
# import base64
from base64 import a85encode

s = b'I love python'
# Using base64.a85encode() method
gfg = a85encode(s)

print(gfg)
```

**输出:**

> b'8K_hfG%De8H$！_