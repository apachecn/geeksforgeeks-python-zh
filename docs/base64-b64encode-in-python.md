# Python 中的 base64.b64encode()

> 原文:[https://www.geeksforgeeks.org/base64-b64encode-in-python/](https://www.geeksforgeeks.org/base64-b64encode-in-python/)

借助`**base64.b64encode()**`方法，我们可以将字符串编码成二进制形式。

> **语法:** `base64.b64encode(string)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.b64encode()`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```py
# import base64
from base64 import b64encode

s = b'GeeksForGeeks'
# Using base64.b64encode() method
gfg = b64encode(s)

print(gfg)
```

**输出:**

> B- R2 vla 3 NGB 3 jhzwvr CW = = "

**例 2 :**

```py
# import base64
from base64 import b64encode

s = b'I love python'
# Using base64.b64encode() method
gfg = b64encode(s)

print(gfg)
```

**输出:**

> b ' ssbsb 3 zlib 5 dghvbg = = '