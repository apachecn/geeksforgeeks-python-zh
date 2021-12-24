# 如何用 Python 将图像转换成 PDF？

> 原文:[https://www . geesforgeks . org/python-convert-image-to-pdf-using-img2pdf-module/](https://www.geeksforgeeks.org/python-convert-image-to-pdf-using-img2pdf-module/)

`**img2pdf**`是一个开源的 Python 包，用于将图像转换为 pdf 格式。它包括另一个模块枕头，也可以用来增强图像(亮度，对比度和其他东西)

使用此命令安装软件包

```
pip install img2pdf
```

**下面是实现:**

使用 img2pdf 模块提供的`img2pdf.convert()`功能可以将图像转换成 pdf 字节，然后以 wb 模式打开 pdf 文件，用字节写入。

```
# Python3 program to convert image to pfd
# using img2pdf library

# importing necessary libraries
import img2pdf
from PIL import Image
import os

# storing image path
img_path = "C:/Users/Admin/Desktop/GfG_images/do_nawab.png"

# storing pdf path
pdf_path = "C:/Users/Admin/Desktop/GfG_images/file.pdf"

# opening image
image = Image.open(img_path)

# converting into chunks using img2pdf
pdf_bytes = img2pdf.convert(image.filename)

# opening or creating pdf file
file = open(pdf_path, "wb")

# writing pdf files with chunks
file.write(pdf_bytes)

# closing image file
image.close()

# closing pdf file
file.close()

# output
print("Successfully made pdf file")
```

**输出:**

```
Successfully made pdf file
```