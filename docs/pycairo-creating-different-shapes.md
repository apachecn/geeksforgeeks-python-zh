# 皮开罗–创造不同的形状

> 原文:[https://www . geesforgeks . org/py cairo-creating-differential-shape/](https://www.geeksforgeeks.org/pycairo-creating-different-shapes/)

在本文中，我们将看到如何使用 Python 中的 *Pycairo* 创建不同的形状。在 *pycairo* 中，主要有两种形状矩形和拱形，用于制作其他形状，如正方形或半圆形。多边形是在线条的帮助下创建的。

**SVG** 文件是一个图形文件，它使用二维图形矢量格式，使用基于 XML 的文本格式定义图像。作为在网络上显示矢量图形的标准格式，SVG 文件被开发出来。

**PyCairo** 是一个 Python 模块，为 *cairo* 图形库提供绑定。这个库用于创建 SVG，即 python 中的矢量文件。为了安装 *pycairo* 模块，我们将使用下面给出的命令:

```py
pip install pycairo

```

打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

**分步方法:**

*   导入 *pycairo* 模块。
*   创建一个 SVG 表面对象，并向其添加上下文。
*   使用矩形函数创建矩形和正方形。
*   现在使用笔画方法删除任何移动的笔线。
*   使用弧线方法在笔画内创建一个四分之一圆和一个完整的圆，这样就有了额外的线条。

**以下是基于上述方法的完整程序:**

## 蟒蛇 3

```py
# importing pycairo
import cairo

# creating a SVG surface 
# here geek1 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek1.svg", 700, 700) as surface:

    # creating a cairo context object
    context = cairo.Context(surface)

    #creating a rectangle(square)
    context.rectangle(50, 50, 100, 100)

    #creating a rectangle
    context.rectangle(200, 200, 100, 50)

    #stroke the context to remove the moved pen 
    context.stroke()

    #creating a Arc
    context.arc(330, 60, 40, 500, 2*22/7)

     #stroke the context to remove the moved pen 
    context.stroke()

     #creating a Circle
    context.arc(500, 60, 40, 0, 2*22/7)

    # setting scale of the context
    context.scale(700, 700)

    # setting line width of the context
    context.set_line_width(0.0025)

     # setting color of the context
    context.set_source_rgba(0, 0, 0, 1)

    # stroke out the color and width property
    context.stroke()

```

**输出:**

![](img/f56bfbda1b7d62c0ebcfd2f9fdcd69ab.png)