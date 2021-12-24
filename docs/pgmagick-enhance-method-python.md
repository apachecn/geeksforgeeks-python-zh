# Pgmagick 增强()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-enhance-method-python/](https://www.geeksforgeeks.org/pgmagick-enhance-method-python/)

**增强()**功能是 Pgmagick 库中的一个内置功能，用于应用数字滤波器来增强有噪声的图像。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> enhance()
> ```
> 
> **参数:**此功能不接受任何参数。
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**
![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

```py
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke contrast() function
img.enhance()

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/5580935d32f03afc40ce7efc6ddec367.png)
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

# invoke contrast() function
im.enhance()

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/f9695dd23cafa8a12ec47dc810aaa580.png)