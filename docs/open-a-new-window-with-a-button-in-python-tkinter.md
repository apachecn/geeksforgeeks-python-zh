# 用 Python-Tkinter 中的按钮打开一个新窗口

> 原文:[https://www . geesforgeks . org/open-a-new-window-with-in-python-tkinter/](https://www.geeksforgeeks.org/open-a-new-window-with-a-button-in-python-tkinter/)

Python 提供了各种图形用户界面，如 PyQt、Tkinter、Kivy 等。其中，tkinter 是 Python 中最常用的图形用户界面模块，因为它既简单又易于学习和实现。Tkinter 这个词来自 tk 接口。tkinter 模块在 Python 标准库中可用。
**注:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

#### 装置

对于 **Ubuntu** ，您必须通过编写以下命令来安装 tkinter 模块:

> sudo apt-get 安装 python-tk

当 Tkinter 程序运行时，它运行一个主循环(一个无限循环)，负责运行一个图形用户界面程序。一次只能有一个 mainloop 实例处于活动状态，因此为了打开一个新窗口，我们必须使用一个小部件 **Toplevel** 。
一个**顶层**小部件的工作原理很像一个**框架**，但是它在一个单独的顶层窗口中打开，这样的窗口具有主窗口(根/主窗口)应该具有的所有属性。
要用按钮打开新窗口，我们将使用**事件**。
**例 1:**

## 蟒蛇 3

```
# This will import all the widgets
# and modules which are available in
# tkinter and ttk module
from tkinter import *
from tkinter.ttk import *

# creates a Tk() object
master = Tk()

# sets the geometry of main
# root window
master.geometry("200x200")

# function to open a new window
# on a button click
def openNewWindow():

    # Toplevel object which will
    # be treated as a new window
    newWindow = Toplevel(master)

    # sets the title of the
    # Toplevel widget
    newWindow.title("New Window")

    # sets the geometry of toplevel
    newWindow.geometry("200x200")

    # A Label widget to show in toplevel
    Label(newWindow,
          text ="This is a new window").pack()

label = Label(master,
              text ="This is the main window")

label.pack(pady = 10)

# a button widget which will open a
# new window on button click
btn = Button(master,
             text ="Click to open a new window",
             command = openNewWindow)
btn.pack(pady = 10)

# mainloop, runs infinitely
mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-386357-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200311201113/ice_video_20200311-200729_edit_0.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200311201113/ice_video_20200311-200729_edit_0.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200311201113/ice_video_20200311-200729_edit_0.mp4)</video>

**示例 2:** 这将是一种基于类的方法，在这种方法中，我们将创建一个类，该类将派生 toplevel 小部件类，并将表现得像一个 Toplevel。当您想要向现有的顶级小部件类添加一些其他属性时，此方法将非常有用。
这个类的每个对象都将是一个顶级小部件。我们还将使用 **bind()方法注册点击事件**。

## 蟒蛇 3

```
# This will import all the widgets
# and modules which are available in
# tkinter and ttk module
from tkinter import *
from tkinter.ttk import *

class NewWindow(Toplevel):

    def __init__(self, master = None):

        super().__init__(master = master)
        self.title("New Window")
        self.geometry("200x200")
        label = Label(self, text ="This is a new Window")
        label.pack()

# creates a Tk() object
master = Tk()

# sets the geometry of
# main root window
master.geometry("200x200")

label = Label(master, text ="This is the main window")
label.pack(side = TOP, pady = 10)

# a button widget which will
# open a new window on button click
btn = Button(master,
             text ="Click to open a new window")

# Following line will bind click event
# On any click left / right button
# of mouse a new window will be opened
btn.bind("<Button>",
         lambda e: NewWindow(master))

btn.pack(pady = 10)

# mainloop, runs infinitely
mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-386357-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200311203730/ice_video_20200311-203512_edit_0.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200311203730/ice_video_20200311-203512_edit_0.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200311203730/ice_video_20200311-203512_edit_0.mp4)</video>