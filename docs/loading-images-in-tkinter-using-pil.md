# 使用 PIL 加载 Tkinter 中的图像

> 原文:[https://www . geesforgeks . org/loading-images-in-tkinter-using-pil/](https://www.geeksforgeeks.org/loading-images-in-tkinter-using-pil/)

在本文中，我们将学习如何使用 PIL 模块将图像从用户系统加载到 Tkinter 窗口。该程序将打开一个对话框，从任何目录中选择所需的文件，并在 tkinter 窗口中显示。
**安装要求–**
**使用此命令安装 Tkinter :**

```py
pip install python-tk
```

**使用此命令安装 PIL :**

```py
pip install pillow
```

**导入模块–**

## 蟒蛇 3

```py
from tkinter import *

# loading Python Imaging Library
from PIL import ImageTk, Image

# To get the dialog box to open when required
from tkinter import filedialog
```

**注意:**ImageTk 模块包含从 PIL 图像创建和修改 Tkinter BitmapImage 和 PhotoImage 对象的支持，当您从系统中的任何位置打开文件或将文件保存在特定位置或地方时，会出现 filedialog 对话框。

**功能创建一个由按钮组成的 Tkinder 窗口–**

## 蟒蛇 3

```py
# Create a window
root = Tk()

# Set Title as Image Loader
root.title("Image Loader")

# Set the resolution of window
root.geometry("550x300 + 300 + 150")

# Allow Window to be resizable
root.resizable(width = True, height = True)

# Create a button and place it into the window using grid layout
btn = Button(root, text ='open image', command = open_img).grid(
                                        row = 1, columnspan = 4)
root.mainloop()
```

按钮对象是用文本“打开图像”创建的。单击它将调用 open_image 函数。
**将图像放在窗口上的功能–**

## 蟒蛇 3

```py
def open_img():
    # Select the Imagename  from a folder
    x = openfilename()

    # opens the image
    img = Image.open(x)

    # resize the image and apply a high-quality down sampling filter
    img = img.resize((250, 250), Image.ANTIALIAS)

    # PhotoImage class is used to add image to widgets, icons etc
    img = ImageTk.PhotoImage(img)

    # create a label
    panel = Label(root, image = img)

    # set the image as img
    panel.image = img
    panel.grid(row = 2)
```

openfilename 函数将返回图像的文件名。
**功能返回从对话框中选择的文件名–**

## 蟒蛇 3

```py
def openfilename():

    # open file dialog box to select image
    # The dialogue box has a title "Open"
    filename = filedialog.askopenfilename(title ='"pen')
    return filename
```

要运行这段代码，请通过扩展名保存它。py，然后打开 cmd(命令提示符)，移动到保存文件的位置，然后写下–

```py
python "filename".py 
```

然后按回车键，它就会运行。或者只需双击您的。py 扩展名文件。

**输出:**
https://media . geekesforgeks . org/WP-content/uploads/20191121233525/Screencast-from-星期四-21-11-2019-111137-ist2 . webm