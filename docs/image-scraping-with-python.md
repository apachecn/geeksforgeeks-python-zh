# 用 Python 进行图像刮擦

> 原文:[https://www.geeksforgeeks.org/image-scraping-with-python/](https://www.geeksforgeeks.org/image-scraping-with-python/)

[刮痧](https://www.geeksforgeeks.org/introduction-to-web-scraping/) 是每个人从任何网站获取数据都非常必不可少的技能。在本文中，我们将看到如何使用 python 从网站上刮取图像。对于刮擦图像，我们将尝试不同的方法。

**方法 1:** 使用美丽的组和请求

*   [**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)【T4:美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install bs4

```

*   [**请求**](https://www.geeksforgeeks.org/python-requests-tutorial/) **:** 请求让你发送 HTTP/1.1 请求极其轻松。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install requests

```

**进场:**

*   导入模块
*   创建请求实例并传入网址
*   将请求传递到一个美丽的输出()函数中
*   使用“img”标签查找所有标签(“src”)

**实施:**

## 蟒蛇 3

```py
import requests 
from bs4 import BeautifulSoup 

def getdata(url): 
    r = requests.get(url) 
    return r.text 

htmldata = getdata("https://www.geeksforgeeks.org/") 
soup = BeautifulSoup(htmldata, 'html.parser') 
for item in soup.find_all('img'):
    print(item['src'])
```

**输出:**

> https://media . geesforgeks . org/WP-content/cdn-uploads/20201018234700/GFG-RT-DSA-creative . png
> https://media . geesforgeks . org/WP-content/cdn-uploads/logo-new-2 . SVG

**方法二:**使用 urllib 和 BeautifulSoup

[**URL lib**](https://www.geeksforgeeks.org/python-urllib-module/)**:**It是一个 Python 模块，允许您使用其 URL 访问网站并与之交互。要安装此软件，请在终端中键入以下命令。

```py
pip install urllib

```

**进场:**

*   导入模块
*   用 urlopen()读取 URL
*   将请求传递到一个美丽的输出()函数中
*   使用“img”标签查找所有标签(“src”)

**实施:**

## 蟒蛇 3

```py
from urllib.request import urlopen
from bs4 import BeautifulSoup

htmldata = urlopen('https://www.geeksforgeeks.org/')
soup = BeautifulSoup(htmldata, 'html.parser')
images = soup.find_all('img')

for item in images:
    print(item['src'])
```

**输出:**

> https://media . geesforgeks . org/WP-content/cdn-uploads/20201018234700/GFG-RT-DSA-creative . png
> https://media . geesforgeks . org/WP-content/cdn-uploads/logo-new-2 . SVG