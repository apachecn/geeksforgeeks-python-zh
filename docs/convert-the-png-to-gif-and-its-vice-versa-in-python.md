# 转换。巴布亚新几内亚到。在 Python 中是 GIF，反之亦然

> 原文:[https://www . geesforgeks . org/convert-the-png-to-gif-its-反之亦然-in-python/](https://www.geeksforgeeks.org/convert-the-png-to-gif-and-its-vice-versa-in-python/)

**先决条件:**

*   [箭](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/)
*   tkinter

Python 支持将一种文件格式转换成另一种文件格式的子系统。本文讨论了这个主题，并描述了如何将一个 png 文件转换为其等价的 gif 文件，反之亦然。为了将一种文件格式转换成另一种格式，采用了 PIL。

给定的例子使用了一个图形用户界面的代码，所以我们将需要 Tkinter。它是一个绑定到 Tk 图形用户界面工具包的 Python。这是 Tk 图形用户界面工具包的标准 Python 接口，它提供了图形用户界面应用程序的接口。

### 方法

*   导入模块
*   创建普通窗口
*   添加按钮以选择是将 png 转换为 gif 还是相反
*   开文件
*   检查提供的文件格式是否正确
*   转换为其相应的等价物
*   保存图像
*   执行代码

**程序:**

## 蟒蛇 3

```py
from tkinter import *
from tkinter import filedialog as fd
import os
from PIL import Image
from tkinter import messagebox

root = Tk()

# naming the GUI interface to image_conversion_APP
root.title("Image_Conversion_App")

# creating the Function which converts the jpg_to_png

def gif_to_png():
    global im

    import_filename = fd.askopenfilename()
    if import_filename.endswith(".gif"):
        im = Image.open(import_filename)
        export_filename = fd.asksaveasfilename(defaultextension=".png")
        im.save(export_filename)
        messagebox.showinfo("Success", "File converted to .png")
    else:
        messagebox.showerror("Fail!!", "Error Interrupted!!!! Check Again")

def png_to_gif():
    import_filename = fd.askopenfilename()
    if import_filename.endswith(".png"):
        im = Image.open(import_filename)
        export_filename = fd.asksaveasfilename(defaultextension=".gif")
        im.save(export_filename)
        messagebox.showinfo("Success", "File converted to .gif")
    else:
        messagebox.showerror("Fail!!", "Error Interrupted!!!! Check Again")

button1 = Button(root, text="GIF_to_PNG", width=20, height=2, bg="green",
                 fg="white", font=("helvetica", 12, "bold"), command=gif_to_png)

button1.place(x=120, y=120)

button2 = Button(root, text="PNG_to_GIF", width=20, height=2, bg="green",
                 fg="white", font=("helvetica", 12, "bold"), command=png_to_gif)

button2.place(x=120, y=220)
root.geometry("500x500+400+200")
root.mainloop()
```

**输出:**

![](img/a869d2a98cb974c77faaf3e1f1afbe9e.png)