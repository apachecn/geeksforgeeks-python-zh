# Pgmagick wave()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-wave-method-python/](https://www.geeksforgeeks.org/pgmagick-wave-method-python/)

**wave()** 函数是 Pgmagick 库中的一个内置函数，用于随着正弦波改变图像。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> wave(amplitude, wavelength)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，如下所述:
> 
> *   **振幅:**该参数存储正弦波的振幅值。
> *   **波长:**该参数存储正弦波的波长值。
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

# invoke wave function with amplitude 5 and wavelength 8
img.wave(5, 8)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/08c13b56d9e1129e3cf573d118d45e42.png)
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

# invoke wave function with amplitude 15 and wavelength 18
im.wave(15, 18)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/8b7b4642bec977af2d0018f18e9df3e3.png)