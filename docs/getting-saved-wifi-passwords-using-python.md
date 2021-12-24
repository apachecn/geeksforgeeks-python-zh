# 使用 Python 获取保存的 Wifi 密码

> 原文:[https://www . geeksforgeeks . org/get-saved-wifi-password-use-python/](https://www.geeksforgeeks.org/getting-saved-wifi-passwords-using-python/)

通常在连接 wifi 时，我们必须输入一些密码才能访问网络，但我们无法直接看到之前输入的密码，即保存的网络密码。在本文中，我们将看到如何使用 python 获取所有保存的 WiFi 名称和密码，为了做到这一点，我们将使用 Python 的子流程模块。
**Wi-Fi** 是一种无线网络技术，允许计算机(笔记本电脑和台式机)、移动设备(智能手机和可穿戴设备)和其他设备(打印机和摄像机)等设备与互联网连接。
Python 中的**子流程**模块(2.x 和 3.x)用于通过创建新流程，通过 Python 代码运行新的应用程序或程序。它还有助于获得输入/输出/错误管道以及各种命令的退出代码。

> **实施步骤:**
> 1。导入子流程模块
> 2。借助 check_output 方法
> 3 获取无线局域网(wifi)的元数据。解码元数据，按照
> 4 行拆分元数据。从解码的元数据中获取保存的 wlan 网络的名称
> 5。现在对于每个名称，根据名称
> 6 再次获取 wlan 的元数据。启动 try and catch block，在 try block 中，解码并分割该元数据，获得给定 wifi 名称的密码
> 7。打印密码和 wifi 名称，如果没有密码则打印空白
> 8。在除了发生过程错误的块中，发生打印编码错误

下面是实现

## 蟒蛇 3

```
# importing subprocess
import subprocess

# getting meta data
meta_data = subprocess.check_output(['netsh', 'wlan', 'show', 'profiles'])

# decoding meta data
data = meta_data.decode('utf-8', errors ="backslashreplace")

# splitting data by line by line
data = data.split('\n')

# creating a list of profiles
profiles = []

# traverse the data
for i in data:

    # find "All User Profile" in each item
    if "All User Profile" in i :

        # if found
        # split the item
        i = i.split(":")

        # item at index 1 will be the wifi name
        i = i[1]

        # formatting the name
        # first and last character is use less
        i = i[1:-1]

        # appending the wifi name in the list
        profiles.append(i)

# printing heading       
print("{:<30}| {:<}".format("Wi-Fi Name", "Password"))
print("----------------------------------------------")

# traversing the profiles       
for i in profiles:

    # try catch block begins
    # try block
    try:
        # getting meta data with password using wifi name
        results = subprocess.check_output(['netsh', 'wlan', 'show', 'profile', i, 'key = clear'])

        # decoding and splitting data line by line
        results = results.decode('utf-8', errors ="backslashreplace")
        results = results.split('\n')

        # finding password from the result list
        results = [b.split(":")[1][1:-1] for b in results if "Key Content" in b]

        # if there is password it will print the pass word
        try:
            print("{:<30}| {:<}".format(i, results[0]))

        # else it will print blank in front of pass word
        except IndexError:
            print("{:<30}| {:<}".format(i, ""))

    # called when this process get failed
    except subprocess.CalledProcessError:
        print("Encoding Error Occured")
```

**输出:**

```
Wi-Fi Name                    | Password
-----------------------------------------------
Engineer                      | ayush123
honor                         | 1234567890
Engineer_5GHz                 | ayush123
Redmi                         | 12345677
Ayush                         | 123123123
BiGX-cmtqaGFtYjc              | rakshit123
UERJTTBV8e0GUmVkbWkg 2        | 987654321
DESKTOP-F32H70N 5009          | SUSHANT@123
UERJTTBV8e0GUmVkbWkg          | 
Bunns                         | heyhotspot
Hogwarts                      | sushant@123
Cgc wireless                  | database1234
Moto G (5) Plus 8691          | rakshit123
AndroidAP                     | udrw7859
AndroidAPab7e                 | 123000123
roshan                        | 12345678
Svj?                          | salonivij
Hey                           | heythere
AndroidAP202                  | bhuvanbroo
JARVIS                        | abhishek09
B6NO-wq5hamF0IGt1bWHCrg       | 12345678
CDAC                          | 
```