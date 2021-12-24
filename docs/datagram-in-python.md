# Python 中的数据报

> 原文:[https://www.geeksforgeeks.org/datagram-in-python/](https://www.geeksforgeeks.org/datagram-in-python/)

数据报是两个端点之间的一种无线通信，它需要 ip 地址和端口号来建立连接。数据报使用 UDP(用户数据报协议)，它将用户数据转换成小数据包或数据块，以便可以通过网络以连续的方式发送。在 UDP 类型的连接中，数据包在发送端没有记录，它只是由用户发送，然后由接收方决定是否接受数据包。我们在视频会议或视频通话中使用的 UDP 连接类型。

让我们学习如何在本地主机网络上发送一些数据，并在同一台机器上接收与接收器相同的数据，以演示数据报的使用。

要了解计算机的 IP 配置，请在终端上使用以下命令:

```
ipconfig
```

**代码#1:** 发送方结束。

```
# importing socket module
import socket

UDP_IP = "localhost"
UDP_PORT = 8080
MESSAGE = "GeeksforGeeks"

print ("message:", MESSAGE)

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.sendto(bytes(MESSAGE, "utf-8"), (UDP_IP, UDP_PORT))
```

**输出:**

```
message: Geeksforgeeks
```

**说明:**

*   在 **UDP_IP** 处指定您的 IPv4 地址，记住端口号 8080 是您的本地主机端口号，所以您需要指定相同的端口号。
*   `socket.socket()`使用 *AF_INET* 以便使用您系统的 IPv4 地址，而 **SOCK_DGRAM** 是我们用于通信的一种协议。
*   使用 *sock* 对象调用函数`sendto()`，然后传递包含 IP 地址和端口号的元组的参数。

**步骤#2:** 在接收端。

```
# importing socket module
import socket

UDP_IP = "localhost"
UDP_PORT = 8080

sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
sock.bind((UDP_IP, UDP_PORT))

while True:
    # buffer size is 1024 bytes
    data, addr = sock.recvfrom(1024) 
    print ("Received message:", data)
```

**输出:**

```
Received Message: b'Geeksforgeeks'
```

**说明:**

*   我们需要在`UDP_IP`中指定 localhost IPaddress，使用 **socket.socket()** 功能同上。
*   **将**参数绑定到套接字对象，这样在这些端口地址接收到的任何东西都会被我们捕获。在循环中，将缓冲区大小定义为 1024，因为消息不大，它是足够的缓冲区大小。