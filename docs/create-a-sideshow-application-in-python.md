# 用 Python 创建一个 Sideshow 应用程序

> 原文:[https://www . geesforgeks . org/create-a-sideshow-application-in-python/](https://www.geeksforgeeks.org/create-a-sideshow-application-in-python/)

在这篇文章中，我们将创建一个幻灯片应用程序，即我们可以看到下一个图像，而无需手动或点击来更改它。

#### 所需模块:

*   **[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/):**Tkinter 包(“Tk 接口”)是 Tk GUI 工具包的标准 Python 接口。
*   **[枕头](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/):**Python 图像库为您的 Python 解释器增加了图像处理功能。该库提供了广泛的文件格式支持、高效的内部表示和相当强大的图像处理能力。可以使用以下命令安装:

```py
pip install Pillow

```

#### 逐步方法:

*   首先，我们必须导入模块。

## 蟒蛇 3

```py
# import required modules
import tkinter as tk
from tkinter import *
from PIL import Image
from PIL import ImageTk
```

*   加载图像。

## 蟒蛇 3

```py
# adjust window
root = tk.Tk()
root.geometry("200x200")

# loading the images
img = ImageTk.PhotoImage(Image.open("photo1.png"))
img2 = ImageTk.PhotoImage(Image.open("photo2.png"))
img3 = ImageTk.PhotoImage(Image.open("photo3.png"))

l = Label()
l.pack()
```

*   现在我们要做一个叫做*移动*的函数，让图像移动(这里的意思是一个图像出现，一个移动之后就消失了。

## 蟒蛇 3

```py
# using recursion to slide to next image
x = 1

# function to change to next image
def move():
    global x
    if x == 4:
        x = 1
    if x == 1:
        l.config(image=img)
    elif x == 2:
        l.config(image=img2)
    elif x == 3:
        l.config(image=img3)
    x = x+1
    root.after(2000, move)

# calling the function
move()
```

*   现在我们只需要调用 tkinter 的 mainloop 函数来结束任务。

## 蟒蛇 3

```py
root.mainloop()
```

*   完整代码=

## 蟒蛇 3

```py
# import required modules
import tkinter as tk
from tkinter import *
from PIL import Image
from PIL import ImageTk

# adjust window
root=tk.Tk()
root.geometry("200x200")

# loading the images
img=ImageTk.PhotoImage(Image.open("photo1.png"))
img2=ImageTk.PhotoImage(Image.open("photo2.png"))
img3=ImageTk.PhotoImage(Image.open("photo3.png"))

l=Label()
l.pack()

# using recursion to slide to next image
x = 1

# function to change to next image
def move():
    global x
    if x == 4:
        x = 1
    if x == 1:
        l.config(image=img)
    elif x == 2:
        l.config(image=img2)
    elif x == 3:
        l.config(image=img3)
    x = x+1
    root.after(2000, move)

# calling the function
move()

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-514585-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201115173431/autoimage_Trim.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201115173431/autoimage_Trim.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201115173431/autoimage_Trim.mp4)</video>