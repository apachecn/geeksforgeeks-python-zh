# Python–获取正在运行的进程列表

> 原文:[https://www . geesforgeks . org/python-get-list-of-running-processes/](https://www.geeksforgeeks.org/python-get-list-of-running-processes/)

A *进程*是正在执行(处理)的程序。一个进程可能不必是由用户显式运行的，它可以是由操作系统产生的系统进程。任何在操作系统上执行的应用程序首先创建一个自己的进程来执行。在典型的操作系统安装中，大多数进程都是操作系统服务和后台应用程序，运行它们是为了维护操作系统、软件和硬件。
在本文中，我们将了解通过 Python 获取 Windows 操作系统运行进程列表的不同方法。首先，我们将描述一个 python 方法来获得结果，然后查看在 Windows 命令处理器中找到的命令。
**方法 1:**
我们将使用 wmi 库获取 Windows 操作系统上正在运行的进程列表。为了安装该模块，请在操作系统的命令解释器中执行以下命令:-

```py
pip install wmi

```

**COde:**

## 蟒蛇 3

```py
import wmi

# Initializing the wmi constructor
f = wmi.WMI()

# Printing the header for the later columns
print("pid   Process name")

# Iterating through all the running processes
for process in f.Win32_Process():

    # Displaying the P_ID and P_Name of the process
    print(f"{process.ProcessId:<10} {process.Name}")
```