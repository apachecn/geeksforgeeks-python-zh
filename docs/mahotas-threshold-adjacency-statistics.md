# maho tas–阈值邻接统计

> 原文:[https://www . geesforgeks . org/maho tas-阈值-邻接-统计/](https://www.geeksforgeeks.org/mahotas-threshold-adjacency-statistics/)

在本文中，我们将看到如何在 mahotas 中获得图像的阈值邻接统计特征。汉密尔顿等人在《快速自动化细胞表型图像分类》中提出了 TAS。TAS 给出了原始参数，不像 PFTAS 给出了没有任何硬编码参数的变化。
在本教程中我们将使用‘lena’图像，下面是加载 Lena 图像的命令

```py
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.features.tas 方法
> **语法:**maho tas . features . tas(img)
> **参数:**它以图像对象作为参数
> **返回:**它返回一维数组

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

# computing tas
value = mahotas.features.tas(img)

# printing value
print(value)
```

**输出:**

```py
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```py
[8.18235887e-01 4.96278071e-02 3.85778412e-02 5.42293510e-02
 2.31141496e-02 8.96518478e-03 4.17582280e-03 2.30390223e-03
 7.70054279e-04 8.11830699e-01 5.42434618e-02 3.79106870e-02
 5.78859183e-02 2.54097764e-02 7.40147155e-03 2.98681431e-03
 1.76294893e-03 5.68223210e-04 8.69779571e-01 3.56911714e-02
 2.61354551e-02 4.12780295e-02 1.73316328e-02 5.09194046e-03
 2.56976434e-03 1.52282331e-03 5.99611680e-04 7.43348142e-01
 5.80286091e-02 4.97388078e-02 7.46472685e-02 3.83537568e-02
 1.81614021e-02 1.17267978e-02 4.57940731e-03 1.41580823e-03
 9.37920200e-01 1.55393289e-02 1.20666222e-02 1.87743206e-02
 9.61712375e-03 3.05412151e-03 1.93789436e-03 8.37170364e-04
 2.53218197e-04 9.13099391e-01 2.42303089e-02 1.70045074e-02
 2.72925208e-02 1.13702921e-02 3.81980697e-03 1.62341796e-03
 1.19050651e-03 3.69248007e-04]
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

# computing tas
value = mahotas.features.tas(img)

# printing value
print(value)
```

**输出:**

```py
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```py
[8.92356868e-01 2.75272814e-02 2.05523535e-02 3.43358813e-02
 1.80176597e-02 5.01153448e-03 1.33785553e-03 6.79775240e-04
 1.80791287e-04 8.81674218e-01 3.13932157e-02 2.34006832e-02
 3.69160363e-02 1.95048908e-02 5.11444295e-03 1.23809709e-03
 6.09325269e-04 1.49090226e-04 9.06137850e-01 2.75823883e-02
 2.03761048e-02 2.88661485e-02 1.36743022e-02 2.68646310e-03
 4.75770564e-04 1.39449993e-04 6.15220557e-05 8.35720148e-01
 4.69532212e-02 3.62894953e-02 5.08719737e-02 2.36920394e-02
 4.84714813e-03 1.21050472e-03 2.87238408e-04 1.28231432e-04
 9.38717680e-01 1.80549908e-02 1.33994005e-02 1.87263793e-02
 8.80054720e-03 1.75569656e-03 3.62486722e-04 1.35538513e-04
 4.72808768e-05 9.05435494e-01 2.48433294e-02 1.91342383e-02
 2.97531477e-02 1.52476648e-02 4.03149662e-03 1.02763639e-03
 4.30377634e-04 9.66153873e-05]
```