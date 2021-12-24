# maho tas–图像的欧拉数

> 原文:[https://www . geesforgeks . org/maho tas-Euler-number-of-image/](https://www.geeksforgeeks.org/mahotas-euler-number-of-image/)

在本文中，我们将看到如何在 mahotas 中获得图像的欧拉数。欧拉数是图像拓扑的度量。它被定义为图像中对象的总数减去这些对象中的孔的数量。你可以使用 4-或 8-连通的邻域。

在本教程中，我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.euler 方法
> 
> **语法:** mahotas.euler(img)
> 
> **自变量:**以图像对象为自变量
> 
> **返回:**返回整数

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

# creating a labeled image
marker, n_nucleus = mahotas.label(img)

# showing image
imshow(img)
show()

# euler number of image of image
euler = mahotas.euler(img)

print("Euler Number of Image : " + str(euler))
```

**输出:**

```py
Image threshold using Otsu Method
```

![](img/af1a498fc91de1bb4de1ff5f7faf7b73.png)

```py
Euler Number of Image : 54.25
```

另一个例子

## 蟒蛇 3

```py
# importing required libraries
import mahotas
import numpy as np
from pylab import gray, imshow, show
import os

# loading image
img = mahotas.imread('dog_image.png')

# filtering image
img = img[:, :, 0]

# otsu method
T_otsu = mahotas.otsu(img)  

# image values should be greater than otsu value
img = img > T_otsu

print("Image threshold using Otsu Method")

# showing image
imshow(img)
show()

# euler number of image of image
euler = mahotas.euler(img)

print("Euler Number of Image : " + str(euler))
```

**输出:**

```py
Image threshold using Otsu Method 
```

![](img/ab80b555f0ab23baeefa960156d3bedc.png)

```py
Euler Number of Image : 76.75
```