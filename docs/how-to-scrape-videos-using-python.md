# 如何用 Python 刮视频？

> 原文:[https://www . geesforgeks . org/how-to-scratch-videos-use-python/](https://www.geeksforgeeks.org/how-to-scrape-videos-using-python/)

**先决条件:**

*   [请求](https://www.geeksforgeeks.org/python-requests-tutorial/)
*   [美丽的脉冲星](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)

在本文中，我们将讨论使用 python 对视频进行网页抓取。对于网页抓取，我们将使用 Python 中的**请求和** **美化程序**模块。**请求**库是 Python 的一个组成部分，用于向指定的网址发出 HTTP 请求。无论是 REST APIs 还是 Web Scraping，都必须学习请求才能进一步使用这些技术。当一个人向 URI 提出请求时，它会返回一个响应。Python 请求提供了管理请求和响应的内置功能。

```py
pip install requests
```

**美汤**是一个 Python 库，专为像刮屏这样的快速周转项目而设计。

```py
pip install bs4
```

**我们来了解一下分步实施:**

*   导入所需模块

## 蟒蛇 3

```py
# Import Required Module
import requests
from bs4 import BeautifulSoup
```

*   解析超文本标记语言内容

## 蟒蛇 3

```py
# Web URL
Web_url = "Enter WEB URL"

# Get URL Content
r = requests.get(Web_url)

# Parse HTML Code
soup = BeautifulSoup(r.content, 'html5lib')
```

*   数一数网页上有多少视频。在 HTML 中为了显示视频，我们使用**视频**标签。

## 蟒蛇 3

```py
# List of all video tag
video_tags = soup.findAll('video')
print("Total ",len(video_tags),"videos found")
```