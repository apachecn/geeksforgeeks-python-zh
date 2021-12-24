# Python 中的 hashlib.sha3_384()

> 原文:[https://www.geeksforgeeks.org/hashlib-sha3_384-in-python/](https://www.geeksforgeeks.org/hashlib-sha3_384-in-python/)

借助`**hashlib.sha3_384()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.sha3_384()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.sha3_384()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.sha3_384()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```py
# import hashlib
import hashlib

# Using hashlib.sha3_384() method
gfg = hashlib.sha3_384()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b ' \ x90 \ xb3 \ xee \ xa 6i \ x8 e \ xc 1 \ xc63 \ xc 6 \ xe 1 _ # \ xbe \ xe 2f \ xb2 ~ \ xe 2[\ xca \ xb1 I \ xc 9i \ xef \ xa 5 \ xb32 \ xf 9 \ xcc \ xd 8 \ x9c \ x8 c \ x8c \ x89 \ xd 6 \ xc 9 \ xb1 \ x9b！\ x02 \ xb4 \ xan \ xb9 \ x90 XO”

**例 2 :**

```py
# import hashlib
import hashlib

# Using hashlib.sha3_384() method
gfg = hashlib.sha3_384()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b ' \ xfc \ xc 4/q \ xb0 x \ x0 CP \ xa 7 \ xfa \ xd 34 \ x18 { \ xaa \ xb6 \ xbb \ x88 \ xb5 \ xe 8 \ xa9 \ xc 4 \ xd 2 \ xc 6 \ x9c \ xcd-# \ xc6 \ xedt ` \ xbc \ t \ x0 b \ X11 \ xe 4 \ x8 bx qax '。C\nv\x1ev