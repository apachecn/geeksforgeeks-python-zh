# lzma。Python 中的 LZMACompressor()

> 原文:[https://www . geesforgeks . org/lzma-lzmaccompressor-in-python/](https://www.geeksforgeeks.org/lzma-lzmacompressor-in-python/)

借助`**lzma.LZMACompressor()**`方法，我们可以让 compressor 使用`lzma.LZMACompressor()`方法压缩字符串的字节。

> **语法:** `lzma.LZMACompressor()`
> **返回:**返回压缩字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`lzma.LZMACompressor()`方法，我们能够使用该方法将字符串压缩为字节格式。

```py
# import lzma and compress
import lzma

s = b'This is GFG author, and final year student.'
print(len(s))

# using lzma.LZMACompressor() method
compressor = lzma.LZMACompressor()
t = compressor.compress(s)
print(len(t))
```

**输出:**

> 43
> 24

**例 2 :**

```py
# import lzma and compress
import lzma

s = b'GeeksForGeeks@12345678'
print(len(s))

# using lzma.LZMACompressor() method
compressor = lzma.LZMACompressor()
t = compressor.compress(s)
print(len(t))
```

**输出:**

> 22
> 24