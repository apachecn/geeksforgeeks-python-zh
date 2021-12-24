# Python 中的 html.unescape()

> 原文:[https://www.geeksforgeeks.org/html-unescape-in-python/](https://www.geeksforgeeks.org/html-unescape-in-python/)

借助`**html.unescape()**`方法，我们可以通过使用`html.escape()`方法将 ascii 字符替换为特殊字符，将 ascii 字符串转换为 html 脚本。

> **语法:** `html.unescape(String)`
> 
> **返回:**返回一个 html 脚本。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`html.unescape()`方法，我们能够使用该方法将 ascii 字符串转换为 html 脚本。

```
# import html
import html

s = '<html><head></head><body><h1>This is python</h1></body></html>'
temp = html.escape(s)
# Using html.unescape() method
gfg = html.unescape(temp)

print(gfg)
```

**输出:**

> # This is a python

**例 2 :**

```
# import html
import html

s = '<html><head></head><body><h1>GeeksForGeeks</h1></body></html>'
temp = html.escape(s)
# Using html.unescape() method
gfg = html.unescape(temp)

print(gfg)
```

**输出:**

> # Geeks