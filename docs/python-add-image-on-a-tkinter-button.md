# Python |在 Tkinter 按钮上添加图像

> 原文:[https://www . geesforgeks . org/python-add-image-on-a-tkinter-button/](https://www.geeksforgeeks.org/python-add-image-on-a-tkinter-button/)

[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个 Python 模块，用于借助各种小部件和功能创建 GUI(图形用户界面)应用程序。像任何其他图形用户界面模块一样，它也支持图像，即您可以在应用程序中使用图像来使其更具吸引力。

可以借助`PhotoImage()`方法添加图像。这是一个 Tkinter 方法，这意味着您不必导入任何其他模块来使用它。

**重要提示:**如果在[按钮](https://www.geeksforgeeks.org/python-creating-a-button-in-tkinter/)上同时给出图像和文本，则文本将占主导地位，按钮上将只出现图像。但是如果你想同时显示图像和文本，那么你必须在按钮选项中通过**复合**。

> **`Button(master, text = "Button", image = "image.png", compound=LEFT)`**
> 
> `**compound = LEFT**` - >图像将在按钮左侧
> `**compound = RIGHT**` - >图像将在按钮右侧
> `**compound = TOP**` - >图像将在按钮顶部
> `**compound = BOTTOM**` - >图像将在按钮底部

**语法:**

```
photo = PhotoImage(file = "path_of_file")
```

*path_of_file* 是本地机器上可用的任何有效路径。

**代码#1:**

```
# importing only those functions
# which are needed
from tkinter import * 
from tkinter.ttk import *

# creating tkinter window
root = Tk()

# Adding widgets to the root window
Label(root, text = 'GeeksforGeeks', font =(
  'Verdana', 15)).pack(side = TOP, pady = 10)

# Creating a photoimage object to use image
photo = PhotoImage(file = r"C:\Gfg\circle.png")

# here, image option is used to
# set image on button
Button(root, text = 'Click Me !', image = photo).pack(side = TOP)

mainloop()
```

**输出:**
![](img/b8ba644c9a74329fb8718b603f685022.png)
在输出中观察到按钮上只显示图像，按钮的大小也比平时的大小大这是因为我们还没有设置图像的大小。

**代码#2:** 在[按钮](https://www.geeksforgeeks.org/python-creating-a-button-in-tkinter/)上显示图像和文本。

```
# importing only those functions
# which are needed
from tkinter import * 
from tkinter.ttk import *

# creating tkinter window
root = Tk()

# Adding widgets to the root window
Label(root, text = 'GeeksforGeeks', font =(
  'Verdana', 15)).pack(side = TOP, pady = 10)

# Creating a photoimage object to use image
photo = PhotoImage(file = r"C:\Gfg\circle.png")

# Resizing image to fit on button
photoimage = photo.subsample(3, 3)

# here, image option is used to
# set image on button
# compound option is used to align
# image on LEFT side of button
Button(root, text = 'Click Me !', image = photoimage,
                    compound = LEFT).pack(side = TOP)

mainloop()
```

**输出:**
![](img/d179adc9e89142894d501ef8f0aec992.png)
观察文字和图像都出现了，图像的大小也小了。