# 如何使用 Python 自动实现 VPN 在 Ubuntu 上更改 IP 位置？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 实现 VPN-to-change-IP-location-on-Ubuntu/](https://www.geeksforgeeks.org/how-to-automate-vpn-to-change-ip-location-on-ubuntu-using-python/)

为了防止未经授权的用户访问我们的系统，您可以使用不同组织提供的[虚拟专用网](https://www.geeksforgeeks.org/virtual-private-network-vpn-introduction/)服务来欺骗我们系统的 IP 地址。你可以在你的系统上免费设置一个虚拟专用网络。

在您通过 Ubuntu 系统设置并登录到虚拟专用网后，您需要在一段时间后手动连接到不同的虚拟专用网服务器。我们可以使用 python 自动实现它，这样在一段时间后，我们系统的 IP 地址就会自动改变，这样就没有人能够跟踪我们的系统了。这将使我们的系统得到更好的保护。

#### 使用 Python 实现虚拟专用网自动化的步骤如下:

**第一步:**打开终端(Ctrl+Alt+T)，通过在终端上键入以下命令，使用 *gedit* 创建文件。

```py
gedit gfg.py
```

**第二步:**将 python 的模块导入到打开的文件中。

## 蟒蛇 3

```py
# import required modules
import os
from time import sleep
import random
```

**步骤 3:** 创建 windscripte(VPN)提供的免费 VPN 服务器代码列表。

## 蟒蛇 3

```py
# list of VPN server codes
codeList = ["TR", "US-C", "US", "US-W", "CA", "CA-W",
            "FR", "DE", "NL", "NO", "RO", "CH", "GB", "HK"]
```

**步骤 4:** 使用*操作系统*模块启动试块连接到防风网

```py
os.system("windscribe connect")
```

然后，开始一个无限循环，并在它下面写一些行。

*   使用*随机*模块从*代码列表*中选择一个随机代码。

```py
choiceCode = random.choice(codeList)
```

*   创建 15 到 20 分钟的随机睡眠，之后使用*时间*和*随机*模块更改系统的 IP。

```py
sleep(random.randrange(120,300))
```

*   用随机选择的虚拟专用网码连接。

```py
os.system("windscribe connect "+ choiceCode)
```

## 蟒蛇 3

```py
try:

    # connect to VPN
    os.system("windscribe connect")
    while True:

        # assigning a random VPN server code
        choiceCode = random.choice(codeList)

        # changing IP after a particular time period
        sleep(random.randrange(120, 300))

        # connecting to a different VPN server
        print("!!! Changing the IP Address........")
        os.system("windscribe connect " + choiceCode)
```

**第 5 步:**开始一个捕捉块，然后:

*   断开虚拟专用网，如果它得到任何错误，它将运行。

```py
os.system("windscribe disconnect")
```

*   在此显示断开消息。

```py
print("sorry, some error has occurred..!!")
```

## 蟒蛇 3

```py
except:

    # disconnect VPN
    os.system("windscribe disconnect")
    print("sorry, some error has occurred..!!")
```

#### 以下是基于上述方法的完整代码:

## 蟒蛇 3

```py
# import required modules
import os
from time import sleep
import random

# list of VPN server codes
codeList = ["TR", "US-C", "US", "US-W", "CA", "CA-W",
            "FR", "DE", "NL", "NO", "RO", "CH", "GB", "HK"]

try:

    # connect to VPN
    os.system("windscribe connect")
    while True:

        # assigning a random VPN server code
        choiceCode = random.choice(codeList)

        # changing IP after a particular time period
        sleep(random.randrange(120, 300))

        # connecting to a different VPN server
        print("!!! Changing the IP Address........")
        os.system("windscribe connect " + choiceCode)

except:

    # disconnect VPN
    os.system("windscribe disconnect")
    print("sorry, some error has occurred..!!")
```

**输出:**

<video class="wp-video-shortcode" id="video-517177-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201123235816/How-to-Execute-and-Implement-VPN-cervice-Automation-program-in-python.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201123235816/How-to-Execute-and-Implement-VPN-cervice-Automation-program-in-python.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201123235816/How-to-Execute-and-Implement-VPN-cervice-Automation-program-in-python.mp4)</video>

#### 用 python 执行自动虚拟专用网定位器程序的过程:

**步骤 1:** 使用下面给出的命令登录到您用来在系统上设置[虚拟专用网络的防风网。](https://www.geeksforgeeks.org/how-to-setup-vpn-on-ubuntu-linux-system-for-ip-spoofing-using-windscribe/)

```py
windscribe login
```

**步骤 2:** 使用下面的命令执行您在上述步骤中创建的文件。

```py
python3 gfg.py
```

**注意:**这会随机改变你系统的 IP 地址。按 *Ctrl+c* 关闭 VPN 服务。

点击此处观看小视频，更好地了解 VPN 自动化程序的设置和执行。