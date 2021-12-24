# Pgmagick shade()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-shade-method-python/](https://www.geeksforgeeks.org/pgmagick-shade-method-python/)

**阴影()**功能是 Pgmagick 库中的一个内置功能，用于使用远距离光源对图像进行阴影处理。该函数在成功时返回真值。

> **语法:**
> 
> ```py
> shade( azimuthal angle, elevation angle )
> ```
> 
> **参数:**该函数接受两个参数，如上所述，如下所述:
> 
> *   **方位角:**该参数存储方位角的值。
> *   **仰角:**该参数存储仰角的值。
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

# invoke shade function with azimuthal angle as 45 and angle of elevation as 90
img.shade(45, 90)

# invoke write function along with filename
img.write('2_a.png')
```

**输出:**
![](img/42b5dc9a67c10c61520d053c7392e103.png)
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

# invoke shade function with azimuthal angle as 30 and angle of elevation as 10
im.shade(30, 10)

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/8eb3321cdf4d5a231b7e484aa11fb611.png)