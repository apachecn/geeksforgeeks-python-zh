# maho tas–图像的圆度

> 原文:[https://www.geeksforgeeks.org/mahotas-roundness-of-image/](https://www.geeksforgeeks.org/mahotas-roundness-of-image/)

在本文中，我们将了解如何在 mahotas 中获取图像的圆度特征。圆度是由形状的主要特征决定的，而不是它的边缘和角的定义，或者制造的物体的表面粗糙度。一个光滑的椭圆可以有低圆度，如果它的偏心率很大
对于这个教程我们将使用‘lena’图像，下面是加载 Lena 图像的命令

```py
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为了做到这一点，我们将使用 mahotas.features .圆度方法
> **语法:** mahotas.features .圆度(img)
> **参数:**它以图像对象作为参数
> **返回:**它返回浮点值

**注意:**输入图像应该被过滤或者应该被加载为灰色
为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并借助索引对其进行过滤，下面是这样做的命令

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
import matplotlib.pyplot as plt

# loading image
img = mahotas.demos.load('lena')

# filtering image
img = img.max(2)

print("Image")

# showing image
imshow(img)
show()

# computing roundness in image
value = mahotas.features.roundness(img)

# printing value
print("Roundness : " + str(value))
```

**输出:**

```py
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```py
Roundness : 0.0
```

另一个例子

## 蟒蛇 3

```py
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

# computing roundness in image
value = mahotas.features.roundness(img)

# printing value
print("Roundness : " + str(value))
```

**输出:**

```py
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```py
Roundness : 0.04297201733896709
```