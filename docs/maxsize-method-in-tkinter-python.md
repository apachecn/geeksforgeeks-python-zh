# Tkinter | Python 中的 maxsize()方法

> 原文:[https://www . geesforgeks . org/maxsize-method-in-tkinter-python/](https://www.geeksforgeeks.org/maxsize-method-in-tkinter-python/)

该方法用于设置根窗口的**最大尺寸**(一个窗口可以扩展的最大尺寸)。用户仍然可以将窗口的大小缩小到最小。

**语法:**

```
 master.maxsize(height, width) 
```

这里，高度和宽度以像素为单位。

**代码#1:**

```
# importing only those functions
# which are needed
from tkinter import *
from tkinter.ttk import * 
from time import strftime

# creating tkinter window
root = Tk()

# Adding widgets to the root window
Label(root, text = 'GeeksforGeeks', 
      font =('Verdana', 15)).pack(side = TOP, pady = 10)

Button(root, text = 'Click Me !').pack(side = TOP)

mainloop()
```

**输出:**
窗口初始大小(未设置窗口最大大小)
![Initial size of the window ](img/8960a9e996c60ba79c3f830cc8c7f354.png)

窗口的扩展尺寸(该窗口可以扩展到屏幕的尺寸，因为尺寸不是固定的)。
![Expanded size of the window](img/4adec74218fbedd3a4a0bfc7165eb264.png)

**代码#2:** 固定根窗的最大尺寸

```
# importing only those functions
# which are needed
from tkinter import * 
from tkinter.ttk import * 
from time import strftime

# creating tkinter window
root = Tk()

# Fixing the size of the root window.
# No one can now expand the size of the
# root window than the specified one.
root.maxsize(200, 200)

# Adding widgets to the root window
Label(root, text = 'GeeksforGeeks', 
      font =('Verdana', 15)).pack(side = TOP, pady = 10)

Button(root, text = 'Click Me !').pack(side = TOP)

mainloop()
```

**输出:**
窗口最大扩展尺寸
![Maximum expanded size of the window](img/ac5952a223836daec9da0c111f656cea.png)

**注意:** [Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 还提供了 [minsize()](https://www.geeksforgeeks.org/minsize-method-in-tkinter-python/) 方法，用于设置窗口的最小尺寸。