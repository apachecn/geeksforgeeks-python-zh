# maho tas–图像上的关闭过程

> 原文:[https://www . geesforgeks . org/maho tas-closing-process-on-image/](https://www.geeksforgeeks.org/mahotas-closing-process-on-image/)

在本文中，我们将看到如何在 mahotas 中对图像执行关闭操作。闭合是首先执行扩张操作然后执行侵蚀操作的过程。它从获得的图像中消除了小孔，用于平滑轮廓和融合狭窄的断裂。

在本教程中我们将使用“luispedro”图像，下面是加载它的命令。

```py
mahotas.demos.load('luispedro')
```

下面是路易斯德罗的照片

![](img/a5b38a36a4a2b449bce4b0f49291011e.png)

为此，我们将使用 mahotas.morph.closemethod

> **语法:**maho tas . morph . close(image)
> **自变量:**它以图像对象为自变量
> **返回:**它返回图像对象

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
luispedro = mahotas.demos.load('luispedro')

# filtering image
luispedro = luispedro.max(2)

# otsu method
T_otsu = mahotas.otsu(luispedro)

# image values should be greater than otsu value
img = luispedro > T_otsu

print("Image threshold using Otsu Method")

# showing image
imshow(img)
show()

# closing image
new_img = mahotas.morph.close(img)

# showing new image
print("Closed Image")
imshow(new_img)
show()
```

**输出:**

```py
Image threshold using Otsu Method 
```

![](img/73600c310d2709aae2e00e9b3837048f.png)

```py
Closed Image
```

![](img/2370b0fcb8731bf7081e0545081bf4e8.png)

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

# setting filter to the image
img = img[:, :, 0]

# otsu method
T_otsu = mahotas.otsu(img)

# image values should be greater than otsu value
img = img > T_otsu

print("Image threshold using Otsu Method")

# showing image
imshow(img)
show()

# closing image
new_img = mahotas.morph.close(img)

# showing new image
print("Closed Image")
imshow(new_img)
show()
```

**输出:**

```py
Image threshold using Otsu Method 
```

![](img/4d8a759cb27087644c89f718a86a41f1.png)

```py
Closed Image
```

![](img/72b938e37ea803bd558f1ce1e4223b18.png)