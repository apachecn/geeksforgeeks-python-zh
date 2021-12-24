# Python 中的 hashlib.shake_256()

> 原文:[https://www . geesforgeks . org/hashlib-shake _ 256-in-python-2/](https://www.geeksforgeeks.org/hashlib-shake_256-in-python-2/)

借助`**hashlib.shake_256()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.shake_256()`方法，可以将密码和重要文件转换成哈希来保护它们。
注意，我们可以调整加密数据的长度。

> **语法:** `hashlib.shake_256()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.shake_256()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```py
# import hashlib
import hashlib

# Using hashlib.shake_256() method
gfg = hashlib.shake_256()
gfg.update(b'GeeksForGeeks')

print(gfg.digest(10))
```

**输出:**

> b ' e \ xd 6 \ xdf \ x8 d \ x88 \ x89 \ x8d \ xe 6 \ x9b < '

**例 2 :**

```py
# import hashlib
import hashlib

# Using hashlib.shake_256() method
gfg = hashlib.shake_256()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest(15))
```

**输出:**

> S7-1200 可编程控制器。'我不知道