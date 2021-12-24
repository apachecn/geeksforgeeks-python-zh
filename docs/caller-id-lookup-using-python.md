# 使用 Python 查找来电显示

> 原文:[https://www . geesforgeks . org/来电显示-查找-使用-python/](https://www.geeksforgeeks.org/caller-id-lookup-using-python/)

**先决条件**:

*   [靓汤](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)
*   [请求模块](https://www.geeksforgeeks.org/python-requests-tutorial/)

在本文中，我们将看到如何使用[numverify](https://numverify.com/) API 获取来电显示信息。Numverify 提供了一个强大的工具，只需使用一个简单的网址发出请求，就可以以便携式 JSON 格式提供电话号码验证和信息查找。

为了让下面的程序工作，你必须有一个应用编程接口密钥，要获得一个，只需[点击这里](https://numverify.com/documentation)。

**所需模块:**

*   **bs4:** 美人汤(bs4)是一个从 HTML 和 XML 文件中拉出数据的 Python 库。这个模块没有内置 Python。要安装，请在您的终端中键入以下命令。

```
pip install bs4
```

*   **请求:** Request 让你可以极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装，请在您的终端中键入以下命令。

```
pip install requests
```

**进场:**

*   导入模块
*   为 GET 请求创建一个函数
*   传递带有现有应用编程接口密钥、手机号码和国家代码的网址
*   现在检索来电显示信息

**程序:**

## 蟒蛇 3

```
# import module
import requests
import pandas as pd
from bs4 import BeautifulSoup

# link for extract html data
# Making a GET request

def getdata(url):
    r=requests.get(url)
    return r.text
# API key
# Enter your own API key instead of 'YOUR API KEY'
api = 'YOUR API KEY'

# number and country code
number = '9852638787'
country = 'IN'

# pass Your API, number and country code
# in getdata function
htmldata=getdata('http://apilayer.net/api/validate?access_key='+api+'&number='+number+'&country_code='+country+'&format=1')
soup = BeautifulSoup(htmldata, 'html.parser')
print(soup)
```

**输出:**

> {
> 
> “有效”:真，
> 
> “号码”:“919852638787”，
> 
> “local _ format”:“09852638787”，
> 
> " international _ format ":+919852638787 "、
> 
> “country _ prefix”:“+91”，
> 
> “国家代码”:“输入”，
> 
> “国家名称”:“印度(共和国)”，
> 
> “位置”:“比哈尔邦”，
> 
> “运营商”:“Aircel 蜂窝有限公司”，
> 
> " line_type":"mobile "
> 
> }