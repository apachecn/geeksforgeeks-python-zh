# PUT 和 POST HTTP 请求的区别

> 原文:[https://www . geeksforgeeks . org/put 和 post-http-requests 之间的差异/](https://www.geeksforgeeks.org/diffrence-between-put-and-post-http-requests/)

在发出 HTTP 请求时，PUT 和 POST 请求肯定有很多相似之处，两者都可以处理，这样一个执行另一个的功能。本文围绕 PUT 和 POST 请求之间的主要区别展开。

#### 放 HTTP 请求

PUT 是万维网使用的 HTTP 支持的请求方法。PUT 方法要求将封闭实体存储在提供的 URI 下。如果 URI 引用了一个已经存在的资源，它将被修改，如果 URI 没有指向一个现有的资源，那么服务器可以用那个 URI 创建资源。
**示例–**
为了示例目的，让我们尝试向 httpbin 的 API 发出请求。

## 蟒蛇 3

```
import requests

# Making a PUT request
r = requests.put('https://httpbin.org/put', data={'key':'value'})

#check status code for response received
# success code - 200
print(r)

# print content of request
print(r.content)
```