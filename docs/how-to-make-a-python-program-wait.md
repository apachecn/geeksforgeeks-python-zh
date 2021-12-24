# 如何让 Python 程序等待？

> 原文:[https://www . geesforgeks . org/如何制作 python 程序-等待/](https://www.geeksforgeeks.org/how-to-make-a-python-program-wait/)

**先决条件:**

*   [时间模块](https://www.geeksforgeeks.org/time-functions-in-python-set-1-time-ctime-sleep/)
*   [键盘模块](https://www.geeksforgeeks.org/keyboard-module-in-python/)
*   [操作系统模块](https://www.geeksforgeeks.org/os-module-python-examples/)

一些需求要求 Python 程序在继续之前等待。我们可能需要完成另一个功能或加载一个文件来给用户更好的体验。下面讨论的是实现这一点的一些方法。

## 不同的方法和途径

### 1.Python 时间模块

**1(A)一般睡眠功能**

Python 有一个名为*时间**的模块。*** 这个模块给出了几个有用的功能来控制与时间相关的任务。sleep()就是这样一个函数，它在给定的秒数内暂停调用线程的执行，并返回 void。该参数可以是一个浮点数，以指示更精确的睡眠时间。这是最常用的方法，因为它易于使用，并且独立于平台。实现如下:

**示例:**

## 蟒蛇 3

```py
# First import time module.
import time

# immediately prints the following.
print("GFG printed immediately.")
time.sleep(5.5)

# delays the execution
# for 5.5 secs.
print("GFG printed after 5.5 secs.")
```

**输出:**

<video class="wp-video-shortcode" id="video-520740-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201201130155/py1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201201130155/py1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201201130155/py1.mp4)</video>

**1(B)多线程编程中的休眠**

对于多线程 python 程序， *sleep()* 函数将当前线程挂起给定的秒数，而不是整个进程。但是对于单线程程序 *sleep()* 函数挂起线程和整个进程。实现如下:

**示例:**

## 蟒蛇 3

```py
# import threading and time module.
import threading
import time

def print_GFG():
    for i in range(5):
        # suspend the current thread.
        time.sleep(1)
        print("GFG")

def print_Geeksforgeeks():
    for i in range(5):
        # suspend the current thread.
        time.sleep(1.5)
        print("Geeksforgeeks")

# two threads are available in this program.
t1 = threading.Thread(target=print_GFG)
t2 = threading.Thread(target=print_Geeksforgeeks)
t1.start()
t2.start()
```