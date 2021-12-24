# Python 中的 hashlib.sha3_224()

> 原文:[https://www.geeksforgeeks.org/hashlib-sha3_224-in-python/](https://www.geeksforgeeks.org/hashlib-sha3_224-in-python/)

借助`**hashlib.sha3_224()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.sha3_224()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.sha3_224()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.sha3_224()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```
# import hashlib
import hashlib

# Using hashlib.sha3_224() method
gfg = hashlib.sha3_224()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b " \ xa 1 \ x155 \ exec \ x93 \ xb1 \ xdcf)\ x1 c \ xea \ xf0 \ xf5 \ xe 6 \ xdf \ xc 5i \ x94 ' r { 2 \ x44 \ xe 8 \ xc9 \ xcey \ xa 8 "

**例 2 :**

```
# import hashlib
import hashlib

# Using hashlib.sha3_224() method
gfg = hashlib.sha3_224()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b):\ xddo \ xd 7 \ xb9 y \ xc 9% \ xd 1 \ x9f \ x6u " g \ x89 * { \ xbd \ x18 \ x07 \ xcdic \ xbc < uq \ xed "