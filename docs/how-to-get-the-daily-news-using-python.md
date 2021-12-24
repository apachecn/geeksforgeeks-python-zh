# 如何使用 Python 获取每日新闻

> 原文:[https://www . geesforgeks . org/如何使用 python 获取每日新闻/](https://www.geeksforgeeks.org/how-to-get-the-daily-news-using-python/)

在本文中，我们将看到如何使用 Python 获取每日新闻。这里我们将使用美丽的汤和请求模块来刮数据。

## **需要的模块**

*   [**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)【T4:美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install bs4
```

*   [**请求**](https://www.geeksforgeeks.org/python-requests-tutorial/) **:** 请求让你发送 HTTP/1.1 请求极其轻松。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install requests
```

## 逐步实施:

**第一步:**首先，确保导入这些库。

## 蟒 3

```py
import requests
from bs4 import BeautifulSoup
```