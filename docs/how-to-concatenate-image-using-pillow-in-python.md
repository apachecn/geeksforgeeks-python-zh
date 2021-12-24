# 如何在 Python 中使用枕头连接图像？

> 原文:[https://www . geesforgeks . org/如何使用 python 中的枕头连接图像/](https://www.geeksforgeeks.org/how-to-concatenate-image-using-pillow-in-python/)

**先决条件:** [蟒枕](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/)

连接图像意味着两个图像的连接。我们可以合并任何图像，无论它有不同的像素，不同的图像格式，即' jpeg '，' png '，' gif '，' tiff '等。在 python 中，我们可以使用 Python 图像库(也称为枕头库)来连接两个图像。在本文中，我们将看到图像的拼接是如何完成的。

图像拼接可以通过两种方式完成:

*   水平的
*   垂直的

### **水平拼接图像**

**进场:**

*   导入模块
*   打开图像
*   使用 [Resize()](https://www.geeksforgeeks.org/python-pil-image-resize-method/) 功能调整图像大小。两个调整大小的图像应该具有相同的宽度和高度，以便它们的纵横比保持不变，并且可以粘贴到新的背景图像中。
*   为了创建一个新的图像，它有一个 [new()](https://www.geeksforgeeks.org/python-pil-image-new-method/) 函数，该函数有 3 个参数(“模式”、“大小”、“颜色”)
*   使用[粘贴()](https://www.geeksforgeeks.org/python-pil-paste-and-rotate-method/)将图像粘贴到新图像

**程序:**

## 蟒蛇 3

```
# library
from PIL import Image
import matplotlib.pyplot as plt

# opening up of images
img = Image.open("logo.png")
img1 = Image.open("logo2.png")
img.size
img1.size
img_size = img.resize((250, 90))
img1_size = img1.resize((250, 90))

# creating a new image and pasting 
# the images
img2 = Image.new("RGB", (500, 90), "white")

# pasting the first image (image_name,
# (position))
img2.paste(img_size, (0, 0))

# pasting the second image (image_name,
# (position))
img2.paste(img1_size, (250, 0))

plt.imshow(img2)
```

**输出:**

![](img/ba514617a32fd0203555586f46456217.png)

### **垂直连接图像**

整个代码与水平代码相同，但唯一的变化是，在水平代码中，我们将宽度加倍，高度相同，但在垂直代码中，我们将宽度的大小相同，但高度加倍。

**进场:**

*   导入用于图像处理的库。
*   使用 Image.open()打开库。
*   使用 img.size 了解图像的大小。
*   使用 img.resize((宽度，高度))来调整图像的大小。
*   两幅图像的大小应该相同。
*   使用 new()创建一个新图像，并传递 3 个参数“模式”、“大小”、“颜色”)。
*   新图像的大小应为(宽度，2 *高度)。
*   创建新图像后，使用粘贴()粘贴第一个图像，并传递参数(img_resize，(位置))#position(0，0)
*   粘贴第一个图像后，使用粘贴粘贴第二个图像，并传递参数(img1_reszie，(位置))。在位置上，宽度将是相同的，但高度将是第一个图像高度的最后一个位置。。#位置=(0，180)
*   使用 plt.imshow(img2)显示图像的连接。

**程序:**

## 蟒蛇 3

```
# library
from PIL import Image
import matplotlib.pyplot as plt

# opening up of images
img = Image.open("logo.png")
img1 = Image.open("logo2.png")
img.size
img1.size
img_size = img.resize((250, 90))
img1_size = img1.resize((250, 90))

# creating a new image and pasting the 
# images
img2 = Image.new("RGB", (250, 180), "white")

# pasting the first image (image_name,
# (position))
img2.paste(img_size, (0, 0))

# pasting the second image (image_name,
# (position))
img2.paste(img1_size, (0, 90)

plt.imshow(img2)
```

**输出:**

![](img/80c14331297a27f85ddacdb5b5e4c20d.png)