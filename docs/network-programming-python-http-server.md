# 网络编程 Python–HTTP 服务器

> 原文:[https://www . geesforgeks . org/network-programming-python-http-server/](https://www.geeksforgeeks.org/network-programming-python-http-server/)

HTTP 网络服务器只是一个在机器上运行的进程，它通过特定的 IP 和端口号监听传入的 HTTP 请求，然后发回请求响应。

Python 有一个由其标准库提供的内置 webserver，可以调用它进行简单的客户端-服务器通信。 *http 服务器*和 *socketserver* 是用来创建 web 服务器的两个主要功能。端口号可以在用于访问 web 服务器的程序中手动定义。这个网络服务器对于许多类型的文件格式都是有效的，但是它的功能并不全。通过使用所需的响应代码进行响应，可以轻松解析和提供简单的静态 HTML 文件。下面给出了 python HTTP web 服务器的一个基本实现:

示例 HTML 文件:

> <title>Python HTTP 服务器</title>
> 
> # 简单 HTTP 服务器
> 
> 恭喜！HTTP 服务器正在工作！
> 
> 欢迎来到极客论坛

## 蟒蛇 3

```py
# Import libraries
import http.server
import socketserver

# Defining PORT number
PORT = 8080

# Creating handle
Handler = http.server.SimpleHTTPRequestHandler

# Creating TCPServer
http = socketserver.TCPServer(("", PORT), Handler)

# Getting logs
print("serving at port", PORT)
http.serve_forever()
```

**输出:**

```py
serving at port 8080
127.0.0.1 - - [17/Oct/2020 00:31:27] "GET / HTTP/1.1" 200 -

```

![](img/93d33225bbc4581997c9a190b7cbfcec.png)

在保存 HTML 文件的目录中执行上述程序。创建网络服务器后，打开网络浏览器，在网址中输入 ***。***

这里 *SimpleHTTPRequestHandler* 用于创建自定义处理程序。 *TCPServer* 告诉服务器发送和接收消息。要调用*TCP 服务器*，需要两个参数:TCP 地址，即 IP 和端口，第二个参数是处理程序。TCP 地址是由 IP 地址和端口号组成的元组。 *Serve_forever()* 是 *TCPServer* 实例的一个功能，它启动服务器并监听和响应传入的请求。

*localhost* 是主机(在我们的例子中是我们正在使用的系统)，用于使用环回网络接口访问网络服务。

如果 python 程序仅用作本地主机服务，则以下程序用于此目的:

## 蟒蛇 3

```py
# Import libraries
import sys
import http.server
import socketserver

# Creating handle
HandlerClass = http.server.SimpleHTTPRequestHandler

# Creating Server
ServerClass  = http.server.HTTPServer

# Defining protocol
Protocol     = "HTTP/1.0"

# Setting TCP Address
if sys.argv[1:]:
    port = int(sys.argv[1])
else:
    port = 8000
server_address = ('127.0.0.1', port)

# invoking server
HandlerClass.protocol_version = Protocol
http = ServerClass(server_address, HandlerClass)

# Getting logs
sa = http.socket.getsockname()
print("Serving HTTP on", sa[0], "port", sa[1], "...")
http.serve_forever()
```

**输出:**

![](img/a33caffe43851611ca320ef7a4b12dc7.png)