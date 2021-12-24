# maho tas–调整图像大小

> 原文:[https://www.geeksforgeeks.org/mahotas-resizing-image/](https://www.geeksforgeeks.org/mahotas-resizing-image/)

在本文中，我们将看到如何在 mahotas 中调整图像的大小。当您将图像从一个像素网格调整到另一个像素网格时，就会发生图像插值。当您需要增加或减少像素总数时，需要调整图像大小，而当您校正镜头失真或旋转图像时，可能会发生重新映射。
在本教程中我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.imresize 方法
> **语法:** mahotas.imresize(img，size)
> **参数:**它以图像对象和新大小作为参数
> **返回:**它返回图像对象

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

# resizing image
new_img = mahotas.imresize(img, [200, 250])

# showing image
print("Resized Image")
imshow(new_img)
show()
```

**输出:**

```py
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```py
Resized Image
```

![](img/b64d9db3c17e37f389b73d658de20914.png)

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

# resizing image
new_img = mahotas.imresize(img, [200, 200])

# showing image
print("Resized Image")
imshow(new_img)
show()
```

**输出:**

```py
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```py
Resized Image
```

![](img/6fbb51bfa8e0dd41610a3841832cf175.png)