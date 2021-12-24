# Tkinter 中的开/关切换按钮开关

> 原文:[https://www . geesforgeks . org/on-off-toggle-button-switch-in-tkinter/](https://www.geeksforgeeks.org/on-off-toggle-button-switch-in-tkinter/)

**先决条件:** [**Tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为开发图形用户界面提供了多种选择。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。

在本文中，我们将学习如何使用 this 进行开/关切换。

**进场:**

*   制作一个名为**的全局变量 is _ on**；默认值为“真”，表示开关打开。
*   制作两个**图像**物体；一个物体有**“开像”**，另一个物体有**“关像”**。
*   创建一个默认为图像上**的按钮；将边框宽度设置为零。**
*   使用 **config()** 方法，创建一个改变按钮图像的功能。
*   该功能将检查**是 _on** 值是**真**还是**假**

**图片链接:**

*   [打开](https://drive.google.com/file/d/1tlLl2hjPq38mc_c_PpMhkKDlP1HqvDY5/view?usp=sharing)
*   [关闭](https://drive.google.com/file/d/1bejSlQtIokdQw7d-5Qbqw1X3Sw5Y2bWO/view?usp=sharing)

**下面是实现:**

## 蟒蛇 3

```
# Import Module
from tkinter import *

# Create Object
root = Tk()

# Add Title
root.title('On/Off Switch!')

# Add Geometry
root.geometry("500x300")

# Keep track of the button state on/off
#global is_on
is_on = True

# Create Label
my_label = Label(root,
    text = "The Switch Is On!",
    fg = "green",
    font = ("Helvetica", 32))

my_label.pack(pady = 20)

# Define our switch function
def switch():
    global is_on

    # Determine is on or off
    if is_on:
        on_button.config(image = off)
        my_label.config(text = "The Switch is Off",
                        fg = "grey")
        is_on = False
    else:

        on_button.config(image = on)
        my_label.config(text = "The Switch is On", fg = "green")
        is_on = True

# Define Our Images
on = PhotoImage(file = "on.png")
off = PhotoImage(file = "off.png")

# Create A Button
on_button = Button(root, image = on, bd = 0,
                   command = switch)
on_button.pack(pady = 50)

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-544819-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210117181116/FreeOnlineScreenRecorderProject8.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210117181116/FreeOnlineScreenRecorderProject8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210117181116/FreeOnlineScreenRecorderProject8.mp4)</video>