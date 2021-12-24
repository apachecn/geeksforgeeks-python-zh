# bz2 .用 Python 压缩

> 原文:[https://www.geeksforgeeks.org/bz2-compresss-in-python/](https://www.geeksforgeeks.org/bz2-compresss-in-python/)

借助`**bz2.compress(s)**`方法，我们可以通过`bz2.compress(s)`方法得到压缩的字符串字节。

> **语法:** `bz2.compress(string)`
> **返回:**返回压缩字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`bz2.compress(s)`方法，我们能够使用该方法将字符串压缩为字节格式。

```py
# import bz2 and compress
import bz2

s = b'This is GFG author, and final year student.'
print(len(s))

# using bz2.compress(s) method
t = bz2.compress(s)
print(len(t))
```

**输出:**

> 43
> 77

**例 2 :**

```py
# import bz2 and compress
import bz2

s = b'GeeksForGeeks@12345678'
print(len(s))

# using bz2.compress(s) method
t = bz2.compress(s)
print(len(t))
```

**输出:**

> 22
> 60