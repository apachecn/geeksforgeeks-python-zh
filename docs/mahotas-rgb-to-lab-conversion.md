# maho tas–RGB 到 LAB 的转换

> 原文:[https://www . geesforgeks . org/maho tas-RGB 到 lab-conversion/](https://www.geeksforgeeks.org/mahotas-rgb-to-lab-conversion/)

在本文中，我们将看到如何在 mahotas 中将 rgb 图像转换为 CIE L*a*b*。RGB 图像，有时也称为真彩色图像，在 MATLAB 中存储为一个 m 乘 n 乘 3 的数据数组，该数组定义了每个单独像素的红色、绿色和蓝色分量。CIELAB 颜色空间(也称为 CIE L*a*b*或有时简称为“LAB”颜色空间)是由国际照明委员会(CIE)在 1976 年定义的颜色空间。

在本教程中我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/f013f576026c96925a69f4df10464384.png)

为此，我们将使用 mahotas.colors.rgb2sepiamethod

> **语法:**maho tas . colors . rgb2lab(img)
> **参数:**它以图像对象作为参数
> **返回:**它返回图像对象

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

# showing image
print("Image")
imshow(img)
show()

# rgb to lab
new_img = mahotas.colors.rgb2lab(img)

# showing new image
print("New Image")
imshow(new_img)
show()
```

**强:**

```py
Image
```

![](img/f013f576026c96925a69f4df10464384.png)

```py
New Image
```

![](img/5daae853488d162dd08b0463366621a7.png)

另一个例子

## 蟒蛇 3

```py
# importing required libraries
import mahotas
import numpy as np
import matplotlib.pyplot as plt
import os

# loading image
img = mahotas.imread('dog_image.png')

# filtering image
img = img[:, :, :3]

# showing image
print("Image")
imshow(img)
show()

# rgb to lab
new_img = mahotas.colors.rgb2lab(img)

# showing new image
print("New Image")
imshow(new_img)
show()
```

**强:**

```py
Image

```

![](img/e3c66e3e9870972a0777c387df5090d1.png)

```py
New Image
```

![](img/cef887eecec2affd6c0d6eca3cc80716.png)