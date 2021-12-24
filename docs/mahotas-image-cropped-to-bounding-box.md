# maho tas–裁剪到边界框的图像

> 原文:[https://www . geeksforgeeks . org/maho tas-image-裁剪到边界框/](https://www.geeksforgeeks.org/mahotas-image-cropped-to-bounding-box/)

在本文中，我们将看到如何在 mahotas 中将图像裁剪到边界框中。借助 bbox 方法可以得到图像包围盒。在本教程中我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为了做到这一点，我们将使用 mahotas.croptobbox 方法
> 
> **语法:**mahotas . croptobox(img)
> 
> **自变量:**以图像对象为自变量
> 
> **返回:**返回图像对象

**注意:**输入图像应被过滤或加载为灰色

为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并在索引的帮助下过滤它，下面是这样做的命令

```py
image = image[:, :, 0]
```

下面是实现

## 蟒蛇 3

```py
# importing required libraries
import mahotas
import mahotas.demos
from pylab import gray, imshow, show
import numpy as np

# loading image
img = mahotas.demos.load('lena')

# filtering image
img = img.max(2)

# otsu method
T_otsu = mahotas.otsu(img)  

# image values should be greater than otsu value
img = img > T_otsu

print("Image threshold using Otsu Method")

# showing image
imshow(img)
show()

# crop to bbox
new_img = mahotas.croptobbox(img)

print("Cropped to bbox Image")

# showing image
imshow(new_img)
show()
```