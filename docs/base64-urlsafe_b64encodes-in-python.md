# Python 中的 base64 . urlsife _ b64 encode

> 原文:[https://www . geesforgeks . org/base64-URL safe _ b64 encodes-in-python/](https://www.geeksforgeeks.org/base64-urlsafe_b64encodes-in-python/)

借助`**base64.urlsafe_b64encode(s)**`方法，我们可以使用 url 和文件系统安全字母将字符串编码成二进制形式。

> **语法:** `base64.urlsafe_b64encode(s)`
> 
> **返回:**返回编码后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`base64.urlsafe_b64encode(s)`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```
# import base64
from base64 import urlsafe_b64encode

s = b'GeeksForGeeks'
# Using base64.urlsafe_b64encode(s) method
gfg = urlsafe_b64encode(s)

print(gfg)
```

**输出:**

> B- R2 vla 3 NGB 3 jhzwvr CW = = "

**例 2 :**

```
# import base64
from base64 import urlsafe_b64encode

s = b'www.python.org / documentation'
# Using base64.urlsafe_b64encode(s) method
gfg = urlsafe_b64encode(s)

print(gfg)
```

**输出:**

> b ' d3d lnb 5 dghvbi 5 vcmcv ZG 9 jdw 1 lbnrhdglvbg = = '