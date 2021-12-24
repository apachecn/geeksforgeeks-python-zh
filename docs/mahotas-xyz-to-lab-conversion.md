# 马霍斯-XYZ 到实验室的转换

> 原文:[https://www . geesforgeks . org/maho tas-XYZ-to-lab-conversion/](https://www.geeksforgeeks.org/mahotas-xyz-to-lab-conversion/)

在本文中，我们将看到如何在 mahotas 中将 xyz 图像转换为 rgb 图像。Xyz 是一个基于眼睛如何解释光刺激的附加颜色空间。与其他像 rgb 这样的附加 Rgb 不同，Xyz 是一个纯粹的数学空间，主要成分是“想象的”，这意味着我们不能通过照射代表 x、y 和 z 的任何种类的光来创建物理中所代表的颜色。CIELAB 颜色空间(也称为 CIE L*a*b*或有时简称为“LAB”颜色空间)是由国际照明委员会(CIE)在 1976 年定义的颜色空间..我们使用 mahotas.colors.rgb2xyz 方法将 rgb 图像转换为 xyz 图像。

在本教程中我们将使用“lena”图像，下面是加载它的命令。

```py
mahotas.demos.load('lena')
```

下面是莉娜的形象

![](img/f013f576026c96925a69f4df10464384.png)

为此，我们将使用 mahotas.colors.xyz2labmethod

> **语法:**maho tas . colors . XYZ 2 lab(img)
> **参数:**它以图像对象作为参数
> **返回:**它返回图像对象

下面是实现

## 蟒蛇 3

```py
# importing required libraries
import mahotas
import mahotas.demos
from pylab import gray, imshow, show
import numpy as np

# loading image
img = mahotas.demos.load('lena')

# rgb to xyz
xyz_img = mahotas.colors.rgb2xyz(img)

# showing new image
print("Image")
imshow(xyz_img)
show()

# getting lab image
new_img = mahotas.colors.xyz2lab(xyz_img)

# showing image
print("New Image")
imshow(new_img)
show()
```

**输出:**

```py
Image
```

![](img/7cf201311981e4f8833b39b2801fb8f2.png)

```py
New Image
```

![](img/ce2488a6f2e43b8eae836dfa56da9a36.png)

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

# filtering image
img = img[:, :, :3]

# rgb to xyz
xyz_img = mahotas.colors.rgb2xyz(img)

# showing new image
print("Image")
imshow(xyz_img)
show()

# getting lab image
new_img = mahotas.colors.xyz2lab(xyz_img)

# showing image
print("New Image")
imshow(new_img)
show()
```

**输出:**

```py
Image 
```

![](img/cd18498249beb046ad0843904234da00.png)

```py
New Image
```

![](img/43e9ea8b8b609ef2cfe6d47d661d5af3.png)