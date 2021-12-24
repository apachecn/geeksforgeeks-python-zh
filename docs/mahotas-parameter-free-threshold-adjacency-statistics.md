# maho tas–无参数阈值邻接统计

> 原文:[https://www . geesforgeks . org/maho tas-参数-自由-阈值-邻接-统计/](https://www.geeksforgeeks.org/mahotas-parameter-free-threshold-adjacency-statistics/)

在本文中，我们将看到如何在 mahotas 中获得图像的无参数阈值邻接统计。汉密尔顿等人在《快速自动化细胞表型图像分类》
中介绍了 TAS，在本教程中我们将使用‘lena’图像，下面是加载 Lena 图像的命令

```
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.features.pftas 方法
> **语法:**maho tas . features . pftas(img)
> **参数:**它以图像对象作为参数
> **返回:**它返回一维数组

**注意:**输入图像应被过滤或加载为灰色

为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并在索引的帮助下过滤它，下面是这样做的命令

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

# computing pftas
value = mahotas.features.pftas(img)

# printing value
print(value)
```

**输出:**

```
Image 
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```
[8.40466496e-01 3.96107929e-02 3.32482230e-02 4.78710924e-02
 1.99986198e-02 9.29542475e-03 4.81678283e-03 3.41591333e-03
 1.27665448e-03 8.74954977e-01 3.30841335e-02 2.54587942e-02
 3.93565900e-02 1.67089809e-02 5.66629477e-03 2.56520631e-03
 1.63400128e-03 5.71021954e-04 8.94910256e-01 2.94171187e-02
 2.18929382e-02 3.09704979e-02 1.29246004e-02 5.15770440e-03
 2.69414206e-03 1.49270033e-03 5.40041990e-04 7.95067984e-01
 5.76368630e-02 4.24876742e-02 5.77221625e-02 2.45406623e-02
 1.12339424e-02 7.21633656e-03 3.25844038e-03 8.35934968e-04
 9.01310067e-01 2.80622737e-02 1.99915045e-02 3.05637402e-02
 1.27837749e-02 4.03875587e-03 1.90138423e-03 1.03160208e-03
 3.16897372e-04 8.28594029e-01 4.43179717e-02 3.44044708e-02
 5.11290091e-02 2.25801812e-02 1.03552423e-02 4.92079472e-03
 2.92782150e-03 7.70479341e-04]
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

# computing pftas
value = mahotas.features.pftas(img)

# printing value
print(value)
```

**输出:**

```
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```
[9.09810233e-01 2.60317846e-02 1.97574078e-02 2.77915537e-02
 1.31694722e-02 2.52446879e-03 6.36716463e-04 2.17571455e-04
 6.07920241e-05 9.15640448e-01 2.48822727e-02 1.86702013e-02
 2.63437145e-02 1.18992323e-02 2.02411568e-03 4.07844204e-04
 1.09513721e-04 2.26580113e-05 9.71165298e-01 9.19026798e-03
 6.63816594e-03 8.62583483e-03 3.68366898e-03 5.02318497e-04
 1.13426757e-04 5.40127416e-05 2.70063708e-05 8.33778879e-01
 4.29548185e-02 3.26013800e-02 5.29056931e-02 2.73491801e-02
 7.36566005e-03 1.98765890e-03 8.80608375e-04 1.76121675e-04
 9.00955422e-01 2.52231333e-02 1.89294439e-02 3.21553830e-02
 1.65154923e-02 4.43605931e-03 1.16101879e-03 5.12783301e-04
 1.11264301e-04 9.08750580e-01 2.31333775e-02 1.64857417e-02
 2.92278667e-02 1.50633649e-02 4.92893055e-03 1.33347821e-03
 7.40821225e-04 3.35838955e-04]
```