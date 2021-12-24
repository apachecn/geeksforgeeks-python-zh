# maho tas–加速鲁棒特性

> 原文:[https://www . geesforgeks . org/maho tas-speed-up-robust-features/](https://www.geeksforgeeks.org/mahotas-speeded-up-robust-features/)

在本文中，我们将看到如何在 mahotas 中获得加速的稳健图像特征。在计算机视觉中，加速鲁棒特征是一种专利的局部特征检测器和描述符。它可用于对象识别、图像配准、分类或三维重建等任务。它部分地受到尺度不变特征变换描述符的启发。为此，我们将使用来自核分割基准的荧光显微图像。我们可以借助下面给出的命令
获得图像

```py
mahotas.demos.nuclear_image()
```

下图是核 _ 图像

![](img/2d9f2099be91821b3aa41b61a692af29.png)

为此，我们将使用 surf.surf 方法

> **语法:** surf.surf(img)
> **自变量:**它以图像对象为自变量
> **返回:**它返回 numpy.ndarray

**例 1 :**

## 蟒蛇 3

```py
# importing various libraries
import mahotas
import mahotas.demos
import mahotas as mh
import numpy as np
from pylab import imshow, show
from mahotas.features import surf

# loading nuclear image
nuclear = mahotas.demos.nuclear_image()

# filtering image
nuclear = nuclear[:, :, 0]

# adding gaussian filter
nuclear = mahotas.gaussian_filter(nuclear, 4)

# showing image
print("Image")
imshow(nuclear)
show()

# getting Speeded-Up Robust Features
spoints = surf.surf(nuclear)
print("No of  points: {}".format(len(spoints)))
```

**输出:**

![](img/598c4a65961462244a1fa7ca90ec2a9b.png)

```py
No of  points: 217
```

**例 2 :**

## 蟒蛇 3

```py
# importing required libraries
import numpy as np
import mahotas
from pylab import imshow, show
from mahotas.features import surf

# loading image
img = mahotas.imread('dog_image.png')

# filtering the image
img = img[:, :, 0]

# setting gaussian filter
gaussian = mahotas.gaussian_filter(img, 5)

# showing image
print("Image")
imshow(gaussian)
show()

# getting Speeded-Up Robust Features
spoints = surf.surf(gaussian)
print("No of  points: {}".format(len(spoints)))
```

**输出:**

![](img/470b82393697c679336d8ffcdabf2b59.png)

```py
No of  points: 364
```