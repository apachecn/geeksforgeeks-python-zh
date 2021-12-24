# 使用 Python 进行磁性墨水字符识别

> 原文:[https://www . geesforgeks . org/magic-ink-字符识别-使用-python/](https://www.geeksforgeeks.org/magnetic-ink-character-recognition-using-python/)

磁性墨水字符识别或 MICR，通常用于银行。这是一个 9 位数的代码，用于识别银行分行的位置。MICR 代码是使用 MICR(磁性墨水字符识别技术)打印在支票上的代码。这使得能够识别支票，进而意味着更快的处理。在本文中，我们将编写一个 python 脚本来验证 MICR 代码并提取信息。

### **需要的模块**

*   [**bs4:**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/) 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install bs4

```

*   [**请求:**](https://www.geeksforgeeks.org/python-requests-tutorial/) 请求可以让你极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install requests

```

**进场:**

*   导入模块
*   将 MICR 代码合并到网址
*   创建请求实例并传入网址
*   将请求传递到一个美丽的输出()函数中
*   遍历信息 MICR 代码到汤对象中

**实施:**

## 蟒蛇 3

```py
# import module
import requests
from bs4 import BeautifulSoup

# link for extract html data
# Making a GET request
def getdata(url):
    r = requests.get(url)
    return r.text

# input by geek
# MICR code
Micr = "800002012"

# url
url = "https://micr.bankifsccode.com/"+Micr

# pass the url
# into getdata function
htmldata = getdata(url)
soup = BeautifulSoup(htmldata, 'html.parser')

# traverse the bank information
data = []
for i in (soup.find_all("div", class_="text6")):
    data.append((i.get_text()))

# Validate the
# data
if len(data) == 0:
    print("Not Valid MICR Code")
else:
    print("Found")
    print(data)
```

**输出:**

```py
Found
['MICR Code:- 800002012, STATE BANK OF INDIA, DIGHA']

```