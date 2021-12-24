# Python 中的 gzip .解压

> 原文:[https://www.geeksforgeeks.org/gzip-decompresss-in-python/](https://www.geeksforgeeks.org/gzip-decompresss-in-python/)

借助`**gzip.decompress(s)**`方法，我们可以使用`gzip.decompress(s)`方法将字符串的压缩字节解压缩为原始字符串。

> **语法:** `gzip.decompress(string)`
> **返回:**返回解压后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`gzip.decompress(s)`方法，我们能够使用该方法将压缩后的字符串解压缩为字符串的字节格式。

```py
# import gzip and decompress
import gzip
s = b'This is GFG author, and final year student.'
s = gzip.compress(s)

# using gzip.decompress(s) method
t = gzip.decompress(s)
print(t)
```

**输出:**

> 这是 GFG 作家，也是最后一年的学生。'

**例 2 :**

```py
# import gzip and compress
import gzip
s = b'GeeksForGeeks@12345678'
s = gzip.compress(s)

# using gzip.decompress(s) method
t = gzip.decompress(s)
print(t)
```

**输出:**

> b'GeeksForGeeks@12345678 '