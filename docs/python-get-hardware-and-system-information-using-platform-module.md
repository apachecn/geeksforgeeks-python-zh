# Python–使用平台模块

获取硬件和系统信息

> 原文:[https://www . geesforgeks . org/python-get-硬件和系统-信息-使用-平台-模块/](https://www.geeksforgeeks.org/python-get-hardware-and-system-information-using-platform-module/)

在本文中，我们将了解如何显示系统信息，即处理器名称、系统名称等。

**平台模块**用于检索尽可能多的关于程序当前正在其上执行的平台的信息。现在所说的平台信息，是指关于设备的信息，包括操作系统、节点、操作系统版本、Python 版本等。当您想要检查您的程序是否与安装在特定系统上的 python 版本兼容，或者硬件规格是否满足您的程序要求时，该模块起着至关重要的作用。

为了做到这一点，我们需要导入`platform`模块。

```py
import platform
```

下面是 Python 实现–

```py
# importing module
import platform

# dictionary
info = {}

# platform details
platform_details = platform.platform()

# adding it to dictionary
info["platform details"] = platform_details

# system name
system_name = platform.system()

# adding it to dictionary
info["system name"] = system_name

# processor name
processor_name = platform.processor()

# adding it to dictionary
info["processor name"] = processor_name

# architectural detail
architecture_details = platform.architecture()

# adding it to dictionary
info["architectural detail"] = architecture_details

# printing the details
for i, j in info.items():
    print(i, " - ", j)
```

**输出:**

```py
platform details  -  Windows-10-10.0.17134-SP0
system name  -  Windows
processor name  -  Intel64 Family 6 Model 158 Stepping 10, GenuineIntel
architectural detail  -  ('64bit', 'WindowsPE')

```

**注意:**输出可能会因您的系统架构而异。