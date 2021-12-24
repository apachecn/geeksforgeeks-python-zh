# 如何用 Python 测试打字速度？

> 原文:[https://www . geesforgeks . org/如何使用 python 测试打字速度/](https://www.geeksforgeeks.org/how-to-test-typing-speed-using-python/)

**先决条件:**[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

在本文中，我们将使用 Python 语言创建一个程序，用一个基本的 GUI 应用程序测试用户的打字速度。这里像 **Tkinter** 和 **Timeit** 这样的 Python 库分别用于速度测试的 GUI 和时间计算。此外，**随机**功能用于获取速度测试计算的随机字。以下命令用于安装上述库:

```py
pip install tkintertable
pip install pytest-timeit
```

首先，导入如上所述安装的所有库，并使用自下而上的方法创建使用 python 测试打字速度的程序。

下面是实现。

## 蟒蛇 3

```py
# importing all libraries
from tkinter import *
from timeit import default_timer as timer
import random

# creating window using gui
window = Tk()

# the size of the window is defined
window.geometry("450x200")

x = 0

# defining the function for the test
def game():
    global x

    # loop for destroying the window
    # after on test
    if x == 0:
        window.destroy()
        x = x+1

    # defining function for results of test
    def check_result():
        if entry.get() == words[word]:

            # here start time is when the window
            # is opened and end time is when
            # window is destroyed
            end = timer()

            # we deduct the start time from end
            # time and calculate results using
            # timeit function
            print(end-start)
        else:
            print("Wrong Input")

    words = ['programming', 'coding', 'algorithm',
             'systems', 'python', 'software']

    # Give random words for testing the speed of user
    word = random.randint(0, (len(words)-1))

    # start timer using timeit function
    start = timer()
    windows = Tk()
    windows.geometry("450x200")

    # use label method of tkinter for labeling in window
    x2 = Label(windows, text=words[word], font="times 20")

    # place of labeling in window
    x2.place(x=150, y=10)
    x3 = Label(windows, text="Start Typing", font="times 20")
    x3.place(x=10, y=50)

    entry = Entry(windows)
    entry.place(x=280, y=55)

    # buttons to submit output and check results
    b2 = Button(windows, text="Done",
                command=check_result, width=12, bg='grey')
    b2.place(x=150, y=100)

    b3 = Button(windows, text="Try Again",
                command=game, width=12, bg='grey')
    b3.place(x=250, y=100)
    windows.mainloop()

x1 = Label(window, text="Lets start playing..", font="times 20")
x1.place(x=10, y=50)

b1 = Button(window, text="Go", command=game, width=12, bg='grey')
b1.place(x=150, y=100)

# calling window
window.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-464071-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200804170454/typing-speed-test-python.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200804170454/typing-speed-test-python.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200804170454/typing-speed-test-python.webm)</video>

在上面的代码中，我们首先使用 Tkinter 创建速度测试窗口。该函数用于计算和打印用户输入后的正确输出。向用户提供特定的单词列表来打字和测试打字速度。为此，我们提供了一个单词列表，并用随机函数生成它们。