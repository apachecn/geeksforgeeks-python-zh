# 如何设置大小不变的 Tkinter 窗口？

> 原文:[https://www . geeksforgeeks . org/如何设置恒定大小的窗口/](https://www.geeksforgeeks.org/how-to-set-a-tkinter-window-with-a-constant-size/)

**先决条件:**

*   [python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
*   [明斯克](https://www.geeksforgeeks.org/minsize-method-in-tkinter-python/)
*   [最大尺寸](https://www.geeksforgeeks.org/maxsize-method-in-tkinter-python/)

这里的任务是生成一个大小不变的 Tkit 窗口。一个大小不变的窗口不能按照用户的方便来调整大小，它严格地保持它的尺寸。另一方面，普通窗口可以调整大小。

**接近**

*   导入模块
*   声明 Tkinter 对象
*   使用 maxsize()和 minsize()函数创建一个固定大小的窗口。

**语法:**

这里，高度和宽度以像素为单位。

```
minsize(height, width)
```

在 Tkit 中，minsize()方法用于设置 Tkit 窗口的最小大小。使用这种方法，用户可以将窗口的初始化大小设置为其最小大小，并且仍然能够最大化和缩放窗口。

```
maxsize(height, width)
```

此方法用于设置根窗口的最大大小。用户仍然可以将窗口的大小缩小到最小。

**程序 1:** 创建正常窗口

## 蟒蛇 3

```
# Import module
from tkinter import *

# Create object
root = Tk()

# Adjust size
root.geometry("400x400")

# Execute tkinter
root.mainloop()
```

**输出:**

![](img/4f4f1781fc990854e5f4409d992e969e.png)

**程序 2** :创建一个大小不变的窗口

## 蟒蛇 3

```
# Import module
from tkinter import *

# Create object
root = Tk()

# Adjust size
root.geometry("400x400")

# set minimum window size value
root.minsize(400, 400)

# set maximum window size value
root.maxsize(400, 400)

# Execute tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-522845-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201203152943/FreeOnlineScreenRecorderProject1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201203152943/FreeOnlineScreenRecorderProject1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201203152943/FreeOnlineScreenRecorderProject1.mp4)</video>