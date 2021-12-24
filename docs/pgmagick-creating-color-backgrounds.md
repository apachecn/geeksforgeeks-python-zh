# pgmagick|创建彩色背景

> 原文:[https://www . geesforgeks . org/pgmagick-creating-color-backgrounds/](https://www.geeksforgeeks.org/pgmagick-creating-color-backgrounds/)

在本文中，我们将学习如何创建纯色背景。我们可以在输出图像背景中使用这些背景。此外，我们将如何创建透明和带有颜色梯度的背景。
**为例:**
![](img/6b615c2b2cee397058eb842cde1aad87.png)

在上面的图片中，绿色为我们提供了 GeeksforGeeks 徽标的背景颜色，所以让我们从代码开始。

**1。实心背景:**
现在让我们创建一个带有实心绿色的背景。
T4【代码:

```
from pgmagick.api import Image

img = Image((300, 300), 'green')
img.write('green.jpg')
```

**输出:**
![](img/4281cc5d66b693f2fb64c01e432e3b22.png)

**2。透明背景:**
现在让我们创建一个透明背景。
T4【代码:

```
from pgmagick.api import Image

img = Image((300, 300), 'transparent')
img.write('transparent.jpg')
```

**输出:**
![](img/4ff06ac6d111f9c2732069373dc91a3b.png)

**2。渐变背景:**
现在让我们创建一个带有一些颜色渐变的背景。
T4【代码:

```
from pgmagick.api import Image

img = Image((300, 200), 'gradient:# 318749-# 0eed4c')
img.write('gradient.jpg')
```

**输出:**

![](img/e96a891abec03ba4107c39fabf09137f.png)