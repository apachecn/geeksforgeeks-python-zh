# Pmagick despeckle()方法–Python

> 原文:[https://www . geesforgeks . org/pgmagick-despeckle-method-python/](https://www.geeksforgeeks.org/pgmagick-despeckle-method-python/)

**去斑点()**函数是 Pgmagick 库中的一个内置函数，用于减少图像中的斑点。该函数返回成功的真实值。

> **语法:**
> 
> ```
> emboss(radius)
> ```
> 
> **参数:**此功能不接受任何参数。
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

# invoke despeckle() function
img.despeckle()

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**

![](img/5faea72a05f5ff005b80ef6c41bf1e7e.png)

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

# invoke despeckle() function
im.deskpeckle()

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**

![](img/da2f4fbb63d16639f8eb7c216d7ade2b.png)