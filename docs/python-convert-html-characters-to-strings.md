# Python–将 HTML 字符转换为字符串

> 原文:[https://www . geesforgeks . org/python-convert-html-characters-to-strings/](https://www.geeksforgeeks.org/python-convert-html-characters-to-strings/)

**先决条件:** [html 模块](https://www.geeksforgeeks.org/html-escape-in-python/)

给定一个包含 HTML 字符的字符串，任务是将 HTML 字符转换为字符串。这可以借助 html.escape()方法来实现(对于 Python 3.4 **+** ，我们可以通过使用 html.escape() 方法将 ASCII 字符串替换为特殊字符，从而将 ASCII 字符串转换为 html 脚本。

通过这种方法，我们可以将 HTML 实体解码成文本。

**语法:**

```
html.unescape(String)
```

我们也可以使用处理实体转换的【美人汤】  。在美丽的汤 4 中，实体被自动解码。

**示例 1:** Python 3.6+

## 蟒蛇 3

```
# import html
import html

# Create Text
text = 'Γeeks for Γeeks'

# It Converts given text To String
print(html.unescape(text)) 

# It Converts given text to HTML Entities 
print(html.escape(text)) 
```

**输出:**

> γeek 的γeek
> 
> Γ eeks 代表Γ eeks

**例 2:** Python 2.6-3.3

我们可以使用标准库中的 HTMLParser.unescape():

*   对于 Python 2.6-2.7，它在 HtmlParser 中。
*   对于 Python 3，它在 html.parser 中

## 蟒蛇 3

```
#import html
import html

try:
    # Python 2.6-2.7
    from HTMLParser import HTMLParser
except ImportError:
    # Python 3
    from html.parser import HTMLParser

# for python 3
h = html.parser
print(h.unescape('Γeeks for Γeeks'))  
```

**输出:**

> γeek 的γeek