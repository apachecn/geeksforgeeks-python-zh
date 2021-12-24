# Python–获取系统已连接的所有 Wifi 设备

> 原文:[https://www . geeksforgeeks . org/python-获取所有 wifi 设备-系统已连接/](https://www.geeksforgeeks.org/python-getting-all-the-wifi-devices-the-system-has-connected/)

在这篇文章中，我们将看到我们如何能够所有的 wifi 网络上的系统曾经连接。Wi-Fi 是一种无线网络技术，允许计算机(笔记本电脑和台式机)、移动设备(智能手机和可穿戴设备)和其他设备(打印机和摄像机)等设备与互联网连接。
为此，我们将使用子流程模块。Python 中存在的子进程模块(2.x 和 3.x)用于通过创建新的进程，通过 Python 代码运行新的应用程序或程序。它还有助于获得输入/输出/错误管道以及各种命令的退出代码。
为了获得 wifi 设备系统连接的信息，我们将使用下面给出的命令

```
subprocess.check_output(['netsh', 'wlan', 'show', 'profiles'])
```

这个命令将返回字节格式的元数据，以便获得我们必须解码和过滤的网络名称，从而获得所需的输出。
下面是实现

## 蟒蛇 3

```
# importing subprocess
import subprocess

# getting meta data of the wifi network
meta_data = subprocess.check_output(['netsh', 'wlan', 'show', 'profiles'])

# decoding meta data from byte to string
data = meta_data.decode('utf-8', errors ="backslashreplace")

# splitting data by line by line
# string to list
data = data.split('\n')

# creating a list of wifi names
names = []

# traverse the list
for i in data:

    # find "All User Profile" in each item
    # as this item will have the wifi name
    if "All User Profile" in i :

        # if found split the item
        # in order to get only the name
        i = i.split(":")

        # item at index 1 will be the wifi name
        i = i[1]

        # formatting the name
        # first and last chracter is use less
        i = i[1:-1]

        # appending the wifi name in the list
        names.append(i)

# printing the wifi names
print("All wifi that system has connected to are ")
print("-----------------------------------------")
for name in names:
    print(name)
```

**输出:**

```
All wifi that system has connected to are 
-----------------------------------------
Engineer_5GHz
Engineer
honor
Redmi
Ayush
BiGX-cmtqaGFtYjc
UERJTTBV8e0GUmVkbWkg 2
DESKTOP-F32H70N 5009
UERJTTBV8e0GUmVkbWkg
Bunns
Hogwarts
Cgc wireless
Moto G (5) Plus 8691
AndroidAP
AndroidAPab7e
roshan
Svj?
Hey
AndroidAP202
JARVIS
B6NO-wq5hamF0IGt1bWHCrg
CDAC
```