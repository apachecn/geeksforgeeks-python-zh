# Python 中的 hashlib.sha3_256()

> 原文:[https://www.geeksforgeeks.org/hashlib-sha3_256-in-python/](https://www.geeksforgeeks.org/hashlib-sha3_256-in-python/)

借助`**hashlib.sha3_256()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.sha3_256()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.sha3_256()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.sha3_256()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```py
# import hashlib
import hashlib

# Using hashlib.sha3_256() method
gfg = hashlib.sha3_256()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b ' \ x14 \ xf7h \ xf 7 \ xb2w < \ xe 5 \ x8 FQ \ xe 9s I \ xd 0 \ x89 \ x1 c $ \ xfe \ xac \ xdfv \ xe 8c | \ xb9 \ xdf \ x96 \ xe 3 \ x93 z '

**例 2 :**

```py
# import hashlib
import hashlib

# Using hashlib.sha3_256() method
gfg = hashlib.sha3_256()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b“b \ xea \ x7f”\ x8a \ xd3 \ x93 \ XB 1k \ t5 \ xa 5j | u \ xea \ xad \ x03 \ xc8 \ x9 egw \ xdew \ x03 \ xa 6 \ xb8 \ x85 } \ xd 5 ~ \ xb6”