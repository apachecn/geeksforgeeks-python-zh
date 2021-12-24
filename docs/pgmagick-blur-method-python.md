# Pgmagick blur()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-blur-method-python/](https://www.geeksforgeeks.org/pgmagick-blur-method-python/)

**模糊()**函数是 Pgmagick 库中的一个内置函数，用于向图像添加模糊滤镜。该函数在成功时返回真值。

> **语法:**
> 
> ```
> blur( radius, sigma )
> ```
> 
> **参数:**该函数接受两个参数，如上所述，如下所述:
> 
> *   **半径:**该参数存储模糊半径的值。
> *   **σ:**是存储对象σ的可选参数。
> 
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

```
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke blur function with radius 4 and sigma 6
img.blur(4, 6)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/4bf9a4833b2eeae6890d8252c4335781.png)
**例 2:**

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

# invoke blur function with radius 5 and sigma 8
im.blur(5, 8)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/d6df5e7a0b1833872e17b723c4ce3c65.png)