# 如何在 Tkinter Python 中使用 Thread

> 原文:[https://www . geeksforgeeks . org/如何使用 tkinter-python 中的线程/](https://www.geeksforgeeks.org/how-to-use-thread-in-tkinter-python/)

**先决条件:**

*   [**Python GUI–tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/)
*   [**多线程**](https://www.geeksforgeeks.org/multithreading-python-set-1/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 和 tkinter 是创建图形用户界面应用程序最快最简单的方法。使用 tkinter 创建图形用户界面是一项简单的任务。

创建图形用户界面时，需要在后端进行多项工作/操作。假设我们想同时执行 4 个操作。这里的问题是，每个操作都是逐个执行的。在一个操作的执行过程中，图形用户界面窗口也不会移动，这就是为什么我们需要线程。下面给出了两种实现，这显然有助于更好地理解它们的区别。

### 没有线程

在没有线程的情况下工作，会使进程延迟。此外，在完全执行之前，窗口不会移动。

**接近**

*   创建正常 Tkinter 窗口
*   带命令的添加按钮
*   运行 Tkinter

**程序:**

## 蟒蛇 3

```
# Import Module
from tkinter import *
import time
from threading import *

# Create Object
root = Tk()

# Set geometry
root.geometry("400x400")

def work():

    print("sleep time start")

    for i in range(10):
        print(i)
        time.sleep(1)

    print("sleep time stop")

# Create Button
Button(root, text="Click Me", command=work).pack()

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-527669-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201213175002/FreeOnlineScreenRecorderProject6.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201213175002/FreeOnlineScreenRecorderProject6.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201213175002/FreeOnlineScreenRecorderProject6.mp4)</video>

### 带螺纹

**接近**

*   创建正常 Tkinter 窗口
*   带线程命令的添加按钮
*   运行 Tkinter

**程序:**

## 蟒蛇 3

```
# Import Module
from tkinter import *
import time
from threading import *

# Create Object
root = Tk()

# Set geometry
root.geometry("400x400")

# use threading

def threading():
    # Call work function
    t1=Thread(target=work)
    t1.start()

# work function
def work():

    print("sleep time start")

    for i in range(10):
        print(i)
        time.sleep(1)

    print("sleep time stop")

# Create Button
Button(root,text="Click Me",command = threading).pack()

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-527669-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201213175614/FreeOnlineScreenRecorderProject7.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201213175614/FreeOnlineScreenRecorderProject7.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201213175614/FreeOnlineScreenRecorderProject7.mp4)</video>