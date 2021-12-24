# 菜单驱动 Python 程序执行 Linux 命令

> 原文:[https://www . geesforgeks . org/menu-driven-python-program-to-execute-Linux-commands/](https://www.geeksforgeeks.org/menu-driven-python-program-to-execute-linux-commands/)

**Linux** 是最受欢迎的操作系统之一，也是开发者的常用选择。然而，很难记住 Linux 支持的大量命令，因此下面演示了一个可以轻松运行这些命令的 Python 程序。

在本文中，我们将讨论一个可以用来运行复杂 Linux 命令的 Python 程序。这个程序是一个下拉菜单，给用户一个选择列表，用户可以继续他/她需要的选项。Python 有一个 [**OS 模块**](https://www.geeksforgeeks.org/os-module-python-examples/) ，可以用来运行或执行 Linux 命令。操作系统模块有助于与操作系统交互。

以下是该计划中实现的功能:

1.  显示当前日期。
2.  显示日历。
3.  配置网站。
4.  正在配置 docker。
5.  添加用户。
6.  删除用户。
7.  正在创建文件。
8.  正在创建文件夹。

## 蟒蛇 3

```py
# importing the module
import os

# sets the text colour to green 
os.system("tput setaf 2")

print("Launching Terminal User Interface")

# sets the text color to red
os.system("tput setaf 1")

print("\t\tWELCOME TO Terminal User Interface\t\t\t")

# sets the text color to white
os.system("tput setaf 7")

print("\t-------------------------------------------------")
print("Entering local device")
while True:
    print("""
        1.Print date
        2.Print cal
        3.Configure web
        4.Configure docker
        5.Add user
        6.Delete user
        7.Create a file
        8.Create a folder
        9.Exit""")

    ch=int(input("Enter your choice: "))

    if(ch == 1):
        os.system("date")

    elif ch == 2:
        os.system("cal")

    elif ch == 3:
        os.system("yum install httpd -y")
        os.system("systemctl start httpd")
        os.system("systemctl status httpd")

    elif ch == 4:
        os.system("yum install docker-ce -y")
        os.system("systemctl start docker")
        os.system("systemctl status docker")

    elif ch == 5:
        new_user=input("Enter the name of new user: ")
        os.system("sudo useradd {}".format(new_user))
        os.system("id -u {}".format(new_user) )   

    elif ch == 6:
        del_user=input("Enter the name of the user to delete: ")
        os.system("sudo userdel {}".format(del_user))

    elif ch == 7:
        filename=input("Enter the filename: ")
        f=os.system("sudo touch {}".format(filename))
        if f!=0:
            print("Some error occurred")
        else:
            print("File created successfully")

    elif ch == 8:
        foldername=input("Enter the foldername: ")
        f=os.system("sudo mkdir {}".format(foldername))
        if f!=0:
            print("Some error occurred")
        else:
            print("Folder created successfully")

    elif ch == 9:
        print("Exiting application")
        exit()
    else:
        print("Invalid entry")

    input("Press enter to continue")
    os.system("clear")
```

**运行应用**
应用必须在 Linux 终端上运行。
运行应用程序的步骤:

1.  从计算机打开根帐户。如果用户无权访问根帐户，则某些根特权命令可能无法正常工作。
2.  打开 Linux 终端
3.  去那个。使用 cd 命令保存 py 文件
4.  运行。py 文件使用 **python3 tui.py** 命令

**输出**T2】

<video class="wp-video-shortcode" id="video-490450-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200924112101/screen-record.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200924112101/screen-record.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200924112101/screen-record.mp4)</video>