# 如何关闭 Tkinter 中的一个窗口？

> 原文:[https://www . geesforgeks . org/如何关闭 tkinter 中的窗口/](https://www.geeksforgeeks.org/how-to-close-a-window-in-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中， *tkinter* 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 与 *tkinter* 是创建图形用户界面应用程序最快最简单的方法。使用 *tkinter* 创建一个图形用户界面是一个简单的任务。

要关闭一个 *tkinter* 窗口，我们可以使用 *destroy()* 方法。*销毁()*是一个通用的小部件方法，也就是说，我们可以在任何可用的小部件以及主 *tkinter* 窗口中使用这个方法。

**示例:**

在下面的例子中，我们将使用一个按钮实现 *destroy()* 方法。

## 计算机编程语言

```py
# import required module 
from tkinter import *

# create object
root = Tk()

# create button to implement destroy()
Button(root, text="Quit", command=root.destroy).pack()

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-523703-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201204152656/Untitled.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201204152656/Untitled.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201204152656/Untitled.mp4)</video>

在上面的例子中，点击按钮*破坏()*方法被调用并且 *tkinter* 窗口被关闭。