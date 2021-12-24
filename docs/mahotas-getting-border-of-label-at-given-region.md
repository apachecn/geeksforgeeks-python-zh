# maho tas–获取给定区域的标签边界

> 原文:[https://www . geeksforgeeks . org/maho tas-在给定区域获取标签边界/](https://www.geeksforgeeks.org/mahotas-getting-border-of-label-at-given-region/)

在本文中，我们将看到如何在 mahotas 中的给定区域内获得标签图像中标签的边界。为此，我们将使用来自核分割基准的荧光显微图像。我们可以借助下面给出的命令
获得图像

```py
mhotas.demos.nuclear_image()
```

下图是核 _ 图像

![](img/2d9f2099be91821b3aa41b61a692af29.png)

为了做到这一点，我们将使用标记边界法

> **语法:**maho tas . label . border(label _ image，I，j)
> **参数:**它以 numpy.ndarray 对象即标签图像和两个整数作为参数
> 注意:如果一个像素具有值 I(或 j)
> **则该像素位于边框上返回:**它返回 numpy.ndarray 对象即带有边框标签的标签图像

**注意:**的输入应该是标记为
的过滤后的图像对象，为了过滤图像，我们将获取 numpy.ndarray 的图像对象，并借助索引对其进行过滤，下面是执行此操作的命令

```py
image = image[:, :, 0]
```

**例 1 :**

## 蟒蛇 3

```py
# importing required libraries
import mahotas
import numpy as np
from pylab import imshow, show
import os

# loading nuclear image
f = mahotas.demos.load('nuclear')

# setting filter to the image
f = f[:, :, 0]

# setting gaussian filter
f = mahotas.gaussian_filter(f, 4)

# setting threshold value
f = (f> f.mean())

# creating a labelled image
labelled, n_nucleus = mahotas.label(f)

# showing the labelled image
print("Labelled Image")
imshow(labelled)
show()

# getting border for label at given point
relabeled = mahotas.labelled.border(labelled, 0, 20)

# showing the image
print("Labels With borders at given point")
imshow(relabelled)
show()
```

**输出:**

![](img/beca481483ce21e51233c18768eb4919.png)

**例 2 :**

## 蟒蛇 3

```py
# importing required libraries
import numpy as np
import mahotas
from pylab import imshow, show

# loading image
img = mahotas.imread('dog_image.png')

# filtering the imagwe
img = img[:, :, 0]

# setting gaussian filter
gaussian = mahotas.gaussian_filter(img, 15)

# setting threshold value
gaussian = (gaussian > gaussian.mean())

# creating a labelled image
labelled, n_nucleus = mahotas.label(gaussian)

print("Labelled Image")
# showing the gaussian filter
imshow(labelled)
show()

# getting border for label at given point
relabeled = mahotas.labelled.border(labelled, 1, 0)

# showing the image
print("Labels With borders at given point")
imshow(relabelled)
show()
```

**输出:**

![](img/7851e3d9f57fc3afd37b7761a1687fee.png)