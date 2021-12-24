# 如何使用 Python 查找可用的 WiFi 网络？

> 原文:[https://www . geeksforgeeks . org/如何找到可用的 wifi 网络-使用-python/](https://www.geeksforgeeks.org/how-to-find-available-wifi-networks-using-python/)

WiFi (Wireless Fidelity)是一种无线技术，允许计算机(笔记本电脑和台式机)、移动设备(智能手机和可穿戴设备)和其他设备(打印机和摄像机)等设备与互联网接口。借助 Python，我们可以找到 WiFi 名称的名称。我们需要具备网络的基础知识，以帮助我们知道自己需要什么，不需要什么。

### **所需模块**

*   **子流程:**子流程模块允许您产生新的流程，连接到它们的输入/输出/错误管道，并获取它们的返回代码。我们不需要使用 pip 来安装它，因为预装了子流程模块。

对于子流程模块，我们需要使用 **check_output()** 方法。我们将传递一个关于 WiFi 网络我们需要知道的事情的列表。我们将需要网络，无线局域网，表演和网络。传递这些参数是为了将输出存储在其中，然后将其转换为字符串来显示输出。

> **语法:**子进程. check_output(args，* stdin =无，stderr =无，shell=False，universal_newlines=False)
> 
> **参数:**
> 
> *   **参数:**用于启动进程的参数。这可能是一个列表或字符串。
> *   **stdin:** 作为管道(os.pipe())传递的标准输入流的值。
> *   **标准输出:**从标准输出流获得的输出值。
> *   **stderr:** 也称为标准错误，是进程可以写入错误消息的默认文件描述符。基本上是误差值(如果有的话)
> *   **shell:** 是一个布尔参数。如果为真，则通过新的外壳环境执行命令。
> *   **universal_newlines:** 是一个布尔参数。如果为 true，则以通用换行符模式打开包含 stdout 和 stderr 的文件。
> 
> **返回:**关于网络的信息

这是它的代码

## 蟒蛇 3

```py
# importing the subprocess module
import subprocess

# using the check_output() for having the network term retrieval
devices = subprocess.check_output(['netsh','wlan','show','network'])

# decode it to strings
devices = devices.decode('ascii')
device s= devices.replace("\r","")

# displaying the information
print(devices)
```

**输出:**

<video class="wp-video-shortcode" id="video-501346-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201016211715/gfgvedio.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201016211715/gfgvedio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201016211715/gfgvedio.mp4)</video>