# 使用 Python 在蓝牙设备不在范围内时锁定电脑

> 原文:[https://www . geesforgeks . org/locking-computer-当-bluetooth-device-in-range-use-python/](https://www.geeksforgeeks.org/locking-computer-when-bluetooth-device-is-not-in-range-using-python/)

Python 提供了使用手机的蓝牙 UUID 地址作为任何系统的物理安全令牌的可访问性。这可以在名为 **PyBluez** 的 Python 包的帮助下完成。Pybluez 可以安装在 Linux、Windows 和 macOS 中，并且兼容 Python 2.7 和 3.x。

#### 所需安装:

需要的模块有:

*   **Pybluez:** This module allows the use of system Bluetooth resources. To install it, type the following command in the terminal.

    ```
    python3 -m pip install pybluez
    ```

*   **Schedule:** The schedule library is used to schedule tasks at a specific time every day or a specific day of the week. To install it, type the following command in the terminal.

    ```
    python3 -m pip install schedule
    ```

#### 方法:

PyBluez 是一个带有蓝牙资源的包，允许 Python 开发人员轻松创建蓝牙应用程序。首先，必要的包已经被导入到程序中。`PyBluez`导入为蓝牙，`schedule`导入为调度程序，`time`包导入为处理时间相关任务，`ctypes`导入为使用其他语言的现有库，通过 Python 编写简单的包装器。以下是步骤。

*   定义了一个函数`job()`，在变量`inputBdaddr`中声明了你手机的蓝牙地址。变量`passed`被初始化为假，以跟踪在发现的设备中是否找到给定的蓝牙地址。要搜索附近可用的蓝牙设备，请使用`bluetooth.discover_devices()`。结果保存在除试块内的变量`scan`中。如果在`scan`中找到所需设备，变量`passed`设置为真，否则为假。
*   如果`passed`被发现为假，表示没有找到需要的设备，工作站被锁定。
*   现在通过每 30 秒调用一次函数`job()`来安排上述步骤。while 循环用于检查是否有任何计划任务等待运行。

下面是实现:

```
# Import required packages
import schedule
import time
import bluetooth
import ctypes

def job():
    # Find your bluetooth uuid in your
    # mobile and give set it in the 
    # variable
    inputBdaddr = "XX:XX:XX:XX:XX:XX"

    # Variable to find whether the
    # given bluetooth uuid is 
    # present in the discovered devices
    passed = False

    # Try to search for the nearby 
    # visible devices
    try:
        # Get the list of discovered devices
        scan = bluetooth.discover_devices()

        # Search for your bluetooth uuid 
        # in the scanned devices If found
        # set the variable to true else 
        # set the variable to false
        if inputBdaddr in scan:
            passed = True

        else:
            passed = False

    except:
        passed = False

    # When bluetooth device 
    # is not found, lock the
    # workstation
    if not passed:
        ctypes.windll.user32.LockWorkStation()

# Schedule the process 
# to run every 30 seconds
schedule.every(30).seconds.do(job)

# Check whether a scheduled 
# task is pending to run or not
while 1:
    schedule.run_pending()
    time.sleep(1)
```

**限制:**

由于 PyBluez 没有在积极开发中，蓝牙检测是概率性的。discover_devices()有时无法检测到范围内的设备。在这种情况下，在放弃之前再试一两次可能是个好主意。