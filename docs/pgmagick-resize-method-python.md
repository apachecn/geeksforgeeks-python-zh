# Pmagick resize()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-resize-method-python/](https://www.geeksforgeeks.org/pgmagick-resize-method-python/)

**resize()** 函数是 Pgmagick 库中的一个内置函数，用于调整图像的大小。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> resize('widthxheight')
> ```
> 
> **参数:**这个函数接受宽度和高度的字符串，格式为‘width xh8’，描述最终图像的尺寸。
> 
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**Example 1:**

```py
# import library
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import  Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke resize() function
img.resize('100x100')

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/42cd18e16ace5e3b899721a5fbd1f41a.png)

**例 2:**

```py
# import library
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import  Geometry, Color

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

# invoke resize() function
im.resize('500x500')

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/f68e6a7cfb609d039bb91254766ff8b3.png)