# 使用‘python-nmap’的端口扫描器

> 原文:[https://www . geesforgeks . org/port-scanner-using-python-nmap/](https://www.geeksforgeeks.org/port-scanner-using-python-nmap/)

在本文中，我们将学习如何使用 Python 中的“`nmap`”模块对端口扫描器进行编程。该程序将一系列端口号作为输入，并打印该范围内所有端口的状态(打开或关闭)。

**Nmap** : Nmap 是一款免费开源的网络扫描工具。要运行本文中讨论的程序，您需要在系统中安装“nmap”工具。如果没有安装，请访问 [Nmap 下载页面](https://nmap.org/download.html)。

### 使用的模块

我们将使用“`python-nmap`”模块来完成这项任务。通过以下命令安装软件包(如果尚未安装)

```
pip install python-nmap

```

**注意:**未经适当许可和授权对目标进行“nmap”扫描是非法的。使用 localhost (127.0.0.1)作为目标

**例:**

```
import nmap

# take the range of ports to 
# be scanned
begin = 75
end = 80

# assign the target ip to be scanned to
# a variable
target = '127.0.0.1'

# instantiate a PortScanner object
scanner = nmap.PortScanner()

for i in range(begin,end+1):

    # scan the target port
    res = scanner.scan(target,str(i))

    # the result is a dictionary containing 
    # several information we only need to
    # check if the port is opened or closed
    # so we will access only that information 
    # in the dictionary
    res = res['scan'][target]['tcp'][i]['state']

    print(f'port {i} is {res}.')
```

**输出:**

```
port 75 is closed.
port 76 is closed.
port 77 is closed.
port 78 is closed.
port 79 is closed.
port 80 is open.

```

**注意**:输出可以根据端口的当前状态而变化。