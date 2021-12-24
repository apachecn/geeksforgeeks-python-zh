# PyCairo–我们如何获得片段范围？

> 原文:[https://www . geeksforgeeks . org/py cairo-我们如何获取剪辑范围/](https://www.geeksforgeeks.org/pycairo-how-we-can-get-clip-extents/)

在本文中，我们将学习如何使用 python 中的 PyCairo 获取片段范围。该模块计算用户坐标中覆盖当前剪辑内区域的边界框。当前剪辑遮挡了对曲面的任何更改。

Pycairo 是一个 Python 模块，为 cairo 图形库提供绑定。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

SVG 代表可缩放矢量图形。它基本上以 XML 格式定义基于矢量的图形。如果缩放或调整大小，SVG 图形不会失去任何质量。SVG 文件中的每个元素和每个属性都可以被动画化。

为了做到这一点，我们将使用 clip _ extents()方法与 Context 对象

> **一起使用语法:**Context . clip _ extends()
> 
> **变元**:它不带变元
> 
> **返回** : (x1，y1，x2，y2)，全部浮动

**例:**

## 蟒 3

```
# importing pycairo
import cairo

# creating a SVG surface
# here geek1 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek1.svg", 700, 700) as surface:

    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a arc without using closing path method
    context.arc(100, 60, 40, 0, 1*22/7)

    # stroke the context to remove the moved pen
    context.stroke()

    # creating a arc with using close path method
    context.arc(300, 60, 40, 0, 1*22/7)

    # making close path
    context.close_path()

    # getting clip extents
    a = context.clip_extents()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

```
(0.0, 0.0, 700.0, 700.0)
```