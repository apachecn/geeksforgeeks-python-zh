# Python | Tkinter 中的 after 方法

> 原文:[https://www . geesforgeks . org/python-after-method-in-tkinter/](https://www.geeksforgeeks.org/python-after-method-in-tkinter/)

Tkinter 提供了各种内置功能来开发交互式和特色图形用户界面。 **after()** 函数也是一个 Universal 函数，可以直接在根上使用，也可以和其他小部件一起使用。

```py
after(parent, ms, function = None, *args)
```

> **参数:**
> **父项**:是小部件或主窗口的对象，以使用该功能的为准。
> **ms** :是以毫秒为单位的时间。
> **功能**:应调用。
> ***args** :其他选项。

**代码#1:**

## 蟒蛇 3

```py
# importing only those functions which
# are needed
from tkinter import Tk, mainloop, TOP
from tkinter.ttk import Button

# time function used to calculate time
from time import time

# creating tkinter window
root = Tk()

button = Button(root, text = 'Geeks')
button.pack(side = TOP, pady = 5)

print('Running...')
# Calculating starting time
start = time()

# in after method 5000 milliseconds
# is passed i.e after 5 seconds
# main window i.e root window will
# get destroyed
root.after(5000, root.destroy)

mainloop()

# calculating end time
end = time()
print('Destroyed after % d seconds' % (end-start))
```

**输出:**

<video class="wp-video-shortcode" id="video-291296-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190408013114/after_video.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190408013114/after_video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190408013114/after_video.mp4)</video>

当你运行程序时，它会显示一个有[按钮](https://www.geeksforgeeks.org/python-creating-a-button-in-tkinter/)的 Tkinter 窗口，但是 5 秒钟后窗口被破坏。
**代码#2:** 一定时间后提示信息(在我们的程序中是 5 秒后)。

## 蟒蛇 3

```py
# importing only those functions which
# are needed
from tkinter import Tk, mainloop, TOP
from tkinter.ttk import Button
from tkinter.messagebox import _show

# creating tkinter window
root = Tk()
root.geometry('200x100 + 300 + 250')

button = Button(root, text = 'Geeks')
button.pack(side = TOP, pady = 5)

# in after method 5000 milliseconds
# is passed i.e after 5 seconds
# a message will be prompted
root.after(5000, lambda : _show('Title', 'Prompting after 5 seconds'))

# Destroying root window after 6.7 seconds
root.after(6700, root.destroy)

mainloop()
```

**输出:**
在下面的输出中，一个消息框会在 5 秒钟后提示你，你甚至可以在一定时间后通过传递函数名来调用任何函数。

<video class="wp-video-shortcode" id="video-291296-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190408014106/prompting_message.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20190408014106/prompting_message.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190408014106/prompting_message.mp4)</video>