# 如何移动 Tkinter 按钮？

> 原文:[https://www.geeksforgeeks.org/how-to-move-a-tkinter-button/](https://www.geeksforgeeks.org/how-to-move-a-tkinter-button/)

**先决条件:** [在 tkinter](https://www.geeksforgeeks.org/python-creating-a-button-in-tkinter/) 中创建按钮

**Tkinter** 是 Python 中开发 GUI(图形用户界面)最常用的库。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。由于 Tk 和 Tkinter 在大多数 Unix 平台和 Windows 系统上都可用，因此使用 Tkinter 开发 GUI 应用程序变得最快和最简单。

这个模块没有内置 Python。要安装此模块，请在终端中键入以下 pip 命令。

```py
pip install tkintertable
```

**方法:**

*   Import tkinter module # Tkinter in Python 2.x (note capital t).
*   Create the main window (root = Tk ()).
*   Add a button to the window.
*   Place the button.

Tkinter 模块中的按钮可以通过两种方式放置或移动到任意位置:

*   Use the place method.
*   I used the method of dressing again.

**方法一:使用放置法**

此方法用于将按钮放置在绝对定义的位置。

> **语法:** button1.place(x=some_value，y=some_value)
> 
> **参数:**
> 
> *   **X:** It defines the X coordinate of the button position.
> *   **Y:** Defines the Y coordinate of the button position.

下面是上面所示方法的实现:

## python 3

T5

```py
# Importing tkinter module
from tkinter import *       

# Creating a tkinter window
root = Tk()

# Initialize tkinter window with dimensions 300 x 250            
root.geometry('300x250')    

# Creating a Button
btn = Button(root, text = 'Click me !', command = root.destroy)

# Set the position of button to coordinate (100, 20)
btn.place(x=100, y=20)

root.mainloop()
```