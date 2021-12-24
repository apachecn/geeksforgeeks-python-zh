# Python 中的 hashlib.blake2b()

> 原文:[https://www.geeksforgeeks.org/hashlib-blake2b-in-python/](https://www.geeksforgeeks.org/hashlib-blake2b-in-python/)

借助`**hashlib.blake2b()**`方法，我们可以将字节格式的正常字符串转换为加密形式。借助`hashlib.blake2b()`方法，可以将密码和重要文件转换成哈希来保护它们。

> **语法:** `hashlib.blake2b()`
> 
> **返回:**返回字符串的哈希代码。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`hashlib.blake2b()`方法，我们能够对字节字符串或密码进行加密，以使用该方法来保护它们。

```
# import hashlib
import hashlib

# Using hashlib.blake2b() method
gfg = hashlib.blake2b()
gfg.update(b'GeeksForGeeks')

print(gfg.digest())
```

**输出:**

> b ' g \ x04 \ x97 \ xc 5 \ xa 2 \ x88:\ x88 { j \ xda \ x19 \ xa 3 \ xd 9[\ x9f \ xaa \ x9d \ TV \ xc 7 ~ \ x82 \ xee \ x1 d \ xae \ xad \ xa 8 \ xf7 \ x92 bi & ~ x \ xf 7 \ xfc \ x82 \ xb5 \ x8gv \ x8a \ xe 1 \ x89 \ x19 \ xe 4 \ 0x 0 c \ n

**例 2 :**

```
# import hashlib
import hashlib

# Using hashlib.blake2b() method
gfg = hashlib.blake2b()
gfg.update(b'xyz@1234_GFG')

print(gfg.digest())
```

**输出:**

> b ' \ xd 4 \ x8 e \ xd 4 \ \ \ \ x8a & \ xe 1 \ xa 7d！\ x90 \ xce \ x9d \ x03v \ x9a \ x05 \ xf7 \ n \ xf0h \ xd 37 \ x81 o \ r { \ xed 5 ~。\ x8f \ xde \ x8a \ x05 \ xad \ xa 0 \ xc2 & \ xc2 \ x404 \ x8eu \ x96 \ xb6 \ xde 1-\ xcc \ xcarq \ xc 5+\ xaa \ xcc \ x88 \ x14p \ xed \ xf9 t '