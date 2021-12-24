# maho tas–模板匹配

> 原文:[https://www.geeksforgeeks.org/mahotas-template-matching/](https://www.geeksforgeeks.org/mahotas-template-matching/)

在本文中，我们将看到如何在 mahotas 中进行模板匹配。模板基本上是图像的一部分或结构。在本教程中我们将使用“lena”图像，下面是加载它的命令。

```
mahotas.demos.load('lena')
```

下图是莉娜形象

![](img/c6cf4d1584ad896c98148d7fd44b7f25.png)

> 为此，我们将使用 mahotas.template_match 方法
> **语法:** mahotas.template_match(img，template)
> **参数:**它以图像对象和模板为参数
> **返回:**它返回图像对象

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

# template
template = np.array([
            [1, 1, 1],
            [1, 1, 1],
            [1, 1, 1]], bool)

# matching template
new_img = mahotas.template_match(img, template)

# showing image
print("Matched Image")
imshow(new_img)
show()
```

**输出:**

```
Image
```

![](img/7e2a2e3e4e2c7d3717764f78ddb13263.png)

```
Matched Image
```

![](img/673a4657b710aae306d94d96951febea.png)

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
# template
template = np.array([
            [1, 1, 1],
            [1, 1, 1],
            [1, 1, 1]], bool)

# matching template
new_img = mahotas.template_match(img, template)

# showing image
print("Matched Image")
imshow(new_img)
show()
```

**输出:**

```
Image
```

![](img/69c070b367f54d4895c9b3e679a941a7.png)

```
Matched Image
```

![](img/0ce901422dc4e3a6fb2a3f0f7d190ee5.png)