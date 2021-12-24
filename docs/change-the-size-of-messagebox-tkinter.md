# 更改消息框的大小–Tkinter

> 原文:[https://www . geesforgeks . org/change-the-size-messagebox-tkinter/](https://www.geeksforgeeks.org/change-the-size-of-messagebox-tkinter/)

Python 有很多用于 **GUI** 的库。 [Tkinter](http://geeksforgeeks.org/python-gui-tkinter/) 是提供图形用户界面的库之一。对于短消息，我们可以使用消息框库。它有许多有效的接口功能。在这个消息框库中提供不同类型的功能来显示**消息框。**

1.  **show info ():-** displays some commonly used information.
2.  **show warning ():-** Show a warning to the user.
3.  **Show error ():-** Displays different types of errors.
4.  **ask question ():-** Ask the user for an inquiry.

**例:**

## 蟒 3

```
# MessageBox Illustration of showinfo() function

from tkinter import *
from tkinter import messagebox

# creating window object
top = Tk()

def Button_1():
    messagebox.showinfo("Status",
                        "Button-1 Pressed")

def Button_2():
    messagebox.showinfo("Status",
                        "Button-2 Pressed")

# size for window
top.geometry("100x100")
B1 = Button(top, text = "Button-1",
            command = Button_1)  
B2 = Button(top, text = "Button-2",
            command = Button_2)  

B1.pack()
B2.pack()
top.mainloop()  
```