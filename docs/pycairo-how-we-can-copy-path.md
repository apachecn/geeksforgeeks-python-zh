# PyCairo–我们如何复制路径？

> 原文:[https://www.geeksforgeeks.org/pycairo-how-we-can-copy-path/](https://www.geeksforgeeks.org/pycairo-how-we-can-copy-path/)

在本文中，我们将学习如何使用 python 中的 PyCairo 复制对象路径。创建当前路径的副本，并将其作为路径返回给用户。

**PyCairo** : PyCairo 是一个为 cairo 图形库提供绑定的 Python 模块。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

**SVG** 文件是使用由万维网联盟(W3C)创建的二维矢量图形格式的图形文件。它使用基于 XML 的文本格式描述图像。SVG 文件是作为在网络上显示矢量图形的标准格式开发的。

> 为此，我们将对上下文对象使用 copy_path()方法
> 
> **语法:** context.copy_path()
> 
> **参数:**不需要参数
> 
> **返回:**返回路径

**示例:**

## 蟒蛇 3

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

    # makeing close path
    context.close_path()

    # Gets a copy of the current path
    c = context.copy_path()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(c)
```

**输出:**

> move _ to 340.0000000 60.000000
> curve _ to 340.000000 70.613281 335.781250 80.792969 328.273438 88.292969
> curve _ to 320.769531 95.796875310 . 58888888