# 如何使用 Python 检查用户上网是开还是关？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 检查用户是上网还是关机/](https://www.geeksforgeeks.org/how-to-check-whether-users-internet-is-on-or-off-using-python/)

在开发我们的项目时，我们经常需要一个检查用户系统的互联网是开着还是关着的解决方案。下面是一些使用 Python 检查的简单解决方案。有两种方法可以实现这一点:

**方法 1:** 使用“httplib”

### 方法

*   我们导入了 http.client 库。
*   已将网址初始化为 www.geeksforgeeks.org
*   我们试图与给定的网址建立连接。
*   只要求网页的标题，以便快速操作。
*   如果连接打开并显示消息，则返回 True。
*   如果异常不起作用，就会捕捉到异常并显示错误消息。

**示例:**

## 蟒蛇 3

```
# importing required module
import http.client as httplib

# function to check internet connectivity
def checkInternetHttplib(url="www.geeksforgeeks.org", timeout=3):
    connection = httplib.HTTPConnection(url, timeout=timeout)
    try:
        # only header requested for fast operation
        connection.request("HEAD", "/")
        connection.close()  # connection closed
        print("Internet On")
        return True
    except Exception as exep:
        print(exep)
        return False

checkInternetHttplib("www.geeksforgeeks.org", 3)
```

**输出:**

```
Internet On
```

**方法 2:** 使用 requests.get()

### 方法

*   导入所需的请求模块
*   正在初始化 geeksforgeeks.org 的网址
*   将超时初始化为 10
*   请求给定的网址。
*   打印“互联网已打开”或会产生异常。
*   捕捉异常并打印“互联网已关闭”

## 蟒蛇 3

```
# importing requests module
import requests

# initializing URL
url = "https://www.geeksforgeeks.org"
timeout = 10
try:
    # requesting URL
    request = requests.get(url, timeout=timeout)
    print("Internet is on")

# catching exception
except (requests.ConnectionError, requests.Timeout) as exception:
    print("Internet is off")
```

**输出:**

```
Internet is off
```