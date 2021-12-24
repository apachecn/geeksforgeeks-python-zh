# maho tas–获取图像时刻

> 原文:[https://www . geesforgeks . org/maho tas-get-image-moments/](https://www.geeksforgeeks.org/mahotas-getting-image-moments/)

在这篇文章中，我们将看到如何在 mahotas 中成像时刻。在图像处理、计算机视觉和相关领域中，图像矩是图像像素强度的特定加权平均值，或者是这种矩的函数，通常被选择为具有某种吸引人的特性或解释。图像矩用于描述分割后的物体。

在本教程中我们将使用“lena”图像，下面是加载它的命令。

```
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.moments 方法
> **语法:** mahotas.moments(img，p0，p1)
> **参数:**它以图像对象和两个浮点值作为参数
> **返回:**它返回图像对象

**注意:**输入图像应被过滤或应加载为灰色
为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并借助索引对其进行过滤，下面是这样做的命令

```
image = image[:, :, 0]
```

下面是实现

## 蟒蛇 3

```
# importing required libraries
import mahotas
import mahotas.demos
from pylab import gray, imshow, show
import numpy as np
import matplotlib.pyplot as plt

# loading image
img = mahotas.demos.load('lena')

# filtering image
img = img.max(2)

print("Image")

# showing image
imshow(img)
show()

# Power for first dimension
p0 = 5.5

# Power for second dimension
p1 = 5.5

# getting moments
moment = mahotas.moments(img, p0, p1)

# printing moments
print("Moment value = " + str(moment))
```

**输出:**

```
Image

```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```
Moment value = 6.784986531904299e+35
```

另一个例子

## 蟒蛇 3

```
# importing required libraries
import mahotas
import numpy as np
from pylab import gray, imshow, show
import os
import matplotlib.pyplot as plt

# loading image
img = mahotas.imread('dog_image.png')

# filtering image
img = img[:, :, 0]

print("Image")

# showing image
imshow(img)
show()

# Power for first dimension
p0 = 10.5

# Power for second dimension
p1 = 2.5

# getting moments
moment = mahotas.moments(img, p0, p1)

# printing moments
print("Moment value = " + str(moment))
```

**输出:**

```
Image

```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```
Moment value = 1.5229432312149368e+42
```