# Pgmagick write()方法–Python

> 原文:[https://www.geeksforgeeks.org/pgmagick-write-method-python/](https://www.geeksforgeeks.org/pgmagick-write-method-python/)

**write()** 函数是 Pgmagick 库中的一个内置函数，用于写入中间图像。当前图像被写入指定的文件名，然后使用该图像继续处理。

> **语法:**
> 
> ```
> write(filename)
> ```
> 
> **参数:**该函数接受上面提到的、下面定义的单个参数:
> 
> *   **文件名:**此参数用于指定已处理图像的名称。
> 
> **返回值:**该函数返回 Pgmagick 对象。

**例 1:**

```
from pgmagick import Image, DrawableCircle, DrawableText
from pgmagick import Geometry, Color

# draw the image of dimension 600 * 600
img = Image((600, 600), "gradient:# ffffff-# 12323e")

# invoke write function along with filename
img.write('1_a.png')
```

**输出:**
![](img/7fd9e25cace534fdb19ee301f75e50b0.png)
**例 2:**

```
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

# invoke write function along with filename
im.write('1_b.png')
```

**输出:**
![](img/17adb48a112ad99eda419908a1a89836.png)
**参考:**

*   [http://www.graphicsmagick.org/Magick++/](http://www.graphicsmagick.org/Magick++/)