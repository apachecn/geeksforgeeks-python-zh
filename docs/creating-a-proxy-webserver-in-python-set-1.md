# 用 Python 创建代理网络服务器|第 1 集

> 原文:[https://www . geesforgeks . org/creating-a-proxy-web server-in-python-set-1/](https://www.geeksforgeeks.org/creating-a-proxy-webserver-in-python-set-1/)

与 c 相比，python 中的套接字编程非常用户友好。程序员不需要担心关于套接字的细节。在 python 中，用户有更多的机会关注应用层，而不是网络层。在本教程中，我们将开发一个能够处理 HTTP 流量的简单多线程代理服务器。它将主要基于基本的套接字编程思想。如果你不确定基础知识，那么我建议你在学习本教程之前复习一下。

这是代理服务器的幼稚实现。在接下来的教程中，我们将逐渐把它开发成一个非常有用的服务器。

**首先，我们将通过 3 个简单的步骤**来完成这个过程

**1。创建一个传入的套接字**
我们在服务器类的 __init__ 方法中创建一个套接字服务器套接字。这为传入连接创建了一个套接字。然后我们绑定套接字，然后等待客户端连接。

```py
def __init__(self, config):
    # Shutdown on Ctrl+C
    signal.signal(signal.SIGINT, self.shutdown) 

    # Create a TCP socket
    self.serverSocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    # Re-use the socket
    self.serverSocket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)

    # bind the socket to a public host, and a port   
    self.serverSocket.bind((config['HOST_NAME'], config['BIND_PORT']))

    self.serverSocket.listen(10) # become a server socket
    self.__clients = {}

```

**2。接受客户并处理**
这是所有步骤中最简单也是最重要的。我们等待客户端的连接请求，一旦连接成功，我们就在一个单独的线程中发送请求，让我们自己可以处理下一个请求。这使我们能够同时处理多个请求，从而将服务器的性能提升了数倍。

```py
while True:

    # Establish the connection
    (clientSocket, client_address) = self.serverSocket.accept() 

    d = threading.Thread(name=self._getClientName(client_address), 
    target = self.proxy_thread, args=(clientSocket, client_address))
    d.setDaemon(True)
    d.start()

```

**3。重定向流量**
代理服务器的主要功能是充当源和目的地之间的中介。在这里，我们将从源获取数据，然后将其传递给客户端。

*   首先，我们从接收到的请求数据中提取网址。

```py
# get the request from browser
request = conn.recv(config['MAX_REQUEST_LEN']) 

# parse the first line
first_line = request.split('\n')[0]

# get url
url = first_line.split(' ')[1]
```

*   然后，我们找到请求的目的地址。地址是**(目的地 _ ip _ 地址，目的地 _ 端口号)**的元组。我们将从这个地址接收数据。

```py
http_pos = url.find("://") # find pos of ://
if (http_pos==-1):
    temp = url
else:
    temp = url[(http_pos+3):] # get the rest of url

port_pos = temp.find(":") # find the port pos (if any)

# find end of web server
webserver_pos = temp.find("/")
if webserver_pos == -1:
    webserver_pos = len(temp)

webserver = ""
port = -1
if (port_pos==-1 or webserver_pos < port_pos): 

    # default port 
    port = 80 
    webserver = temp[:webserver_pos] 

else: # specific port 
    port = int((temp[(port_pos+1):])[:webserver_pos-port_pos-1])
    webserver = temp[:port_pos] 

```

*   现在，我们建立到目标服务器(或远程服务器)的新连接，然后向服务器发送原始请求的副本。然后，服务器将做出响应。所有响应消息使用 **RFC 822** 的通用消息格式。

```py
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
s.settimeout(config['CONNECTION_TIMEOUT'])
s.connect((webserver, port))
s.sendall(request)

```

*   然后，我们将服务器的响应重定向到客户端。conn 是客户端的原始连接。响应可能比我们在一次调用中收到的 MAX_REQUEST_LEN 更大，因此，空响应标志着响应的结束。

```py
while 1:
    # receive data from web server
    data = s.recv(config['MAX_REQUEST_LEN'])

    if (len(data) > 0):
        conn.send(data) # send to browser/client
    else:
        break

```

然后，我们适当地关闭服务器连接，并进行错误处理，以确保服务器按预期工作。

**如何测试服务器？**
1。在终端上运行服务器。保持它运行并切换到您最喜欢的浏览器。
2。转到浏览器的代理设置，将代理服务器更改为“localhost”，并将端口更改为“12345”。
3。现在打开任何 HTTP 网站(不是 HTTPS)，例如 geeksforgeeks.org 和伏尔拉！！您应该能够访问浏览器上的内容。

一旦服务器开始运行，我们就可以监控到达客户端的请求。我们可以使用这些数据来监控正在进行的内容，或者我们可以根据内容开发统计数据。
我们甚至可以限制访问某个网站，或者将某个 IP 地址列入黑名单。我们将在即将到来的教程中处理更多这样的特性。
接下来呢？
在接下来的教程中，我们将在代理服务器中添加以下功能。
–将域名列入黑名单
–内容监控
–日志记录
–HTTP 网络服务器+代理服务器

本教程的全部工作源代码可在[这里](https://drive.google.com/file/d/0Bw6qkH-Uvw8Zbnl4RU5xcjNEOHc/view)获得

[用 Python 创建代理网络服务器|第 2 集](https://www.geeksforgeeks.org/kruskals-algorithm-using-stl-in-c/)

如果你有任何问题/意见，请在评论区发表。

关于作者:

**平克什·巴杰蒂亚**来自 IIIT 海得拉巴。他本质上是一个极客，有大量值得寻找的项目。他的项目作品可以在这里看到[。](https://github.com/pinkeshbadjatiya/)

如果你也想在这里展示你的博客，请查看 [GBlog](http://geeksquiz.com/gblog/) 在 GeeksforGeeks 上的客座博文。