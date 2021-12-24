# 打开所需软件应用的菜单驱动 Python 程序

> 原文:[https://www . geesforgeks . org/menu-driven-python-program-for-open-required-software-application/](https://www.geeksforgeeks.org/menu-driven-python-program-for-opening-the-required-software-applictaion/)

在本文中，我们将创建一个菜单驱动的 Python 程序，当用户以文本形式输入时，该程序将执行所需的用户工具。

我们可以通过 **GUI(图形用户界面)**和 **CLI(命令行界面)**与 OS 进行交互。我们也可以通过编程语言给操作系统下达指令。在这个程序中，您可以使用 Python 向操作系统发出指令。这个程序给出了我们如何制作一个基于规则的聊天机器人的想法。

在本程序中，我们将使用[**OS . system()**](https://www.geeksforgeeks.org/python-os-system-method/)**方法的[**OS 模块**](https://www.geeksforgeeks.org/os-module-python-examples/) **。**此方法在子外壳中执行命令(字符串)。**

> ****语法:** os.system(命令)**
> 
> ****Return :** 在 Unix 上，返回值是进程的退出状态，在 Windows 上，返回值是系统 shell 运行命令后返回的值。**

**让我们看看实现:**

## **蟒蛇 3**

```py
# import os library
import os

# infinite while loop
while True:
    print("Hello! user choose your tool")
    print("Choose your tool :-\n")
    print("-> mousepad")
    print("-> chrome")
    print("-> vlc")
    print("-> virtualbox")
    print("-> camera")
    print("-> telegram")
    print("-> firefox")
    print("-> codeblocks")
    print("-> screenshot")
    print("-> task-manager")
    print("-> libreoffice impress / presentation")
    print("-> libreoffice writer / text editor / notepad")
    print("-> libreoffice clac / spreadsheets")
    print("-> libreoffice")
    print("-> jupyter notebook\n")
    print("chat with system:-",end=' ')

    # take input from user
    p = input()

    # check conditions
    if (("do not" in p) or ("dont" in p) or ("don't" in p)):
        print("OK user\n")

    elif (("open" in p) or ("start" in p) or ("run" in p) or ("execute" in p) or ("launch" in p) or ("activate" in p)):

        if (("mousepad" in p) or ("editor" in p)):

            # run mention application
            os.system("mousepad")

        elif (("vlc" in p) or ("media player" in p)):
            os.system("vlc")

        elif (("virtualbox" in p) or ("virtual machine" in p) or ("virtual tool" in p)):
            os.system("virtualbox")

        elif (("camera" in p) or ("cheese" in p)):
            os.system("cheese")

        elif ("telegram" in p):
            os.system("telegram-desktop")

        elif ("codeblocks" in p):
            os.system("codeblocks")

        elif ("taskmanager" in p):
            os.system("xfce4-taskmanager")

        elif ("screenshot" in p):
            os.system("xfce4-screenshooter")

        elif (("jupyter" in p) or ("notebook" in p)):
            os.system("jupyter notebook")

        elif (("libreoffice impress" in p) or ("presentation tool" in p)):
            os.system("libreoffice --impress")

        elif (("libreoffice writer" in p) or ("text editor" in p)):
            os.system("libreoffice --writer")

        elif ("notepad" in p):
            os.system("notepad")

        elif (("libreoffice calc" in p) or ("spreadsheet" in p)):
            os.system("libreoffice --calc")

        elif ("libreoffice" in p):
            os.system("libreoffice")

        elif ("chrome" in p):
            os.system("google-chrome-stable")

        elif (("firefox" in p) or ("mozilla" in p)):
            os.system("firefox")

        else :
            print("don't support")

    # terminating infinite while loop
    elif (("quit" in p) or ("exit" in p) or ("stop" in p) or ("close" in p) or ("deactivate" in p) or ("terminate" in p)):
        print("Thnank You!")
        break

    else :
        print("don't support")
```

****输出:****

**<video class="wp-video-shortcode" id="video-476732-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200828202850/testing-geeks.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200828202850/testing-geeks.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200828202850/testing-geeks.mp4)</video>**