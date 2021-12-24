# 在 Tkinter-Python 中隐藏和取消隐藏窗口

> 原文:[https://www . geesforgeks . org/hide-and-unhide-the-window-in-tkinter-python/](https://www.geeksforgeeks.org/hide-and-unhide-the-window-in-tkinter-python/)

**先决条件:**[Tkit](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。使用 Tkinter 创建图形用户界面是一项简单的任务。

在本文中，我们将讨论如何使用 Python 在 Tkinter 中隐藏和取消隐藏窗口。

**使用的功能:**

*   Toplevel()用于启动第二个窗口

**语法:**

> toplevel = Toplevel(根，bg，fg，bd，高度，宽度，字体，..)

*   deiconify()用于显示或取消显示窗口

**语法:**

> 神化()

*   return()用于隐藏窗口

**语法:**

> 撤回()

**进场:**

*   导入模块
*   创建普通窗口
*   添加按钮以执行隐藏和取消隐藏操作
*   现在再创建一个窗口
*   执行代码

**程序:**

## 蟒蛇 3

```py
# Import Library
from tkinter import *

# Create Object
root = Tk()

# Set title
root.title("Main Window")

# Set Geometry
root.geometry("200x200")

# Open New Window
def launch():
    global second
    second = Toplevel()
    second.title("Child Window")
    second.geometry("400x400")

# Show the window
def show():
    second.deiconify()

# Hide the window
def hide():
    second.withdraw()

# Add Buttons
Button(root, text="launch Window", command=launch).pack(pady=10)
Button(root, text="Show", command=show).pack(pady=10)
Button(root, text="Hide", command=hide).pack(pady=10)

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-559925-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210216101555/FreeOnlineScreenRecorderProject1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210216101555/FreeOnlineScreenRecorderProject1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210216101555/FreeOnlineScreenRecorderProject1.mp4)</video>