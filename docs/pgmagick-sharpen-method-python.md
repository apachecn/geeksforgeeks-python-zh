# Pmagick 锐化()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-锐化-方法-python/](https://www.geeksforgeeks.org/pgmagick-sharpen-method-python/)

**锐化()**函数是 Pgmagick 库中的一个内置函数，用于锐化图像。它使用给定半径和标准偏差(σ)的高斯算子。

> **语法:**
> 
> ```
> sharpen( radius, sd )
> ```
> 
> **参数:**该函数接受两个参数，如上所述，如下所述:
> 
> *   **半径:**该参数存储锐度的半径值。
> *   **sd:** 是存储图像标准差的可选参数。
> 
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
# invoke sharpen function with radius 10 and standard deviation as 5
img.sharpen(10, 13)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**

![](img/c5069484ee3a8c2edcd8ebb692b13aff.png)

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

# invoke sharpen function with radius as 9
im.sharpen(9)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**

![](img/bc56bcca0440b8749e8c4c1e6f67a4d1.png)