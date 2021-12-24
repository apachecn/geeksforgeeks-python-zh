# 使用 Python-tkinter 自动隐藏滚动条

> 原文:[https://www . geesforgeks . org/autohiding-scroll bar-using-python-tkinter/](https://www.geeksforgeeks.org/autohiding-scrollbars-using-python-tkinter/)

在进入主题之前，让我们看看什么是 [Python Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 。因此，我们都知道 Python 在创建图形用户界面时有不同的选项，而 *tkinter* 就是其中之一。是 Python 的标准 *GUI* 库。当 python 与它合并时，它使图形用户界面应用程序的创建变得非常快速和简单。它还为 *Tk* 图形用户界面工具包提供了一个非常有效的面向对象的界面。

**注意:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

#### tkinter 中的小部件

此外，*Tkit*启用许多控件，如标签、文本框、列表框、按钮、滚动条等，这些控件在图形用户界面应用程序中使用。这些控件被称为[小部件](https://www.geeksforgeeks.org/python-gui-tkinter/)。

#### tkinter 的几何管理方法

这些方法用于跨父小部件区域组织小部件。此外，所有 tkinter 小部件都可以访问这些方法。有三种[几何管理方式](https://www.geeksforgeeks.org/python-geometry-method-in-tkinter/)即 *[包()](https://www.geeksforgeeks.org/python-pack-method-in-tkinter/)[格()](https://www.geeksforgeeks.org/python-grid-method-in-tkinter/)[地点()](https://www.geeksforgeeks.org/python-place-method-in-tkinter/)T9】。所有这些方法都有不同的作用。
**现在，让我们讨论一下使用 Python-tkinter 自动隐藏滚动条***的话题。
在本主题中，我们将看到如何使用 Python 中的 tkinter 创建自动隐藏滚动条。所以，首先让我们看看下面自动隐藏滚动条的含义:

#### 自动隐藏滚动条

当一个滚动条在不需要的时候隐藏起来，也就是说，当它不需要的时候是不可见的，这种类型的滚动条被称为*自动隐藏滚动条*。在 Python 中*自动隐藏滚动条*可以与*列表框*和*文本*小部件一起使用。可以借助一些几何管理方法，使用 python tkinter 来实现。
以下示例说明了使用 Python-tkinter :
**自动隐藏滚动条的用法**示例 1:****

```py
# Python program to illustrate the usage of 
# autohiding scrollbars using tkinter

# Importing tkinter
from tkinter import *

# Creating class AutoScrollbar
class AutoScrollbar(Scrollbar):

    # Defining set method with all 
    # its parameter
    def set(self, low, high):

        if float(low) <= 0.0 and float(high) >= 1.0:

            # Using grid_remove
            self.tk.call("grid", "remove", self)
        else:
            self.grid()
        Scrollbar.set(self, low, high)

    # Defining pack method
    def pack(self, **kw):

        # If pack is used it throws an error
        raise (TclError,"pack cannot be used with \
        this widget")

    # Defining place method
    def place(self, **kw):

        # If place is used it throws an error
        raise (TclError, "place cannot be used  with \
        this widget")

# creating tkinter window 
root = Tk()

# Defining vertical scrollbar
verscrollbar = AutoScrollbar(root)

# Calling grid method with all its
# parameter w.r.t vertical scrollbar
verscrollbar.grid(row=0, column=1, 
                  sticky=N+S)

# Defining horizontal scrollbar
horiscrollbar = AutoScrollbar(root, 
                              orient=HORIZONTAL)

# Calling grid method with all its 
# parameter w.r.t horizontal scrollbar
horiscrollbar.grid(row=1, column=0, 
                   sticky=E+W)

# Creating scrolled canvas
canvas = Canvas(root,
                yscrollcommand=verscrollbar.set,
                xscrollcommand=horiscrollbar.set)

canvas.grid(row=0, column=0, sticky=N+S+E+W)

verscrollbar.config(command=canvas.yview)
horiscrollbar.config(command=canvas.xview)

# Making the canvas expandable
root.grid_rowconfigure(0, weight=1)
root.grid_columnconfigure(0, weight=1)

# creating canvas contents
frame = Frame(canvas)
frame.rowconfigure(1, weight=1)
frame.columnconfigure(1, weight=1)

# Defining number of rows and columns
rows = 20
for i in range(1,rows):
    for j in range(1,9):
        button = Button(frame, padx=8, pady=8, 
                        text="[%d,%d]" % (i,j))
        button.grid(row=i, column=j, sticky='news')

# Creating canvas window
canvas.create_window(0, 0, anchor=NW, window=frame)

# Calling update_idletasks method
frame.update_idletasks()

# Configuring canvas
canvas.config(scrollregion=canvas.bbox("all"))

# Calling mainloop method
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-386882-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200319193544/python-auto-hide-scrollbar.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200319193544/python-auto-hide-scrollbar.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200319193544/python-auto-hide-scrollbar.webm)</video>