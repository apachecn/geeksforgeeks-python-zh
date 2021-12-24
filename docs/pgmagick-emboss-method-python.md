# Pmagick 浮雕()方法–Python

> 原文:[https://www . geeksforgeeks . org/pgmagick-浮雕-方法-python/](https://www.geeksforgeeks.org/pgmagick-emboss-method-python/)

**浮雕()**函数是 Pgmagick 库中的一个内置函数，用于浮雕图像，这意味着图像的每个像素都被替换以产生 3D 效果。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> emboss(radius)
> ```
> 
> **参数:**该功能接受如上所述的单个参数，描述如下:
> 
> *   **半径:**该参数存储用于指定压花半径的半径。
> 
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

```py
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke emboss() function
img.emboss(3)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/14a6ea5d77237c84f4347d076301fe61.png)
**例 2:**

```py
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

# invoke emboss() function
im.emboss(4)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/27cbfef76701f7d486c879beda2fe617.png)