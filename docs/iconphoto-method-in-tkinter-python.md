# Tkinter | Python 中的 iconphoto()方法

> 原文:[https://www . geesforgeks . org/icon photo-method-in-tkinter-python/](https://www.geeksforgeeks.org/iconphoto-method-in-tkinter-python/)

**iconphoto()** 方法用于设置任意 tkinter/toplevel 窗口的标题栏图标。但是要将任何图像设置为标题栏的图标，图像应该是**摄影图像**类的对象。
**语法:**

```
iconphoto(self, default = False, *args)
```

**设置图标图像的步骤–**

```
from tkinter import Tk
master = Tk()

photo = PhotoImage(file = "Any image file")
master.iconphoto(False, photo)
```

根据通过参数传递的命名照片图像设置此窗口的标题栏图标。如果默认值为*真*，这也适用于将来创建的所有顶层。图像中的数据在调用时作为快照。如果图像后来改变，这不会反映在*标题栏*图标中。该功能还可以将提供的图标缩放到合适的大小。
**代码#1:** 当提供照片图像时。

## 蟒蛇 3

```
# Importing Tkinter module
from tkinter import *
from tkinter.ttk import *

# Creating master Tkinter window
master = Tk()

# Creating object of photoimage class
# Image should be in the same folder
# in which script is saved
p1 = PhotoImage(file = 'info.png')

# Setting icon of master window
master.iconphoto(False, p1)

# Creating button
b = Button(master, text = 'Click me !')
b.pack(side = TOP)

# Infinite loop can be terminated by
# keyboard or mouse interrupt
# or by any predefined function (destroy())
mainloop()
```

**输出:**

![iconphoto() method in Tkinter](img/22d362dbba9d433d5613dc694d8b9df1.png)

**异常:**如果直接提供图像而不是 PhotoImage 对象，则会显示以下错误。
**代码#2:** 未提供 PhotoImage 对象时。

## 蟒蛇 3

```
# Importing Tkinter module
from tkinter import *
from tkinter.ttk import *

# Creating master Tkinter window
master = Tk()

# Setting icon of master window
master.iconphoto(False, 'info.png')

# Creating button
b = Button(master, text = 'Click me !')
b.pack(side = TOP)

# Infinite loop can be terminated by
# keyboard or mouse interrupt
# or by any predefined function (destroy())
mainloop()
```

**输出:**

```
Traceback (most recent call last):
  File "C:\Users\Admin\Documents\GUI_python\geeks.py", line 14, in 
    master.iconphoto(False, 'info.png')
  File "C:\Users\Admin\AppData\Local\Programs\Python\Python37-32\lib\tkinter\__init__.py", line 1910, in wm_iconphoto
    self.tk.call('wm', 'iconphoto', self._w, *args)
_tkinter.TclError: can't use "info.png" as iconphoto: not a photo image
```