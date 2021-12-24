# maho tas–重新标记

> 原文:[https://www.geeksforgeeks.org/mahotas-re-labeling/](https://www.geeksforgeeks.org/mahotas-re-labeling/)

在本文中，我们将看到如何在 mahotas 中重新标记标签图像。重新标记用于标记已经标记的图像，这是必需的，因为有时会有用户删除的标签，所以当图像被重新标记时，我们也会获得新的标签号。我们使用 mahotas.label 方法来标记图像
为此，我们将使用来自核分割基准的荧光显微图像。我们可以借助下面给出的命令
获得图像

```py
mhotas.demos.nuclear_image()
```

下图是核 _ 图像

![](img/2d9f2099be91821b3aa41b61a692af29.png)

**标记图像**是整数图像，其中的值对应于不同的区域。也就是说，区域 1 是值为 1 的所有像素，区域 2 是值为 2 的像素，以此类推
为了做到这一点，我们将使用 mahotas.relabel 方法

> **语法:** mahotas.relabel(被标记)
> **参数:**它以被标记的图像对象作为参数
> **返回:**它返回被标记的图像和整数，即标签的数量

**例 1:**

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

# printing number of labels
print("Count : " + str(n_nucleus))

# showing the labelled image
print("Labelled Image")
imshow(labelled)
show()

# removing border labels
labelled = mh.labelled.remove_bordering(labelled)

# relabling the labelled image
relabelled, n_left = mahotas.labelled.relabel(labelled)

# showing number of labels
print("Count : " + str(n_left))

# showing the image
print("No border Label")
imshow(relabelled)
show()
```

**输出:**

![](img/d53268cba824f9594c5c4b716241b7bf.png)

**例 2:**

## 蟒蛇 3

```py
# importing required libraries
import numpy as np
import mahotas
from pylab import imshow, show

# loading image
img = mahotas.imread('dog_image.png')

# filtering the image
img = img[:, :, 0]

# setting gaussian filter
gaussian = mahotas.gaussian_filter(img, 15)

# setting threshold value
gaussian = (gaussian > gaussian.mean())

# creating a labelled image
labelled, n_nucleus = mahotas.label(gaussian)

# printing number of labels
print("Count : " + str(n_nucleus))

print("Labelled Image")
# showing the gaussian filter
imshow(labelled)
show()

# removing border labels
labelled = mh.labelled.remove_bordering(labelled)

# relabling the labelled image
relabelled, n_left = mahotas.labelled.relabel(labelled)

# showing number of labels
print("Count : " + str(n_left))

# showing the image
print("No border Label")
imshow(relabelled)
show()
```

**输出:**

![](img/fd23165fe454c0b2fb51b8913b606fe8.png)