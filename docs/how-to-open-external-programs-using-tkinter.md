# 如何使用 Tkinter 打开外部程序？

> 原文:[https://www . geesforgeks . org/如何使用-tkinter/](https://www.geeksforgeeks.org/how-to-open-external-programs-using-tkinter/) 打开外部程序

**前提条件:**[【tkinter】](https://www.geeksforgeeks.org/python-gui-tkinter/)、 [os](https://www.geeksforgeeks.org/os-module-python-examples/)

Python 为开发图形用户界面提供了多种选择。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。在本文中，我们将学习如何使用 Tkinter 打开外部程序。这里我们将使用 os 模块中的 **system()** 方法。

**进场:**

*   首先，我们将导入所需的库
*   然后我们创建一个对象，它会要求您打开一个文件
*   要打开该文件，我们将使用**操作系统**模块中的**系统()**方法。

**语法:**

> 操作系统(“% s”“%文件路径)

**下面是实现:**

## 蟒蛇 3

```py
# Import Library
from tkinter import *
import os
from tkinter.filedialog import askopenfilename 

# Create Object 
root = Tk() 

# Set geometry
root.geometry('200x200') 

def open_file(): 
    file = askopenfilename()
    os.system('"%s"' % file)

Button(root, text ='Open', 
       command = open_file).pack(side = TOP, 
                                 pady = 10) 

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-544802-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210118131946/FreeOnlineScreenRecorderProject3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210118131946/FreeOnlineScreenRecorderProject3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210118131946/FreeOnlineScreenRecorderProject3.mp4)</video>