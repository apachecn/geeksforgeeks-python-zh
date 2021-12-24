# 使用 Python 将巴布亚新几内亚转换为 JPG

> 原文:[https://www . geesforgeks . org/convert-png-to-jpg-using-python/](https://www.geeksforgeeks.org/convert-png-to-jpg-using-python/)

PNG 和 JPG 格式用于图像插图。这两种格式都被用来为某些类型的图像提供良好的兼容性，比如巴布亚新几内亚更适合线条画和图标图形，而 JPG 适合照片。然而，对于媒体和图片的使用和存储，两者都是可以相互转换的。Python 提供了各种选项来执行图像转换。

**方法 1: Python 映像库(PIL)**

Python 使用 PIL 包(Python 图像库)为图像处理提供支持。该库提供了广泛的文件格式支持，也就是说，它可以用于将图像从一种格式转换为另一种格式。可以使用以下命令将此包安装到环境中:

```
pip install Pillow
```

这个包提供了一个名为 Image 的模块，用于创建新的映像并将其加载到环境中。它还允许处理图像格式及其相关方向。它用于表示 PIL 图像。相关的语法是:

```
from PIL import Image
```

图像模块的以下功能用于将图像从巴布亚新几内亚转换为 JPG。

**Image.open():** 打开并识别图像文件。除非显式执行 load()操作，否则它不会加载文件。它只是打开图像，而没有实际分析图像内容。

```
PIL.Image.open(fp, mode='r', formats=None)
```

> **论据:**
> 
> fp —文件名，路径名。路径对象或文件对象。
> 
> 模式—总是在阅读模式下打开。
> 
> 格式—执行文件打开操作的格式列表。
> 
> **返回类型:**
> 
> 图像对象。

**Image.save():** 用指定的文件名保存图像。如果没有指定扩展名，则从指定的文件名分析扩展名。

```
Image.save(fp, format=None, **params)
```

> **论据:**
> 
> fp —文件名，路径名。路径对象或文件对象。
> 
> 格式—可选格式。
> 
> 参数—图像写入器的额外参数。
> 
> **返回类型:**
> 
> 不归还任何东西。

以下示例 Python 代码用于将图像从巴布亚新几内亚转换为 JPG:

## 蟒蛇 3

```
#importing the required package
from PIL import Image

#open image in png format
img_png = Image.open('C:\gfg\img.png')

#The image object is used to save the image in jpg format
img_png.save('C:\gfg\modified_img.jpg')
```

**输出:**

以下是 C 语言中的原始文件:

![](img/79430e702d7dfa4ecd5306f4cd4eef27.png)

以下是程序执行后同一文件夹的内容:

![](img/62bd957105f9a126671652d6a0912948.png)

**方法二:使用 OpenCV**

OpenCV(开源计算机视觉)库是一个图像处理库，使用 MATLAB 语法执行数值运算。可以使用以下命令将其整合到我们的环境中:

```
pip install opencv-python
```

下载后，可以使用命令将库导入 python 程序

```
import cv2
```

它为我们提供了各种操作图像的函数，例如，imread()函数将本地机器的图像名称作为参数，imwrite()函数用于执行图像的操作和修改。该方法具有以下签名:

```
imwrite ( path, image)
```

> **论据:**
> 
> 路径—表示文件名的字符串，文件名必须包含扩展名图像格式，如。jpg，。巴布亚新几内亚等。
> 
> 图像—要保存的图像。
> 
> **返回类型:**
> 
> 如果图像保存成功，则返回 true。

## 蟒蛇 3

```
#importing required packages and library
import cv2

# Loading .png image
png_img = cv2.imread('img.png')

# converting to jpg file
#saving the jpg file
cv2.imwrite('modified_img.jpg', png_img, [int(cv2.IMWRITE_JPEG_QUALITY), 100])
```

**输出:**

以下目录存储名为“img.png”的图像:

![](img/79430e702d7dfa4ecd5306f4cd4eef27.png)

程序执行后获得以下输出:

![](img/62bd957105f9a126671652d6a0912948.png)