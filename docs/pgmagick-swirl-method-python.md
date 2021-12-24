# Pgmagick 漩涡()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-swirl-method-python/](https://www.geeksforgeeks.org/pgmagick-swirl-method-python/)

**漩涡()**函数是 Pgmagick 库中的一个内置函数，用于围绕图像的中心旋转。度数指定漩涡的紧密度。

> **语法:**
> 
> ```
> swirl(angle)
> ```
> 
> **参数:**该功能接受如上所述的单个参数，描述如下:
> 
> *   **角度:**该参数存储涡流的角度。
> 
> **返回值:**该函数返回添加了图像的 Pgmagick 对象。

**输入图像:**

![](img/4a43a98e9c0ff6dd3018f90f150a2a76.png)

**例 1:**

## 蟒蛇 3

```
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image('input.png')

# invoke swirl function with angle 30
img.swirl(30)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**

![](img/c17e4da022389378ee30f8edb3086da8.png)

**例 2:**

## 蟒蛇 3

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

# invoke swirl function with angle 80
im.swirl(80)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**

![](img/cc4f09c0e0eac907c1c7f1e95d071e54.png)