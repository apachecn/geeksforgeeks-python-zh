# Python 中的 base64 . decodebytes

> 原文:[https://www . geeksforgeeks . org/base64-python 中的 decodebytess/](https://www.geeksforgeeks.org/base64-decodebytess-in-python/)

借助`**base64.decodebytes(s)**`方法，我们可以借助 base64 数据将二进制字符串解码成范式。

> **语法:** `base64.decodebytes(b_string)`
> 
> **返回:**返回解码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.decodebytes(s)`方法，我们能够通过使用该方法获得可以是二进制形式的解码字符串。

```
# import base64
from base64 import encodebytes
from base64 import decodebytes

s = b'GeeksForGeeks'
s = encodebytes(s)
# Using base64.decodebytes(s) method
gfg = decodebytes(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```
# import base64
from base64 import encodebytes
from base64 import decodebytes

s = b'Hello World'
s = encodebytes(s)
# Using base64.decodebytes(s) method
gfg = decodebytes(s)

print(gfg)
```

**输出:**

> 《你好，世界》