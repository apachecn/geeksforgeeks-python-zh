# Pgmagick 内爆()方法–Python

> 原文:[https://www . geeksforgeeks . org/pgmagick-inter decd-method-python/](https://www.geeksforgeeks.org/pgmagick-implode-method-python/)

**内爆()**函数是 Pgmagick 库中的一个内置函数，用于内爆中心周围的图像像素。该函数在成功时返回真值。

> **语法:**
> 
> ```
> implode(factor)
> ```
> 
> **参数:**该功能接受如上所述的单个参数，描述如下:
> 
> *   **因子:**该参数用于指定图像需要围绕中心内爆图像像素的因子。
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

# invoke implode() function
img.implode(4)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/75a7cb5729fc00c079506c730348785a.png)
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

# set font size to 40p
im.fontPointsize(40)

# invoke DrawableText() function
text = DrawableText(250, 450, "GeeksForGeeks")

# invoke draw() function
im.draw(text)

# invoke implode() function
im.implode(8)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/fac027bb9394c18a7b92a95d38eaffd4.png)