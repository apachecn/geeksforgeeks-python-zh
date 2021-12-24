# Python 中的 hashlib.blake2s()

> 原文:[https://www.geeksforgeeks.org/hashlib-blake2s-in-python/](https://www.geeksforgeeks.org/hashlib-blake2s-in-python/)

借助`**hashlib.blake2s()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.blake2s()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.blake2s()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.blake2s()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```
# import hashlib
import hashlib

# Using hashlib.blake2s() method
gfg = hashlib.blake2s()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b'\xb6\x88\x94，\ x0 ff * \ x8163 \ x9 和\ x1 f \ \ 0 \ xaa \ x8c { \ x17 \ xca \ xfc \ x14 \ xc3 \ xe 5n \ x8e \ xbbv \ xf8 \ xa 1 \ xdb '

**例 2 :**

```
# import hashlib
import hashlib

# Using hashlib.blake2s() method
gfg = hashlib.blake2s()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b ' \ xad \ x1bp 等级\ xbf \ xdc \ xbb \ xea \ xb0 { j \ xdb \ x83b！\ x14 \ xb3 \ xbft \ x3 \ xfa \ xac \ x93 zb \ xb6 \ xd 3 \ t \ x7f \ x14 \ t”