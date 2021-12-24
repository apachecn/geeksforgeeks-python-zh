# maho tas–标记区域的大小

> 原文:[https://www . geeksforgeeks . org/maho tas-size-of-labed-region/](https://www.geeksforgeeks.org/mahotas-sizes-of-labeled-region/)

在本文中，我们将看到如何在 mahotas 中获得标记区域的大小。标记图像是整数图像，其中的值对应于不同的区域。即，区域 1 是具有值 1 的所有像素，区域 2 是具有值 2 的像素，以此类推。按照惯例，区域 0 是背景，通常处理方式不同。我们可以在 mahotas.label 方法的帮助下创建一个标记区域。
为了做到这一点，我们将使用 mahotas.label_size 方法

> **语法:**maho tas . taged _ size(taged _ region)
> **参数:**以 numpy.ndarray 对象为参数，即 taged region
> **返回:**返回整数列表

**例 1:**

## 蟒蛇 3

```py
# importing required libraries
import mahotas as mh
import numpy as np
from pylab import imshow, show

# creating region
# numpy.ndarray
regions = np.zeros((10, 10), bool)

# setting 1 value in the region
regions[1, 1] = 1
regions[6, 6] = 1
regions[4, 4] = 1
regions[9, 9] = 1

# getting labelled function
labelled, nr_objects = mh.label(regions)

# showing the image with interpolation = 'nearest'
imshow(labelled, interpolation ='nearest')
show()

# getting sizes of labelled region
sizes = mh.labelled.labelled_size(labelled)

# printing sizes
for i in range(len(sizes)):

    print("Size of region " + str(i) + " : " + str(sizes[i]))

```

**输出:**

![](img/e77ab204fea85d238271943607b67a6c.png)

```py
Size of region 0 : 96
Size of region 1 : 1
Size of region 2 : 1
Size of region 3 : 1
Size of region 4 : 1
```

**例 2:**

## 蟒蛇 3

```py
# importing required libraries
import mahotas as mh
import numpy as np
from pylab import imshow, show

# creating region
# numpy.ndarray
regions = np.zeros((10, 10), bool)

# setting 1 value to the region
regions[:3, :3] = 1
regions[6:, 6:] = 1

# getting labelled function
labelled, nr_objects = mh.label(regions)

# showing the image with interpolation = 'nearest'
imshow(labelled, interpolation ='nearest')
show()

# getting sizes of labelled region
sizes = mh.labelled.labelled_size(labelled)

# printing sizes
for i in range(len(sizes)):

    print("Size of region " + str(i) + " : " + str(sizes[i]))

```

**输出:**

![](img/26ff25b3a8086b6c0ada8fd91567f31a.png)

```py
Size of region 0 : 75
Size of region 1 : 9
Size of region 2 : 16
```