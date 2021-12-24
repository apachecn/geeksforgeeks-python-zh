# 使用 Python-Tkinter 创建第一个图形用户界面应用程序

> 原文:[https://www . geesforgeks . org/create-first-GUI-application-use-python-tkinter/](https://www.geeksforgeeks.org/create-first-gui-application-using-python-tkinter/)

[**【Tkinter】**](https://www.geeksforgeeks.org/python-gui-tkinter/)**是一个用于创建 GUI 应用的 Python 包。Python 有很多 GUI 框架，但是 Tkinter 是 Python 标准库中唯一内置的框架。Tkinter 有几个优点；它是跨平台的，所以同样的代码可以在 Windows、macOS 和 Linux 上运行。与其他框架相比，Tkinter 是轻量级的，使用起来相对轻松。这使得它成为用 Python 构建图形用户界面应用程序的一个引人注目的选择，尤其是对于那些不需要现代光芒的应用程序，并且当务之急是快速构建功能性和跨平台的东西。**

**为了更好地理解 Tkinter，我们将创建一个简单的 GUI。**

## **入门指南**

****1。**导入 tkinter 包及其所有模块。
T3】2。创建根窗口。给根窗口一个标题(使用**标题()**)和尺寸(使用**几何()**)。所有其他小部件都将在根窗口中。
**3。**使用**主循环()**调用窗口的循环。如果您忘记调用此函数，用户将看不到任何内容。该窗口将等待任何用户交互，直到我们关闭它。**

****示例:****

## **蟒蛇 3**

```py
# Import Module
from tkinter import *

# create root window
root = Tk()

# root window title and dimension
root.title("Welcome to GeekForGeeks")
# Set geometry (widthxheight)
root.geometry('350x200')

# all widgets will be here
# Execute Tkinter
root.mainloop()
```

****输出:**** 

**![](img/75d84afcd457f0dd873284e62b404265.png)

根窗口** 

****4。**我们将使用标签类添加标签，并根据需要更改其文本配置。**网格()**功能是一个几何管理器，它将标签保持在窗口内的所需位置。如果默认情况下没有提到任何参数，它将把它放在空单元格中；这是 0，0，因为这是第一个位置。** 

****示例:****

## **蟒蛇 3**

```py
# Import Module
from tkinter import *

# create root window
root = Tk()

# root window title and dimension
root.title("Welcome to GeekForGeeks")
# Set geometry(widthxheight)
root.geometry('350x200')

#adding a label to the root window
lbl = Label(root, text = "Are you a Geek?")
lbl.grid()

# Execute Tkinter
root.mainloop()
```