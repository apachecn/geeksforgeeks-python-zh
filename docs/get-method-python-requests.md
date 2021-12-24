# GET 方法–Python 请求

> 原文:[https://www.geeksforgeeks.org/get-method-python-requests/](https://www.geeksforgeeks.org/get-method-python-requests/)

请求库是 Python 向指定网址发出 HTTP 请求的重要方面之一。本文围绕如何使用**请求向指定的网址发出 GET 请求展开。GET()** 方法。在检查 GET 方法之前，让我们弄清楚 GET 请求是什么–

#### 获取 Http 方法

GET 方法用于使用给定的 URI 从给定的服务器检索信息。GET 方法发送附加到页面请求的编码用户信息。页面和编码信息用“？”分隔性格。
例如:

```py
https://www.google.com/search?q=hello
```

#### 如何通过 Python 请求发出 GET 请求

Python 的 requests 模块提供了一个名为 **get()** 的内置方法，用于向指定的 URI 发出 get 请求。

**语法–**

```py
requests.get(url, params={key: value}, args)

```

**示例–**

出于示例目的，让我们尝试向 github 的 API 发出请求。

```py
import requests

# Making a GET request
r = requests.get('https://api.github.com / users / naveenkrnl')

# check status code for response received
# success code - 200
print(r)

# print content of request
print(r.content)
```

将此文件保存为 request.py 并通过终端运行，

```py
python request.py
```

**输出–**
![python-requests-get-method](img/0fec1d90a02d489d3d6be501534214d8.png)

#### 使用获取方法的优势

*   由于 GET 方法发送的数据显示在 URL 中，因此可以用特定的查询字符串值为页面添加书签。
*   获取请求可以被缓存，并且获取请求保留在浏览器历史记录中。
*   可以将 GET 请求加入书签。

#### 使用 GET 方法的缺点

*   GET 方法不适合传递用户名和密码等敏感信息，因为这些信息在 URL 查询字符串中是完全可见的，并且可能作为被访问的页面存储在客户端浏览器的内存中。
*   因为 GET 方法将数据分配给服务器环境变量，所以 URL 的长度是有限的。因此，发送的总数据是有限制的。