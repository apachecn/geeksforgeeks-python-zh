# Pgmagick edge()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-edge-method-python/](https://www.geeksforgeeks.org/pgmagick-edge-method-python/)

**edge()** 函数是 Pgmagick 库中的一个内置函数，用于应用卷积滤波器来检测边缘。

> **语法:**
> 
> ```
> edge(radius)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **半径:**该参数存储检测滤光片的孔径。
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

# invoke despeckle() function
img.edge(0.7)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/d0a8a08ebce4da9a9c6179a991a7180c.png)
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

# invoke despeckle() function
im.edge(0.4)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/9c01278de7008b86ec062cbaa9b7aecd.png)