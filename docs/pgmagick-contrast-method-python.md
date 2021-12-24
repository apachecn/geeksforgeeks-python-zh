# Pgmagick 对比度()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-contrast-method-python/](https://www.geeksforgeeks.org/pgmagick-contrast-method-python/)

**对比度()**功能是 Pgmagick 库中的一个内置功能，用于增强或降低图像的对比度。该函数在成功时返回真值。

> **语法:**
> 
> ```
> contrast(multiplier)
> ```
> 
> **参数:**该函数接受单个参数乘数，即图像对比度应增加或减少的因子。
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**

![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

## 蟒蛇 3

```
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke contrast() function
img.contrast(27)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**

![](img/762234a28b19987ebcf908de262bd733.png)

**例 2:**

## 蟒蛇 3

```
# import library
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# Draw image of dimension 600 * 600 having background green
im = Image(Geometry(600, 600), Color("# 32CD32"))

# invoke DrawableCircle() function
circle = DrawableCircle(100, 100, 300, 20)

# invoke draw() function
im.draw(circle)

# set font size to 40px
im.fontPointsize(40)

# invoke DrawableText() function
text = DrawableText(250, 450, "GeeksForGeeks")

# invoke draw() function
im.draw(text)

# invoke contrast() function
im.contrast(40)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**

![](img/5c06aaef0cb86d4709b0afd3e0a1b266.png)