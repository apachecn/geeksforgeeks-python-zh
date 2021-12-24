# 使用 Python 获取 MICR 代码

> 原文:[https://www.geeksforgeeks.org/get-micr-code-using-python/](https://www.geeksforgeeks.org/get-micr-code-using-python/)

MICR 代表磁性墨水字符识别，通常用于银行。这是一个 9 位数的代码，用于识别银行分行的位置。MICR 代码是使用 MICR(磁性墨水字符识别技术)打印在支票上的代码。这使得能够识别支票，进而意味着更快的处理。在本文中，我们将编写一个 python 脚本来使用银行信息获取 MICR 代码。

**所需模块:**

*   [**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)【T4:美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```
pip install bs4

```

*   [**请求**](https://www.geeksforgeeks.org/python-requests-tutorial/) **:** 请求让你发送 HTTP/1.1 请求极其轻松。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

```
pip install requests

```

**进场:**

*   导入模块
*   将银行信息合并到网址中
*   创建请求实例并传入网址
*   将请求传递到一个美丽的输出()函数中
*   遍历 MICR 代码到汤对象中

**实施:**

## 蟒蛇 3

```
# import module
import requests
from bs4 import BeautifulSoup

# link for extract html data
# Making a GET request
def getdata(url):
    r = requests.get(url)
    return r.text

# input by geek
# bank details
bank_name = "KOTAK_MAHINDRA_BANK"
state = "BIHAR"
city = "PATNA"
branch = "PATNA"

# url
url = "https://bankifsccode.com/"+bank_name+"/"+state+"/"+city+"/"+branch

# pass the url
# into getdata function
htmldata = getdata(url)
soup = BeautifulSoup(htmldata, 'html.parser')

# traverse the data
data = []
for i in (soup.find_all('a')):
    data.append((i.get_text()))

print("MICR Code :")
print(data[17])
```

**输出:**

```
MICR Code :
800485005

```