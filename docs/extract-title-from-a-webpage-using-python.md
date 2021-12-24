# 使用 Python 从网页中提取标题

> 原文:[https://www . geesforgeks . org/extract-title-from-a-网页-使用-python/](https://www.geeksforgeeks.org/extract-title-from-a-webpage-using-python/)

**先决条件** [**使用**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)**[**Python urlib 模块**](https://www.geeksforgeeks.org/python-urllib-module/)**[**网页抓取工具**](https://www.geeksforgeeks.org/python-tools-world-web-scraping/)****

****在本文中，我们将编写 python 脚本，从给定的网页 URL 中提取网页的标题。****

******方法一:bs4** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。****

```
**pip install bs4** 
```

******请求**模块让你可以极其轻松的发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。****

```
**pip install requests** 
```

******进场:******

*   ****导入模块****
*   ****创建请求实例并传入网址****
*   ****将请求传递到一个美丽的输出()函数中****
*   ****使用“标题”标签查找所有标签(“标题”)****

******代码:******

## ****蟒蛇 3****

```
**# importing the modules
import requests
from bs4 import BeautifulSoup

# target url
url = 'https://www.geeksforgeeks.org/'

# making requests instance
reqs = requests.get(url)

# using the BeaitifulSoup module
soup = BeautifulSoup(reqs.text, 'html.parser')

# displaying the title
print("Title of the website is : ")
for title in soup.find_all('title'):
    print(title.get_text())**
```

******输出:******

```
**Title of the website is : 
GeeksforGeeks | A computer science portal for geeks** 
```

******方法二:**在该方法中，我们将使用 **urllib** 和**beautulsoup**模块提取网站标题。urllib 是一个包，允许您使用程序访问网页。****

****安装:****

```
**pip install urllib** 
```

******进场:******

*   ****导入模块****
*   ****用请求读取网址。****
*   ****从 HTML 文档中找到标题****

******实施:******

## ****蟒蛇 3****

```
**# importing the modules
from urllib.request import urlopen
from bs4 import BeautifulSoup

# target url
url = 'https://www.geeksforgeeks.org/'

# using the BeaitifulSoup module
soup = BeautifulSoup(urlopen(url))

# displaying the title
print("Title of the website is : ")
print (soup.title.get_text())**
```

******输出:******

```
**Title of the website is : 
GeeksforGeeks | A computer science portal for geeks** 
```

******方法 3:** 在此方法中，我们将使用**机械化**模块。它是 Python 中有状态的编程式网页浏览。通过简单的 HTML 表单填充和点击链接，以编程方式浏览页面。****

******安装:******

```
**pip install mechanize** 
```

******进场:******

*   ****导入模块。****
*   ****初始化浏览器()实例。****
*   ****检索网页内容浏览器。打开()。****
*   ****使用浏览器显示标题。标题()****

******实施:******

## ****蟒蛇 3****

```
**# importing the module
from mechanize import Browser

# target url
url = 'https://www.geeksforgeeks.org/'

# creating a Browser instance
br = Browser()
br.open(url)

# displaying the title
print("Title of the website is : ")
print( br.title())**
```

******输出:******

```
**Title of the website is : 
GeeksforGeeks | A computer science portal for geeks** 
```