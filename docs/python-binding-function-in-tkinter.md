# Python | Tkinter 中的绑定功能

> 原文:[https://www . geesforgeks . org/python-binding-function-in-tkinter/](https://www.geeksforgeeks.org/python-binding-function-in-tkinter/)

[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个广泛应用于桌面应用的 GUI(图形用户界面)模块。它与 Python 一起提供，但是您也可以借助 ***pip*** 命令从外部安装它。
它提供了多种 Widget 类和功能，借助这些类和功能，我们的 GUI 在外观和功能上都变得更加吸引人和用户友好。
绑定功能用于处理事件。我们可以将 Python 的函数和方法绑定到一个事件，也可以将这些函数绑定到任何特定的小部件。
**代码#1:** 将鼠标移动与 tkinter Frame 绑定。

## 蟒蛇 3

```py
# Import all files from
# tkinter and overwrite
# all the tkinter files
# by tkinter.ttk
from tkinter import *
from tkinter.ttk import *

# creates tkinter window or root window
root = Tk()
root.geometry('200x100')

# function to be called when mouse enters in a frame
def enter(event):
    print('Button-2 pressed at x = % d, y = % d'%(event.x, event.y))

# function to be called when when mouse exits the frame
def exit_(event):
    print('Button-3 pressed at x = % d, y = % d'%(event.x, event.y))

# frame with fixed geometry
frame1 = Frame(root, height = 100, width = 200)

# these lines are showing the
# working of bind function
# it is universal widget method
frame1.bind('<Enter>', enter)
frame1.bind('<Leave>', exit_)

frame1.pack()

mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-289928-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190402212137/working_of_bind_fucntion_with_mouse_event.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190402212137/working_of_bind_fucntion_with_mouse_event.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190402212137/working_of_bind_fucntion_with_mouse_event.mp4)</video>

**代码#2:** 将鼠标按钮与图框
绑定

## 蟒蛇 3

```py
# Import all files from
# tkinter and overwrite
# all the tkinter files
# by tkinter.ttk
from tkinter import *
from tkinter.ttk import *

# creates tkinter window or root window
root = Tk()
root.geometry('200x100')

# function to be called when button-2 of mouse is pressed
def pressed2(event):
    print('Button-2 pressed at x = % d, y = % d'%(event.x, event.y))

# function to be called when button-3 of mouse is pressed
def pressed3(event):
    print('Button-3 pressed at x = % d, y = % d'%(event.x, event.y))

## function to be called when button-1 is double clocked
def double_click(event):
    print('Double clicked at x = % d, y = % d'%(event.x, event.y))

frame1 = Frame(root, height = 100, width = 200)

# these lines are binding mouse
# buttons with the Frame widget
frame1.bind('<Button-2>', pressed2)
frame1.bind('<Button-3>', pressed3)
frame1.bind('<Double 1>', double_click)

frame1.pack()

mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-289928-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190402212646/working_of_bind_fucntion_with_mouse_click.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20190402212646/working_of_bind_fucntion_with_mouse_click.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190402212646/working_of_bind_fucntion_with_mouse_click.mp4)</video>

**代码#3:** 将键盘按钮与根窗口(tkinter 主窗口)绑定。

## 蟒蛇 3

```py
# Import all files from
# tkinter and overwrite
# all the tkinter files
# by tkinter.ttk
from tkinter import *
from tkinter.ttk import *

# function to be called when
# keyboard buttons are pressed
def key_press(event):
    key = event.char
    print(key, 'is pressed')

# creates tkinter window or root window
root = Tk()
root.geometry('200x100')

# here we are binding keyboard
# with the main window
root.bind('<Key>', key_press)

mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-289928-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190402230107/binding_keyboard_buttons_with_tkinter.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20190402230107/binding_keyboard_buttons_with_tkinter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190402230107/binding_keyboard_buttons_with_tkinter.mp4)</video>

**注意:**当我们用 tkinter 窗口绑定键盘按钮时，每当我们按下特殊字符时，我们只会得到空格，而在字母和数字的情况下，我们会得到实际值(在字符串中)。