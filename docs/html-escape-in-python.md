# Python 中的 html.escape()

> 原文:[https://www.geeksforgeeks.org/html-escape-in-python/](https://www.geeksforgeeks.org/html-escape-in-python/)

借助`**html.escape()**`方法，我们可以通过使用`html.escape()`方法将字符串替换为 ascii 字符的特殊字符，从而将 html 脚本转换为字符串。

> **语法:** `html.escape(String)`
> 
> **返回:**从 html 返回一串 ascii 字符脚本。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`html.escape()`方法，我们能够使用该方法将 html 脚本转换为 ascii 字符串。

```
# import html
import html

s = '<html><head></head><body><h1>This is python</h1></body></html>'
# Using html.escape() method
gfg = html.escape(s)

print(gfg)
```

**输出:**

> # 这是巨蟒

**例 2 :**

```
# import html
import html

s = '<html><head></head><body><h1>GeeksForGeeks</h1></body></html>'
# Using html.escape() method
gfg = html.escape(s)

print(gfg)
```

**输出:**

> # 极客们