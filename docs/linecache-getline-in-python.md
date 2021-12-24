# python 中的 linecache.getline()

> 原文:[https://www.geeksforgeeks.org/linecache-getline-in-python/](https://www.geeksforgeeks.org/linecache-getline-in-python/)

借助`**linecache.getline()**`方法，我们可以通过提供行号来获取特定的行，该方法的用例之一是使用`linecache.getline()`方法在一个大文件内找到给定行号的语法错误。

> **语法:** `linecache.getline(filename, lineno)`
> **返回:**返回给定行号的内容。

输入文件:
![](img/08f670457092c8b7a2a0e3e1e4a1c9e1.png)

**示例#1 :**
在这个示例中，我们可以看到，通过使用`linecache.getline()`方法，我们能够使用该方法从一个大文件中获取给定行的内容。

```
# import linecache
import linecache as lc

# Using linecache.getline() method
gfg = lc.getline('File.txt', 1)

print(gfg)
```

**输出:**
![](img/1c3e6e9747740feffe5f3b89fa95c027.png)

**例 2 :**

```
# import linecache
import linecache as lc

# Using linecache.getline() method
gfg = lc.getline('File.txt', 2)

print(gfg)
```

**输出:**
![](img/8b5d4d3520f86d1bb0075c8a12695d01.png)