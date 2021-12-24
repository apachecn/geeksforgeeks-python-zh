# 马霍塔斯–泽尼克特色

> 原文:[https://www.geeksforgeeks.org/mahotas-zernike-features/](https://www.geeksforgeeks.org/mahotas-zernike-features/)

在本文中，我们将看到如何在 mahotas 中获得给定图像的 zernike 特征。Zernike 多项式是一个正交基集(任意一对函数乘积的积分为零的一组函数)
在本教程中我们将使用‘lena’图像，下面是加载 Lena 图像的命令

```
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.features.zernike 方法
> **语法:**maho tas . features . Zernike(img，度数，半径)
> **参数:**它以图像对象和两个整数作为参数
> **返回:**它返回一维数组

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

# degree
degree = 10

# radius
radius = 10

# computing zernike feature
value = mahotas.features.zernike(img, degree, radius)

# printing value
print(value)
```

**输出:**

```
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```
[0.31830989 0.01261485 0.00614926 0.00769591 0.0097145  0.01757332
 0.00617458 0.01008905 0.01415304 0.01099679 0.02894761 0.01838737
 0.0074247  0.01333135 0.01958184 0.00431827 0.00540781 0.01675913
 0.03511082 0.00699177 0.00357231 0.01593838 0.01621848 0.0240565
 0.0154929  0.01631347 0.03239474 0.02506811 0.00796528 0.01291179
 0.01198231 0.01916542 0.0165929  0.01032658 0.02028499 0.02506003]
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

# degree
degree = 10

# radius
radius = 10

# computing zernike feature
value = mahotas.features.zernike(img, degree, radius)

# printing value
print(value)
```

**输出:**

```
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```
[0.31830989 0.00985427 0.00714652 0.00171408 0.00442245 0.01796711
 0.00716781 0.00179965 0.0039829  0.0031081  0.02447476 0.0011686
 0.009291   0.00174885 0.00357579 0.00692029 0.0043969  0.03528869
 0.00264739 0.01381883 0.00750501 0.0036528  0.00867514 0.01298398
 0.0129556  0.00602334 0.04108562 0.00377269 0.01859098 0.01109795
 0.00178511 0.0082474  0.01928068 0.01873102 0.00882483 0.04558572]
```