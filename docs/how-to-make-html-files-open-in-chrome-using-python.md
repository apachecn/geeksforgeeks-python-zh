# 如何用 Python 在 Chrome 中打开 HTML 文件？

> 原文:[https://www . geesforgeks . org/how-to-make-html-files-open-in-chrome-use-python/](https://www.geeksforgeeks.org/how-to-make-html-files-open-in-chrome-using-python/)

**先决条件** : [网络浏览器](https://www.geeksforgeeks.org/python-launch-a-web-browser-using-webbrowser-module/)

HTML 文件包含超文本标记语言(HTML)，用于设计和格式化网页的结构。它以文本格式存储，并包含定义网页布局和内容的标签。HTML 文件在网上被广泛使用，并在网络浏览器中显示。

为了预览超文本标记语言文件，我们使用浏览器，如谷歌浏览器、Mozilla 火狐、苹果 Safari 等。创建和预览 HTML 文件的任务可以在 python 脚本的帮助下自动完成。

以下是我们在 chrome 上打开 HTML 文件的几种方法:

### 方法 1:使用操作系统和网络浏览器

python 中的 webbrowser 模块提供了一个高级界面，允许向用户显示基于 Web 的文档，而 os 模块提供了一种使用操作系统相关功能(如读取或写入文件、操作文件路径等)的可移植方式。).让我们看看这两者的结合如何帮助我们在 Chrome 浏览器中打开一个 HTML 页面:

**使用的函数:** open_new_tab()函数用于在默认浏览器的新选项卡中打开 html 文件。

**语法:**

> open_new_tab(文件名)

**方法:**

*   Import module
*   Open and create file.
*   Add html code
*   Write code to file
*   close a document
*   In the browser window

打开文件

**例:**

## 蟒 3

```py
# creating nd viewing the html files in python

import webbrowser
import os

# to open/create a new html file in the write mode
f = open('GFG.html', 'w')

# the html code which will go in the file GFG.html
html_template = """
<html>
<head></head>
<body>
<p>Geeks For Geeks</p>

</body>
</html>
"""
# writing the code into the file
f.write(html_template)

# close the file
f.close()

# 1st method how to open html files in chrome using
filename = 'file:///'+os.getcwd()+'/' + 'GFG.html'
webbrowser.open_new_tab(filename)
```