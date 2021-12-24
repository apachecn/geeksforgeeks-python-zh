# PyCairo–我们如何获得填充范围？

> 原文:[https://www . geeksforgeeks . org/py cairo-我们如何获得填充范围/](https://www.geeksforgeeks.org/pycairo-how-we-can-get-fill-extents/)

在本文中，我们将学习如何使用 python 中的 PyCairo 获得填充范围。在给定当前路径和填充参数的情况下，通过 context.fill()操作，在用户坐标中计算覆盖受影响区域(“彩色”区域)的边界框。如果当前路径为空，则返回一个空矩形(0，0，0，0)。不考虑表面尺寸和剪裁。

**PyCairo** : PyCairo 是一个为 cairo 图形库提供绑定的 Python 模块。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

**SVG** 文件是使用由万维网联盟(W3C)创建的二维矢量图形格式的图形文件。它使用基于 XML 的文本格式描述图像。SVG 文件是作为在网络上显示矢量图形的标准格式开发的。

请注意，根据填充规则，fill _ extensions()必须做更多的工作来计算精确的彩色区域。

> 为此，我们将对上下文对象使用 fill _ extensions()方法
> 
> **语法:**context . fill _ extensions()
> 
> **参数:**不需要参数
> 
> **返回:** (x1，y1，x2，y2)，全浮

**实施例 1 :**

## 蟒蛇 3

```py
# importing pycairo
import cairo

# creating a SVG surface
# here geek1 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek1.svg", 700, 700) as surface:

    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a arc with using close path method
    context.arc(300, 60, 40, 0, 1*22/7)

    # makeing close path
    context.close_path()
    context.fill()

    # getting fill extends
    a = context.fill_extents()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

```py
(0.0, 0.0, 0.0, 0.0)
```

**实施例 2 :**

## 蟒蛇 3

```py
# importing pycairo
import cairo

# creating a SVG surface
# here geek1 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek1.svg", 700, 700) as surface:

    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a arc with using close path method
    context.arc(300, 60, 40, 0, 1*22/7)

    # getting fill extends
    a = context.fill_extents()

    # makeing close path
    context.close_path()
    context.fill()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

```py
(260.0, 59.94921875, 340.0, 100.0)
```