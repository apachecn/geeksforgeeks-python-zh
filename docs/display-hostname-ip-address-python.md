# 用 Python 显示主机名和 IP 地址

> 原文:[https://www . geesforgeks . org/display-hostname-IP-address-python/](https://www.geeksforgeeks.org/display-hostname-ip-address-python/)

有许多方法可以找到本地机器的主机名和 IP 地址。这里有一个使用 python 代码查找主机名和 IP 地址的简单方法。
使用的库–**插座**:该模块提供对 BSD 插座接口的访问。它可以在所有现代的 Unix 系统、Windows、MacOS 以及其他平台上使用。
**所用方法:**

*   **gethostname()**:gethostname 函数检索本地计算机的标准主机名。
*   **gethostbyname()**:gethostbyname 函数从主机数据库中检索与主机名对应的主机信息。

## 蟒蛇 3

```py
# Python3 code to display hostname and
# IP address

# Importing socket library
import socket

# Function to display hostname and
# IP address
def get_Host_name_IP():
    try:
        host_name = socket.gethostname()
        host_ip = socket.gethostbyname(host_name)
        print("Hostname :  ",host_name)
        print("IP : ",host_ip)
    except:
        print("Unable to get Hostname and IP")

# Driver code
get_Host_name_IP() #Function call

#This code is contributed by "Sharad_Bhardwaj".
```

**输出:**

```py
Hostname :   pppContainer
IP :  10.98.162.168
```

**注**:输出因机器而异。