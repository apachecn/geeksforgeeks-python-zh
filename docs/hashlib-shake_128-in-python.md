# Python 中的 hashlib.shake_128()

> 原文:[https://www.geeksforgeeks.org/hashlib-shake_128-in-python/](https://www.geeksforgeeks.org/hashlib-shake_128-in-python/)

借助`**hashlib.shake_128()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.shake_128()`方法，可以将密码和重要文件转换成哈希来保护它们。
注意，我们可以调整加密数据的长度。

> **语法:** `hashlib.shake_128()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.shake_128()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```
# import hashlib
import hashlib

# Using hashlib.shake_128() method
gfg = hashlib.shake_128()
gfg.update(b'GeeksForGeeks')

print(gfg.digest(10))
```

**输出:**

> 页:1

**例 2 :**

```
# import hashlib
import hashlib

# Using hashlib.shake_128() method
gfg = hashlib.shake_128()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest(15))
```

**输出:**

> b ' \ X80 \ xa 2g \ x15 > \ xcf \ xcf \ x96 \ xd 60p \ x1 c \ xfc \ x0 \ xfe '