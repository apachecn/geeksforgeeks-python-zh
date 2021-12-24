# 如何用 Python 刮段落？

> 原文:[https://www . geesforgeks . org/how-to-scratch-段落-使用-python/](https://www.geeksforgeeks.org/how-to-scrape-paragraphs-using-python/)

**先决条件:** [**使用**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/) 在 Python 中实现网页抓取

在本文中，我们将看到如何使用 python 从给定的 HTML 文档或 URL 中提取所有段落。

**所需模块:**

*   **bs4:** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install bs4

```

*   **请求:** Requests 可以让你极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install requests

```

**进场:**

*   导入模块
*   创建一个 HTML 文档，并在代码中指定“

    ”标记

*   将 HTML 文档传递到美化程序()函数中
*   使用“P”标记从“美丽的组合”对象中提取段落
*   使用 get_text()从 HTML 文档中获取文本。

**代码:**

## 蟒蛇 3

```py
# import module
from bs4 import BeautifulSoup

# Html doc
html_doc = """
<html>
<head>
<title>Geeks</title>
</head>
<body>
<h2>paragraphs</h2>

<p>Welcome geeks.</p>

<p>Hello geeks.</p>

</body>
</html>
"""
soup = BeautifulSoup(html_doc, 'html.parser')

# traverse paragraphs from soup
for data in soup.find_all("p"):
    print(data.get_text())
```

**输出:**

```py
Welcome geeks.
Hello geeks.

```

**现在让我们从给定的网址中提取段落。**

**代码:**

## 蟒蛇 3

```py
# import module
import requests
import pandas as pd
from bs4 import BeautifulSoup

# link for extract html data
def getdata(url):
    r = requests.get(url)
    return r.text

htmldata = getdata("https://www.geeksforgeeks.org/")
soup = BeautifulSoup(htmldata, 'html.parser')
data = ''
for data in soup.find_all("p"):
    print(data.get_text())
```

**输出:**

![](img/2a0b1ed5878bfd078b6baa6ff8abbb02.png)