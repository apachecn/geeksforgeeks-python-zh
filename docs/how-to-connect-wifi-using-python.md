# 如何使用 Python 连接 WiFi？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 连接 wifi/](https://www.geeksforgeeks.org/how-to-connect-wifi-using-python/)

今天看到一台电脑没有活跃的互联网连接几乎是不可能的。互联网在 21 世纪至关重要。有多种方法可以将他们的机器连接到互联网。第一种是传统电缆，即以太网，另一种是现代无线保真系统，即我们都知道的无线保真。无线网络让我们所有人的生活变得更轻松、更快捷。只需轻触拇指或点击鼠标，我们几乎瞬间就能连接到无限的信息和资源海洋。在本文中，我们将使用高级现代编程语言(如 Python)来完成同样的任务

## 连接到已知的无线网络

在这里，我们将连接到以前连接的 WiFi 网络。

**进场:**

该计划的方法很简单:

*   导入必要的 ***库*** 。
*   借助 ***cmd 命令*** 和名为 ***os*** 的 python 库显示所有可用的 SSIDs。
*   ***选择*** 你想连接的已知 Wi-Fi。
*   等待其 ***连接成功*** 。

现在，让我们开始编码。我们将使用几个 ***窗口命令提示符*** 命令来访问可用的无线网络列表，并连接到之前连接的**网络。但是，我们如何在 Python 脚本中编写和执行窗口命令提示符命令呢？嗯…**

*****os*** 库帮助我们通过 python 直接与操作系统进行通信，有 ***path()、getcwd()、system()、*** 等几种方法。我们甚至可以使用 os 功能运行 ***CMD*** 命令。**

****实施:****

## **蟒蛇 3**

```py
# import module
import os

# scan available Wifi networks
os.system('cmd /c "netsh wlan show networks"')

# input Wifi name
name_of_router = input('Enter Name/SSID of the Wifi Network you wish to connect to: ')

# connect to the given wifi network
os.system(f'''cmd /c "netsh wlan connect name={name_of_router}"''')

print("If you're not yet connected, try connecting to a previously connected SSID again!")
```

 ****输出:****

**![](img/2b91a3eb7b9c0391a3abde09dd5dcfcb.png)**

****说明:****

**这里，首先，我们使用 ***导入*** 关键字获取操作系统库。然后，我们使用来自 ***os*** 库的 system()方法来帮助我们运行 cmd 命令**

```py
'cmd /c "netsh wlan show networks"' 
```

**上面的命令 ***扫描所有可用的 ssid***，并将它们与它们的基础架构、身份验证和加密类型一起显示为输出。我们接下来输入 SSID 的字符串，用户希望将其连接并保存在名为 ***name_of_router*** 的变量中。**

**然后，这个字符串变量被替换为另一个 cmd 命令，我们应该在这个命令中输入 SSID 的名称。**

```py
f'''cmd /c "netsh wlan connect name={name_of_router}"''' 
```

**我们现在将成功连接到特定的 SSID。**

## **连接到新的无线网络** 

**现在，连接到一个新的无线网络需要更多的步骤。要连接到新网络，我们必须首先使用将此新的无线网络配置文件添加到我们的系统中。XML 文件。这使得无线网络成为一个已知的 SSID，我们现在可以使用上面的步骤成功地连接到它。**

****进场:****

*   **第一步:导入 ***操作系统*** 库**
*   **第二步:设置新的无线网络的 ***XML 配置*****
*   **第三步: ***选择*** 无线网络**
*   **第四步:将这个 ***档案*** 添加到你的系统中**
*   **第五步: ***将*** 连接到无线网络**

****实施:****

## **蟒蛇 3**

```py
# import module
import os

# function to establish a new connection
def createNewConnection(name, SSID, password):
    config = """<?xml version=\"1.0\"?>
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
    <name>"""+name+"""</name>
    <SSIDConfig>
        <SSID>
            <name>"""+SSID+"""</name>
        </SSID>
    </SSIDConfig>
    <connectionType>ESS</connectionType>
    <connectionMode>auto</connectionMode>
    <MSM>
        <security>
            <authEncryption>
                <authentication>WPA2PSK</authentication>
                <encryption>AES</encryption>
                <useOneX>false</useOneX>
            </authEncryption>
            <sharedKey>
                <keyType>passPhrase</keyType>
                <protected>false</protected>
                <keyMaterial>"""+password+"""</keyMaterial>
            </sharedKey>
        </security>
    </MSM>
</WLANProfile>"""
    command = "netsh wlan add profile filename=\""+name+".xml\""+" interface=Wi-Fi"
    with open(name+".xml", 'w') as file:
        file.write(config)
    os.system(command)

# function to connect to a network   
def connect(name, SSID):
    command = "netsh wlan connect name=\""+name+"\" ssid=\""+SSID+"\" interface=Wi-Fi"
    os.system(command)

# function to display avavilabe Wifi networks   
def displayAvailableNetworks():
    command = "netsh wlan show networks interface=Wi-Fi"
    os.system(command)

# display available netwroks
displayAvailableNetworks()

# input wifi name and password
name = input("Name of Wi-Fi: ")
password = input("Password: ")

# establish new connection
createNewConnection(name, name, password)

# connect to the wifi network
connect(name, name)
print("If you aren't connected to this network, try connecting with the correct password!")
```

****输出:****

**![](img/e1cfb266f1ba469b36caa320297f4ea5.png)**

****说明:****

**首先，我们定义***createnew connection***函数，该函数采用参数名称、SSID 和密码，这些都是我们用来完成配置变量的字符串。配置变量是一个字符串，帮助我们为新的无线网络定义 ***XML*** 配置。**

**然后，我们从用户处获取输入的 ***SSID 名称和密码*** 。然后将它们输入到 XML 代码中，然后使用以下代码行将其作为概要文件添加:**

```py
command = "netsh wlan add profile filename=\""+name+".xml\""+" interface=Wi-Fi"
    with open(name+".xml", 'w') as file:
        file.write(config)
    os.system(command)
```

**我们现在可以使用本文前面使用的相同命令连接到无线网络，并像连接已知网络一样连接到网络。**