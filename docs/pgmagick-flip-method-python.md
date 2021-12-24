# Pgmagick flip()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-flip-method-python/](https://www.geeksforgeeks.org/pgmagick-flip-method-python/)

**flip()** 函数是 Pgmagick 库中的一个内置函数，用于创建垂直方向的镜像。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> flip()
> ```
> 
> **参数:**该功能不接受任何参数。
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

```py
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke flip() function
img.flip()

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/4d1f34b3df37f71bd179c596f60c1bc1.png)
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

# invoke flip() function
im.flip()

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/09e0107f4c9ae4a3fc628888d7b3212b.png)