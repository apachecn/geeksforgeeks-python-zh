# 网络编程 Python–HTTP 客户端

> 原文:[https://www . geesforgeks . org/network-programming-python-http-clients/](https://www.geeksforgeeks.org/network-programming-python-http-clients/)

HTTP 协议中来自客户端的请求到达服务器并获取一些数据，假设它是一个有效的请求。可以使用[请求](https://www.geeksforgeeks.org/python-requests-tutorial/)模块提供的各种方法来分析来自服务器的响应。下面的一些方法提供了关于从服务器发送到运行在客户端的 Python 程序的响应的信息:

## **获得初始响应**

[get()](https://www.geeksforgeeks.org/get-method-python-requests/) 方法用于获取服务器端使用的资源的基本信息。该函数从服务器获取数据，并作为响应对象返回，该响应对象可以简单的文本格式打印。

## 蟒 3

```py
# Import libraries
import requests

# Sending Request
req = requests.get('https://www.geeksforgeeks.org/')

# Show results
print(req.text[:2000])
```