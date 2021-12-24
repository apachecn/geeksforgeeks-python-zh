# maho tas–图像椭圆轴

> 哎哎哎:# t0]https://www . geeksforgeeks . org/mahotas-image-ellipse-axes/

在本文中，我们将看到如何在 mahotas 中获得图像椭圆轴。椭圆 exe 是图像椭圆的参数，与原始图像具有相同质量和二阶矩的恒定强度椭圆的参数。
在本教程中我们将使用‘lena’图像，下面是加载 Lena 图像的命令

```py
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.features.ellipse_axes 方法
> **语法:**maho tas . features . ellipse _ axes(img)
> **参数:**它将图像对象作为参数
> **返回:**它返回两个浮点值

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

# computing Parameters of the ‘image ellipse’
semimajor, semiminor = mahotas.features.ellipse_axes(img)

# showing value
print("Semi Major Exes : " + str(semimajor))
print("Semi Minor Exes : " + str(semiminor))
```

**输出:**

```py
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```py
Semi Major Exes : 295.60277400592844
Semi Minor Exes : 295.60277400592844
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

# fltering image
img = img[:, :, 0]

print("Image")

# showing image
imshow(img)
show()
# computing Parameters of the ‘image ellipse’
semimajor, semiminor = mahotas.features.ellipse_axes(img)

# showing value
print("Semi Major Exes : " + str(semimajor))
print("Semi Minor Exes : " + str(semiminor))
```

**输出:**

```py
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```py
Semi Major Exes : 508.79612573247636
Semi Minor Exes : 308.5809619544451
```