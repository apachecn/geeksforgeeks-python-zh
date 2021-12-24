# maho tas–图像的适当结构元素

> 原文:[https://www . geeksforgeeks . org/maho tas-适当-结构-图像元素/](https://www.geeksforgeeks.org/mahotas-appropriate-structuring-element-of-image/)

在本文中，我们将了解如何在 mahotas 中获得图像的适当结构元素。结构化元素是一个矩阵，它标识正在处理的图像中的像素，并定义在处理每个像素时使用的邻域。
在本教程中我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下图是莉娜形象
![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为了做到这一点，我们将使用`mahotas.get_structuring_elem`方法
> 
> **语法:**maho tas . get _ structure _ elem(img，n)
> 
> **自变量:**以图像对象和整数为自变量
> 
> **返回:**返回数字数组

**注意:**输入图像应被过滤或加载为灰色

为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并在索引的帮助下过滤它，下面是这样做的命令

```py
image = image[:, :, 0]
```

下面是实现

```py
# importing required libraries
import mahotas
import mahotas.demos
from pylab import gray, imshow, show
import numpy as np
import matplotlib.pyplot as plt

# loading iamge
img = mahotas.demos.load('lena')

# filtering image
img = img.max(2)

print("Image")

# showing image
imshow(img)
show()

# getting structring element
value = mahotas.get_structuring_elem(img, 1)

# showing value
print(value)
```

**输出:**

```py
Image
```

![](img/70d09905e2642f2eca05005f11577aa5.png)

```py
[[0 1 0]
 [1 1 1]
 [0 1 0]]
```

另一个例子

```py
# importing required libraries
import mahotas
import numpy as np
from pylab import gray, imshow, show
import os
import matplotlib.pyplot as plt

# loading iamge
img = mahotas.imread('dog_image.png')

# fltering image
img = img[:, :, 0]

print("Image")

# showing image
imshow(img)
show()

# getting structring element
value = mahotas.get_structuring_elem(img, 2)

# showing value
print(value)
```

**输出:**

```py
Image
```

![](img/17e2403b430c8a751c7532a030ce355a.png)

```py
[[1 1 1]
 [1 1 1]
 [1 1 1]]
```