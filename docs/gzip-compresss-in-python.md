# Python 中的 gzip 压缩

> 原文:[https://www.geeksforgeeks.org/gzip-compresss-in-python/](https://www.geeksforgeeks.org/gzip-compresss-in-python/)

借助`**gzip.compress(s)**`方法，我们可以通过`gzip.compress(s)`方法得到压缩的字符串字节。

> **语法:** `gzip.compress(string)`
> **返回:**返回压缩字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`gzip.compress(s)`方法，我们能够使用该方法将字符串压缩为字节格式。

```
# import gzip and compress
import gzip

s = b'This is GFG author, and final year student.'
print(len(s))

# using gzip.compress(s) method
t = gzip.compress(s)
print(len(t))
```

**输出:**

> 43
> 61

**例 2 :**

```
# import gzip and compress
import gzip

s = b'GeeksForGeeks@12345678'
print(len(s))

# using gzip.compress(s) method
t = gzip.compress(s)
print(len(t))
```

**输出:**

> 22
> 39