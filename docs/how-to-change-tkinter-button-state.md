# 如何改变 Tkinter 按钮状态？

> 原文:[https://www . geesforgeks . org/how-to-change-tkinter-button-state/](https://www.geeksforgeeks.org/how-to-change-tkinter-button-state/)

[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个用于创建 GUI 应用程序的 Python 包。Python 有很多 GUI 框架，但是 Tkinter 是 Python 标准库中唯一内置的框架。Tkinter 有几个优点；它是跨平台的，所以同样的代码可以在 Windows、macOS 和 Linux 上运行。与其他框架相比，Tkinter 是轻量级的，使用起来相对轻松。

在本文中，我们将学习如何更改按钮的状态。

**让我们一步一步来理解:**

**第一步:**首先我们要导入 **Tkinter** 模块和一些我们需要的小部件。

## 蟒蛇 3

```py
# importing tkinter module
# along with some constants and Widgets

from tkinter import Tk
from tkinter.constants import DISABLED, NORMAL
from tkinter.ttk import Button, Label
```

如果您使用的是 **Python2** ，那么将 ***tkinter 改为***tkinter，同样 **tkinter.ttk** 也不起作用，所以从 Tkinter 本身导入小部件。

**第二步:**现在我们要创建一个包含所有按钮和标签的**应用程序类**。

## 蟒蛇 3

```py
# Creating App class which
# will contain our overall App
class App:
    def __init__(self, master) -> None:

        # Instantiating master i.e toplevel Widget
        self.master = master

        # Creating label
        self.label = Label(self.master,
                           text = "Click Button2 to change Button1 State")
        self.label.pack(pady = 10)

        # Creating button1
        # We will change the state of this Button
        # it has a initial state of "NORMAL" 
        # i.e Button can be pressed
        self.button1 = Button(self.master,
                              text = "Button1",
                              state = NORMAL)

        self.button1.pack(pady = 20)

        # Creating another button
        # We will use this button to
        # change the State of first button
        self.button2 = Button(self.master,
                              text = "Button2",
                              command = self.changeState)

        self.button2.pack(pady = 20)
```

**第三步:**从上面的代码中可以看到，我们有一个附加了 Button2 的函数，即 **changeState** 函数接下来我们要实现这个函数。在这个功能中，我们将改变按钮 1 的状态。

## 蟒蛇 3

```py
# Helper function which will change the State of Button1
def changeState(self) -> None:

    # Printing the State of 
    # the Button before ALTERING it
    # This is optional
    print(self.button1['state'])

    # Checking if the STATE of the Button1

    # If the STATE is NORMAL
    if (self.button1['state'] == NORMAL):

        # Change the state to DISABLED
        self.button1['state'] = DISABLED
    else:

        # Otherwise, change the state to NORMAL
        self.button1['state'] = NORMAL
```

**第 4 步:**在这一步中，我们将创建运行该应用程序的主函数。在主功能中，我们将设置应用程序标题和几何图形，并实例化我们的应用程序类。

## 蟒蛇 3

```py
if __name__ == "__main__":

    # Instantiating top level
    root = Tk()

    # Setting the title of the window
    root.title("Button State App")

    # Setting the geometry i.e Dimensions
    root.geometry("400x250")

    # Calling our App
    app = App(root)

    # Mainloop which will cause
    # this toplevel to run infinitely
    root.mainloop()
```

**以下是完整实现:**

## 蟒蛇 3

```py
# importing tkinter module
# along with some constants and Widgets
from tkinter import Tk
from tkinter.constants import DISABLED, NORMAL
from tkinter.ttk import Button, Label

# Creating App class
# which will contain our overall App
class App:
    def __init__(self, master) -> None:

        # Instantiating master 
        # i.e toplevel Widget
        self.master = master

        # Creating label
        self.label = Label(self.master,
                           text="Click Button2 to change Button1 State")

        self.label.pack(pady = 10)

        # Creating button1
        # We will change the state of this Button
        # it has a initial state of 
        # "NORMAL" i.e Button can be pressed
        self.button1 = Button(self.master, 
                              text = "Button1", 
                              state = NORMAL)

        self.button1.pack(pady = 20)

        # Creating another button
        # We will use this button
        # to change the State of first button
        self.button2 = Button(self.master,
                              text = "Button2",
                              command = self.changeState)

        self.button2.pack(pady = 20)

    # Helper function which will 
    # change the State of Button1
    def changeState(self) -> None:

        # Printing the State of 
        # the Button before ALTERING it
        # This is optional
        print(self.button1['state'])

        # Checking if the STATE of the Button1
        # If the STATE is NORMAL
        if (self.button1['state'] == NORMAL):

            # Change the state to DISABLED
            self.button1['state'] = DISABLED
        else:

            # Otherwise, change the state to NORMAL
            self.button1['state'] = NORMAL

if __name__ == "__main__":

    # Instantiating top level
    root = Tk()

    # Setting the title of the window
    root.title("Button State App")

    # Setting the geometry i.e Dimensions
    root.geometry("400x250")

    # Calling our App
    app = App(root)

    # Mainloop which will cause this toplevel
    # to run infinitely
    root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-527989-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201214194106/ice_video_20201214-191750.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201214194106/ice_video_20201214-191750.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201214194106/ice_video_20201214-191750.mp4)</video>