# Pgmagick gamma()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-gamma-method-python/](https://www.geeksforgeeks.org/pgmagick-gamma-method-python/)

**伽马()**函数是 Pgmagick 库中的一个内置函数，用于水平伽马校正。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> gamma(red, green, blue)
> ```
> 
> **参数:**该功能接受红、绿、蓝三个参数，分别修正红、绿、蓝三种颜色的伽玛等级。
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

# invoke gamma() function
img.gamma(1, 3.4, 6) 

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/3e15af048c6e61da753f3e86b7e00c50.png)
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

# invoke gamma() function
im.gamma(3, 45, 10) 

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/a8669ffca5c420afd04a031989b7285a.png)