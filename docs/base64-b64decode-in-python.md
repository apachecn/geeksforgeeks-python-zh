# Python 中的 base64.b64decode()

> 原文:[https://www.geeksforgeeks.org/base64-b64decode-in-python/](https://www.geeksforgeeks.org/base64-b64decode-in-python/)

借助`**base64.b64decode()**`方法，我们可以将二进制字符串解码成范式。

> **语法:** `base64.b64decode(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.b64decode()`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```
# import base64
from base64 import b64decode
from base64 import b64encode

s = b'GeeksForGeeks'
s = b64encode(s)
# Using base64.b64decode() method
gfg = b64decode(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```
# import base64
from base64 import b64decode
from base64 import b64encode

s = b'Hello World'
s = b64encode(s)
# Using base64.b64decode() method
gfg = b64decode(s)

print(gfg)
```

**输出:**

> 《你好，世界》