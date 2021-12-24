# Pgmagick flop()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-flop-method-python/](https://www.geeksforgeeks.org/pgmagick-flop-method-python/)

**触发器()**函数是 Pgmagick 库中的一个内置函数，用于创建水平方向的镜像。该函数在成功时返回真值。

> **语法:**
> 
> ```
> flip()
> ```
> 
> **参数:**该功能不接受任何参数。
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

```
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke flop() function
img.flop()

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/582cc4cd4e33b68d1f428a1f06da3891.png)
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

# invoke flop() function
im.flop()

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/d46959a9b80b6c4499ebe8ca85c79f19.png)