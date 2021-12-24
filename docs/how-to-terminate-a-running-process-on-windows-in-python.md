# 如何在 Python 中终止 Windows 上运行的进程？

> 原文:[https://www . geeksforgeeks . org/如何终止运行在 python 窗口上的进程/](https://www.geeksforgeeks.org/how-to-terminate-a-running-process-on-windows-in-python/)

[**进程**](https://www.geeksforgeeks.org/introduction-of-process-management/) 是正在执行(处理)的程序。一个进程可能不必是由用户显式运行的，它可以是由操作系统产生的系统进程。任何在操作系统上执行的应用程序首先会创建一个自己的进程来执行。在典型的操作系统安装中，大多数进程都是操作系统服务和后台应用程序，运行它们是为了维护操作系统、软件和硬件。在本文中，我们将通过 python 了解终止运行在 Windows 操作系统上的进程的不同方法。首先，我们将描述一个 python 方法来实现这个结果，然后查看在 Windows 命令处理器中找到的一个命令来获得等效效果。

**注意:**此方法仅适用于 Windows 操作系统。为了在 Linux 上达到类似的效果，macOS 参考 Linux 中 [Kill 命令](https://www.geeksforgeeks.org/kill-command-in-linux-with-examples/)

### 预防措施

终止一个并发运行的进程应该适当地和有良心地完成。作为终止必要过程(例如。svhost、System、Windows Explorer、Antimalware Service Executable)可能会导致操作系统功能不一致，从而导致系统崩溃、死亡蓝屏、软件故障等。因此，通常建议仔细检查要提前终止的应用程序/工艺流程图的名称。

#### 方法 1:

首先，我们将使用 wmi 库来获取正在运行的进程的列表，然后使用这个列表来搜索我们想要的进程，如果找到，将终止它。要安装该模块，请在操作系统的命令解释器中执行以下命令:

```py
pip install wmi
```

**代码:**

## 蟒蛇 3

```py
# import wmi library
import wmi

# This variable ti would be used
# as a parity and counter for the
# terminating processes
ti = 0

# This variable stores the name
# of the process we are terminating
# The extension should also be
# included in the name
name = 'Process_Name'

# Initializing the wmi object
f = wmi.WMI()

# Iterating through all the
# running processes
for process in f.Win32_Process():

    # Checking whether the process
    # name matches our specified name
    if process.name == name:

        # If the name matches,
        # terminate the process   
        process.Terminate()

        # This increment would acknowledge
        # about the termination of the
        # Processes, and would serve as
        # a counter of the number of processes
        # terminated under the same name
        ti += 1

# True only if the value of
# ti didn't get incremented
# Therefore implying the
# process under the given
# name is not found
if ti == 0:

    # An output to inform the
    # user about the error
    print("Process not found!!!")
```

**说明:**

首先，我们定义一个存储整数值的变量，这个变量可以用来判断进程是否被终止。这个变量也可以用来确定有多少同名进程被终止。然后，我们指定我们愿意终止的进程的名称。之后我们初始化 wmi 库的 WMI()类。这让我们可以使用里面的方法，比如 WMI。Win32_Service，WMI。设计用于执行不同任务的 Win32_Process 等。我们将使用 *WMI。Win32_Process* 函数获取作为 wmi 对象运行的进程列表。然后我们使用 wmi 对象的 name 属性来获取正在运行的进程的名称。之后，我们将使用基本字符串匹配来确定应用程序的名称是否与之前指定的名称匹配。如果是，那么我们调用终止()方法来终止/终止进程。之后，我们增加 ti 的值，其中增加的值(或任何非 0 值)将表示至少一个进程已经终止。在循环结束后(当所有正在运行的进程名称都被检查时)，我们将检查变量 ti 的值是否仍然为 0。如果是，则没有进程被终止，我们使用错误消息通知用户。

#### 方法 2:

现在，我们将使用 windows 命令处理器中名为 **WMIC** (Windows 管理工具命令行)的内置实用程序来终止运行的进程。我们将使用的命令:

```py
wmic process where name="Process_Name" delete
```

其中，进程名称是我们要终止的进程的名称。为了用 python 实现这个实用程序，我们将使用 **os.system()** 创建一个 Windows 命令行实例，并在那里执行命令(绕过它作为参数)。
T3】代号:

## 蟒蛇 3

```py
# import os module
import os

# delete given process
os.system('wmic process where name="Process_Name" delete')
```

**输出:**

> 正在删除实例\ \ DESKTOP-LI99O 93 \ ROOT \ CIMV 2:Win32 _ Process。handle =“5140”
> 实例删除成功。