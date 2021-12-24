# Python 中的 hashlib.sha3_512()

> 原文:[https://www.geeksforgeeks.org/hashlib-sha3_512-in-python/](https://www.geeksforgeeks.org/hashlib-sha3_512-in-python/)

借助`**hashlib.sha3_512()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.sha3_512()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.sha3_512()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.sha3_512()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```py
# import hashlib
import hashlib

# Using hashlib.sha3_512() method
gfg = hashlib.sha3_512()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b ' n \ x1 a \ xf 5 \ x8 e \ xbc \ x95 \ xbb \ xe 1 \ x9 fr \ x13 \ xdfo \ x06 \ xbce \ x8a \ x81q \ x18r \ xa 7 \ x92 j \ x17u \ x03 \ xee \ xdf \ x89 \ xf4 \ xdd $ \ xaf \ xca \ xb7 \ x9f \ XB 5 \ xe 2 \ xd 9 \ xab \ xa 1w \ x03 o \ xdev % \ x

**例 2 :**

```py
# import hashlib
import hashlib

# Using hashlib.sha3_512() method
gfg = hashlib.sha3_512()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b ' q \ xf8q \ x00 \ xb6 r \ xcf \ xf3 \ xf7 \ xfeb \ xf6 \ x81 s \ x92 l \ xfd \ x93 l \ x0 ei ` \ xb0 v \ x8g \ \ \ \ x8cc-\ x12 \ ri \ x 05 \ xe 6y < \ xee \ x8f 4 \ x9 bn \ xa 1-qi \ xfce \ xa 8 = & \ xdgj \ xe 7 \ xfa \ x82 \ xdf \ x9