# 使用 Tkinter–Python 将图像转换为 PDFs】

> 原文:[https://www . geesforgeks . org/convert-images-to-pdf-using-tkinter-python/](https://www.geeksforgeeks.org/convert-images-to-pdf-using-tkinter-python/)

**前提条件:**[【tkinter】](https://www.geeksforgeeks.org/python-gui-tkinter/)、 [img2pdf](https://www.geeksforgeeks.org/python-convert-image-to-pdf-using-img2pdf-module/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。在本文中，我们将学习如何使用 Python 中的 Tkinter 将多个图像转换为多个 PDF 或将多个图像转换为一个 PDF。对于转换，我们将使用 **img2pdf** 模块。

**img2pdf** 是一个开源的 Python 包，用于将图像转换为 pdf 格式。它包括另一个模块枕头，也可以用来增强图像(亮度，对比度和其他东西)

**安装时，在您的终端中运行以下命令:**

```
pip install img2pdf
```

### **我们来了解一下分步实施:**

**步骤 1:** 创建一个 Tkinter 窗口并添加按钮、标签等…

## 蟒蛇 3

```
# Import Module
from tkinter import *

# Create Object
root = Tk() 
# set Geometry
root.geometry('400x200')

# Add Labels and Buttons
Label(root, text = "IMAGE CONVERSION", 
      font = "italic 15 bold").pack(pady = 10)

Button(root, text = "Select Images", font = 14).pack(pady = 10)

frame = Frame()
frame.pack(pady = 20)

Button(frame, text = "Image to PDF", relief = "solid",
                   bg = "white", font = 15).pack(side = LEFT,padx = 10)

Button(frame, text = "Images to PDF", relief = "solid",
                 bg = "white",font = 15).pack()

# Execute Tkinter
root.mainloop()
```

**第二步:**我们将创建三个函数；**选择 _ 文件()**、**图像 _ 至 _pdf()** 、**图像 _ 至 _pdf()**

*   **选择 _ 文件:**会帮你选择文件
*   **image_to_pdf:** 用于将一个图像文件转换为一个 pdf 文件
*   **images_to_pdf:** 用于将多个图像文件转换为一个 pdf 文件

## 蟒蛇 3

```
def select_file():
    global file_names
    file_names = askopenfilenames(initialdir = "/",title = "Select File")

# IMAGE TO PDF
def image_to_pdf():
    for index, file_name in enumerate(file_names):
        with open(f"file {index}.pdf", "wb") as f:
            f.write(img2pdf.convert(file_name))

# IMAGES TO PDF
def images_to_pdf():
    with open(f"file.pdf","wb") as f:
        f.write(img2pdf.convert(file_names))
```

**下面是实现:**

## 蟒蛇 3

```
# Import Module
from tkinter import *
from tkinter.filedialog import askopenfilenames
import img2pdf

# Create Object
root = Tk() 
# set Geometry
root.geometry('400x200')

def select_file():
    global file_names
    file_names = askopenfilenames(initialdir = "/",
                                  title = "Select File")

# IMAGE TO PDF
def image_to_pdf():
    for index, file_name in enumerate(file_names):
        with open(f"file {index}.pdf", "wb") as f:
            f.write(img2pdf.convert(file_name))

# IMAGES TO PDF
def images_to_pdf():
    with open(f"file.pdf", "wb") as f:
        f.write(img2pdf.convert(file_names))

# Add Labels and Buttons
Label(root, text = "IMAGE CONVERSION",
      font = "italic 15 bold").pack(pady = 10)

Button(root, text = "Select Images",
       command = select_file, font = 14).pack(pady = 10)

frame = Frame()
frame.pack(pady = 20)

Button(frame, text = "Image to PDF",
       command = image_to_pdf,
       relief = "solid",
       bg = "white", font = 15).pack(side = LEFT, padx = 10)

Button(frame, text = "Images to PDF",
       command = images_to_pdf, relief = "solid",
       bg = "white", font = 15).pack()

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-551593-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210129115749/FreeOnlineScreenRecorderProject2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210129115749/FreeOnlineScreenRecorderProject2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210129115749/FreeOnlineScreenRecorderProject2.mp4)</video>