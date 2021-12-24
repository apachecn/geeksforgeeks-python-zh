# 如何更改 Tkinter OptionMenu 小部件的背景颜色？

> 原文:[https://www . geesforgeks . org/how-change-background-color-of-tkinter-options menu-widget/](https://www.geeksforgeeks.org/how-to-change-background-color-of-tkinter-optionmenu-widget/)

**先决条件** : [Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

创建图形用户界面应用程序时，会出现各种情况，您需要在各种可用选项中进行选择。为了做出这样的选择，引入了选项菜单小部件。在本文中，我们将讨论更改 Tkinter 的选项菜单小部件的菜单背景颜色的过程。

为了实现我们所需的功能，首先设置一个常规的选项菜单，然后使用 config()方法添加和更改颜色。

#### 语法:

> w = OptionMenu(app、#Options Menu widget name、# option 1、#Option2、#Option3)
> 
> 配置(bg = " #选项菜单的背景颜色"，fg = " #文本颜色")

### 使用的功能

*   OptionMenu()用于创建下拉菜单

> ***语法:***
> 
> *选项菜单(master，options)*
> 
> ***参数:***
> 
> *   ***主:**此参数用于表示父窗口。*
> *   ***选项:**包含菜单值*

*   config()用于设置颜色变化

### 方法

*   导入模块
*   现在，使用 tkinter 创建一个 GUI 应用程序
*   接下来，给应用一个标题(可选)。
*   然后，创建一个选项菜单小部件。
*   此外，创建选项菜单小部件的显示选项。
*   此外，设置菜单背景颜色。
*   指定选项菜单未打开时要显示的文本
*   设置显示选项的背景颜色。
*   在图形用户界面中显示选项菜单小部件
*   最后，循环在屏幕上显示图形用户界面应用程序

**程序:**

## 计算机编程语言

```py
# Python program to change menu background
# color of Tkinter's Option Menu

# Import the library tkinter
from tkinter import *

# Create a GUI app
app = Tk()

# Give title to your GUI app
app.title("Vinayak App")

# Construct the label in your app
l1 = Label(app, text="Choose the the week day here")

# Display the label l1
l1.grid()

# Construct the Options Menu widget in your app
text1 = StringVar()

# Set the value you wish to see by default
text1.set("Choose here")

# Create options from the Option Menu
w = OptionMenu(app, text1, "Sunday", "Monday", "Tuesday",
               "Wednesday", "Thursday", "Friday", "Saturday")

# Se the background color of Options Menu to green
w.config(bg="GREEN", fg="WHITE")

# Set the background color of Displayed Options to Red
w["menu"].config(bg="RED")

# Display the Options Menu
w.grid(pady=20)

# Make the loop for displaying app
app.mainloop()
```

**输出:**

![](img/8d25f2c4a5dc4b791ae530772b8c8abe.png)