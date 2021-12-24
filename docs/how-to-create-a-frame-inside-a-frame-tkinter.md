# 如何在框架 tkinter 内部创建框架？

> 原文:[https://www . geesforgeks . org/如何创建框架内框架-tkinter/](https://www.geeksforgeeks.org/how-to-create-a-frame-inside-a-frame-tkinter/)

**先决条件:**[Tkit](https://www.geeksforgeeks.org/python-gui-tkinter/)

使用 Tkinter 创建一个基本框架是非常容易的，本文重点介绍如何在其中创建另一个框架。为了创建一个基本框架，父窗口的名称作为 frame()函数的第一个参数给出。因此，要在此框架内添加另一个框架，只需将第一个框架的名称作为父窗口提供给第二个框架。

相对于父窗口给出可选值，如框架填充。我们可以使用相同的方法，通过将前一帧作为当前帧的父帧，以这种方式添加多个帧。

**进场:**

*   创建正常 Tkinter 窗口
*   正常创建第一帧
*   创建第二帧
*   将第一个窗口作为其父窗口
*   执行代码

[frame()](https://www.geeksforgeeks.org/python-tkinter-frame-widget/) 是一个内置的 Tkinter 方法，有助于实现我们所需的功能。

> **语法:**帧(主)
> 
> **参数:**
> 
> *   **主**:父窗口
> *   **highlightcolor** :设置小部件需要对焦时的对焦高亮颜色。
> *   **bd** :以像素为单位设置边框宽度。
> *   **bg** :设置正常背景颜色。
> *   **光标**:设置使用的光标。
> *   **宽度**:设置小部件的宽度。
> *   **高度**:设置小部件的高度。

**程序:**

## 蟒蛇 3

```py
# Import Module
from tkinter import *

# Create Tkinter Object
root = Tk()

# Set Geometry
root.geometry("400x400")

# Frame 1
frame1 = Frame(root,bg="black",width=500,height=300)
frame1.pack()

# Frame 2
frame2 = Frame(frame1,bg="white",width=100,height=100)
frame2.pack(pady=20,padx=20)

# Execute Tkinter
root.mainloop()
```

**输出:**

![](img/f2259a391eab51fed089de1bf90f707c.png)