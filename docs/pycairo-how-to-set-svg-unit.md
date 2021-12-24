# PyCairo–如何设置 SVG 单位？

> 原文:[https://www.geeksforgeeks.org/pycairo-how-to-set-svg-unit/](https://www.geeksforgeeks.org/pycairo-how-to-set-svg-unit/)

在本文中，我们将看到如何使用 python 在 pycairo 中设置 SVG 单元。 **SVG 单位**用于描述 SVG 规范中坐标和长度的有效单位

**Pycairo** 是一个为 cairo 图形库提供绑定的 Python 模块。该库用于创建 **SVG** ，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

> 以下是开罗的 SVG 单位
> 
> 1.  用户用户单位，当前坐标系中的一个值。如果在初始坐标系的根元素中使用，它对应于像素
> 2.  元素字体的大小
> 3.  元素字体的 x 高度
> 4.  像素(1px = 1/96 <sup>第</sup>个，共 1 英寸)
> 5.  英寸(1 英寸= 2.54 厘米= 96 像素)
> 6.  厘米厘米(1 厘米= 96px/2.54)
> 7.  毫米毫米(1 毫米= 1/10 <sup>第</sup>个，共 1 厘米)
> 8.  点(1pt = 1/72 <sup>第</sup>个，共 1 英寸)
> 9.  PC Picas (1pc = 1/6 <sup>第</sup>个，共 1 英寸)
> 10.  百分比百分比，是另一个参考值的一部分。

> 为了使用，我们将使用集 _ 文档 _ 单位与 SVG 表面对象
> 
> **语法:** set_document_unit()
> 
> **自变量:**取 SVU 单位，即与之相关的值。
> 
> **返回:**返回非

## 蟒蛇 3

```
# importing pycairo
import cairo

# creating a SVG surface
# here geek95 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek95.svg", 700, 700) as surface:

    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a rectangle(square)
    context.rectangle(10, 10, 100, 100)

    # setting color of the context
    context.set_source_rgba(0.4, 1, 0.4, 1)

    # stroke out the color and width property
    context.fill()

    # Setting SVG unit
    surface.set_document_unit(7)

# printing
print("SVG unit Changed")
```

**输出:**

```
SVG unit Changed

```