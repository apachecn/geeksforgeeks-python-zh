# 如何检查 Python 中的应用程序是否打开？

> 原文:[https://www . geeksforgeeks . org/如何检查应用程序是否在 python 中打开/](https://www.geeksforgeeks.org/how-to-check-if-an-application-is-open-in-python/)

这篇文章是关于如何在使用 Python 的系统中检查应用程序是否打开。您也可以参考文章[Python–获取运行进程列表](https://www.geeksforgeeks.org/python-get-list-of-running-processes/)了解更多信息。

在下面的方法中，我们将检查*chrome.exe*是否在我们的系统中打开。

### **使用 psutil**

*psutil* 是 python 的系统监控和系统利用模块。它主要用于系统监控、分析和限制进程资源，以及管理正在运行的进程。可以监控 CPU、内存、磁盘、网络、传感器等资源的使用情况。Python、2.7 和 3.4+版本支持它。您可以使用以下命令安装 *psutil* 模块

```
pip install psutil
```

我们将使用 **psutil.process_iter()** 方法，它返回一个迭代器，为本地机器上所有正在运行的进程生成一个进程类实例。

## 蟒 3

```
# import module
import psutil

# check if chrome is open
"chrome.exe" in (i.name() for i in psutil.process_iter())
```

**输出:**

```
True
```

我们导入 *psutil* 模块。然后我们使用 *psutil.process_iter()* 在本地机器上的所有运行进程中搜索*chrome.exe*。如果找到，它将返回输出为*真*，否则为*假*。

### **使用 WMI(仅限 Windows 用户)**

*wmi* 模块可用于获取 Windows 机器的系统信息，可使用以下命令安装:

```
pip install wmi
```

其工作原理类似于 *psutil* 。在这里，我们检查一个特定的进程名称是否出现在正在运行的进程列表中。

## 蟒 3

```
# Import module
import wmi

# Initializing the wmi constructor
f = wmi.WMI()

flag = 0

# Iterating through all the running processes
for process in f.Win32_Process():
    if "chrome.exe" == process.Name:
        print("Application is Running")
        flag = 1
        break

if flag == 0:
    print("Application is not Running")
```

**输出:**

```
Application is Running
```

我们导入 *wmi* 模块。然后我们通过遍历进程名在本地机器上的所有运行进程中搜索*chrome.exe*。如果符合流程。名称，将打印*应用程序正在运行*，否则*应用程序未运行*。