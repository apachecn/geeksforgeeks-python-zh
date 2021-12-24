# 如何隐藏、恢复和删除 Tkinter 小部件？

> 原文:[https://www . geesforgeks . org/how-hide-recover-and-delete-tkinter-widgets/](https://www.geeksforgeeks.org/how-to-hide-recover-and-delete-tkinter-widgets/)

[**Tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个用于创建 GUI(图形用户界面)应用程序的 Python 包。**Tkit**为我们提供了各种常见的图形用户界面元素，我们可以使用它们来构建界面，例如按钮、标签、框架、消息、菜单、以及各种输入字段和显示区域。我们称这些元素为小部件。

[**小部件**](https://www.geeksforgeeks.org/what-are-widgets-in-tkinter/) 是图形用户界面的一个元素，它说明信息，以便用户可以与操作系统交互。在 Tkinter 中，Widgets 是对象；表示按钮、框架等的类的实例。

在本文中，我们将演示如何通过使用小部件的各种元素(如按钮、标签、框架等)来隐藏、恢复和删除 Tkinter 小部件。

我们可以通过调用 pack _ 忘我()方法来隐藏 Tkit 小部件，使小部件不可见。我们需要再次调用 pack()方法来打包小部件，使其可见，或者恢复它。我们还可以通过调用本节中的 destroy()方法来永久删除 Tkinter 小部件。

**示例 1:** 使用 [**遗忘 _pack(**](https://www.geeksforgeeks.org/python-forget_pack-and-forget_grid-method-in-tkinter/) **)** 和 [**pack()**](https://www.geeksforgeeks.org/python-pack-method-in-tkinter/) 方法隐藏和恢复 Tkinter 中的按钮。

**语法:**

```py
widget.forget_pack()
```

小部件可以是任何可见的有效小部件。

## 蟒蛇 3

```py
# Imports tkinter
from tkinter import *

# toplevel window
root = Tk()

# Method to make Button(Widget) invisible from toplevel

def hide_button(widget):
    # This will remove the widget from toplevel
    widget.pack_forget()

# Method to make Button(widget) visible
def show_button(widget):
    # This will recover the widget from toplevel
    widget.pack()

# Button widgets
B1 = Button(root, text="Button 1")
B1.pack()

# See, in command hide_button() function is passed to hide Button B1
B2 = Button(root, text="Button 2", command=lambda: hide_button(B1))
B2.pack()

# In command show_button() function is passed to recover Button B1
B3 = Button(root, text="Button 3", command=lambda: show_button(B1))
B3.pack()

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-523868-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201210155344/op1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201210155344/op1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201210155344/op1.mp4)</video>

**示例 2:** 使用遗忘 _pack()和 pack()方法隐藏和恢复 Tkinter 中的标签。**T3】**

## 蟒蛇 3

```py
# Imports tkinter
from tkinter import *

# toplevel window
root = Tk()

# label widget
label = Label(root, text="LABEL")

# Method to make Label(Widget) invisible
def hide_label():
    # This will remove the widget
    label.pack_forget()

# Method to make Label(widget) visible
def recover_label():
    # This will recover the widget
    label.pack()

# hide_label() function hide the label temporarily
B2 = Button(root, text="Click To Hide label", fg="red", command=hide_label)
B2.pack()

# recover_label() function recover the label
B1 = Button(root, text="Click To Show label",
            fg="green", command=recover_label)
B1.pack()

# pack Label widget
label.pack()

# Start the GUI
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-523868-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201210155552/op2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201210155552/op2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201210155552/op2.mp4)</video>

**示例 3:** 通过调用 [**销毁()**方法](https://www.geeksforgeeks.org/destroy-method-in-tkinter-python/#:~:text=destroy()%20is%20a%20universal,with%20the%20main%20tkinter%20window.&text=This%20method%20can%20be%20used%20with%20after()%20method.)永久删除 Tkinter 小部件。我们可以在任何可用的小部件以及主 tkinter 窗口中使用这个方法。

## 蟒蛇 3

```py
from tkinter import *

# toplevel window
root = Tk()

# label widget
mylabel = Label(root, text="GeeksforGeeks")
mylabel.pack()

# delete_label() function  to delete Label(Widget) permanently

def delete_label():
    mylabel.destroy()

# Creating button. In this destroy method is passed
# as command, so as soon as button is pressed
# Label will be destroyed
B1 = Button(root, text="DELETE", command=delete_label)
B1.pack()

# start the GUI
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-523868-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201210155646/op3.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20201210155646/op3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201210155646/op3.mp4)</video>