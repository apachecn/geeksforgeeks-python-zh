# 使用 Python 硒模块下载 Instagram 帖子

> 原文:[https://www . geesforgeks . org/download-insta gram-post-using-python-selenium-module/](https://www.geeksforgeeks.org/download-instagram-posts-using-python-selenium-module/)

在本文中，我们将学习如何使用 Python *Selenium* 模块下载个人资料的 Instagram 帖子。

### 要求:

*   谷歌 Chrome 还是火狐
*   [Chrome 驱动](https://chromedriver.chromium.org/downloads)(针对谷歌 Chrome)或 [Gecko 驱动](https://github.com/mozilla/geckodriver/releases)(针对 Mozilla Firefox)
*   **硒包:**是通过程序控制网页浏览器的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等。在 can 中，使用以下命令安装:

```
pip install selenium 
```

*   [**【漂亮的 Soap 包】**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/) **:** 是一个从 HTML 和 XML 文件中拉出数据的 Python 库。它与您最喜欢的解析器一起工作，提供导航、搜索和修改解析树的惯用方式。它可以使用以下命令安装:

```
pip install bs4
```

*   [**请求包:**](https://www.geeksforgeeks.org/python-requests-tutorial/) 请求库是 Python 的一个组成部分，用于向指定的 URL 发出 HTTP 请求。可以使用以下命令安装:

```
pip install requests
```

### 逐步方法:

**第一步:**导入模块，输入登录信息和页面网址。

## 蟒 3

```
# import required modules
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import selenium.common.exceptions
import time
from bs4 import BeautifulSoup as bs
import requests
import os

# get instagram account credentials
username = input('Enter Your User Name ')
password = input('Enter Your Password ')

# assign URL
url = 'https://instagram.com/' + \
    input('Enter User Name Of User For Downloading Posts ')
```