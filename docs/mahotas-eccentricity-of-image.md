# maho tas–图像偏心

> 原文:[https://www . geesforgeks . org/maho tas-图像偏心/](https://www.geeksforgeeks.org/mahotas-eccentricity-of-image/)

在本文中，我们将看到如何在 mahotas 中获得图像的偏心。偏心测量从给定顶点 v 到连通图的任何其他顶点 w 的最短路径长度。为每个顶点 v 计算，它将图的连通性结构转换成一组值。对于数字图像的连通区域，它是通过其邻域图和给定的度量来定义的。

```
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为了做到这一点，我们将使用 maho tas . features . exception(方法
> **语法:**maho tas . features . exception(img)
> **参数:**它将图像对象作为参数
> **返回:**它返回浮点值

**注意:**输入图像应该被过滤或者应该被加载为灰色
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

# computing eccentricity value
value = mahotas.features.eccentricity(img)

# showing value
print("Eccentricity value = " + str(value))
```

**输出:**

```
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```
Eccentricity value = 0.0
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

# computing eccentricity value
value = mahotas.features.eccentricity(img)

# showing value
print("Eccentricity value = " + str(value))
```

**输出:**

```
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```
Eccentricity value = 0.7950893156644899
```