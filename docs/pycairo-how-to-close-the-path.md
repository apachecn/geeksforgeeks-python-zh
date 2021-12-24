# PyCairo–如何关闭路径？

> 原文:[https://www . geesforgeks . org/py cairo-如何关闭路径/](https://www.geeksforgeeks.org/pycairo-how-to-close-the-path/)

在本文中，我们将学习如何使用 python 中的 PyCairo 来关闭笔路径。将线段添加到从当前点到当前子路径起点的路径中。

**注意:**从开罗版本 1.2.4 开始，对 close_path()的任何调用都会在 CLOSE_PATH 元素之后立即将一个显式的 MOVE_TO 元素放入路径中，

**PyCairo** : PyCairo 是一个为 cairo 图形库提供绑定的 Python 模块。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

**SVG** 文件是使用由万维网联盟(W3C)创建的二维矢量图形格式的图形文件。它使用基于 XML 的文本格式描述图像。SVG 文件是作为在网络上显示矢量图形的标准格式开发的。

**实施步骤:**

1.  导入 Pycairo 模块。
2.  创建一个 SVG 表面对象并向其添加上下文。
3.  创建任何对象，如弧，曲线等。
4.  现在我们可以用 close_path()方法闭合圆弧做成半圆。

**下面是实现:**

## 蟒蛇 3

```py
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

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print("File Saved")
```

**输出:**

![](img/8e45b477f5ff6b781d5fcdd382543d42.png)