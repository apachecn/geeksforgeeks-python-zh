# PyCairo–如何获取 SVG 单位？

> 原文:[https://www.geeksforgeeks.org/pycairo-how-to-get-svg-unit/](https://www.geeksforgeeks.org/pycairo-how-to-get-svg-unit/)

在本文中，我们将看到如何使用 python 在 pycairo 中获取 SVG 单元。 **SVG 单位**用于描述 SVG 规范中坐标和长度的有效单位

**Pycairo** 是一个为 cairo 图形库提供绑定的 Python 模块。该库用于创建 **SVG** ，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

> 以下是开罗的 SVG 单位
> 
> 1.  <u>用户</u>用户单位，当前坐标系中的一个值。如果在初始坐标系的根元素中使用，它对应于像素
> 2.  <u>EM</u> 元素字体的大小
> 3.  <u>EX</u> 元素字体的 x 高度
> 4.  <u>像素(1px = 1/96 <sup>第</sup>个，共 1 英寸)</u>
> 5.  <u>英寸</u>英寸(1 英寸= 2.54 厘米= 96 像素)
> 6.  <u>厘米</u>厘米(1cm = 96px/2.54)
> 7.  <u>毫米</u>毫米(1 毫米= 1/10 <sup>分之一</sup>厘米)
> 8.  <u>PT</u> 点(1pt = 1/72 <sup>第</sup>个，共 1 英寸)
> 9.  <u>PC</u> Picas (1pc = 1/6 <sup>第</sup>位，共 1 英寸)
> 10.  <u>百分比</u>百分比，是另一个参考值的分数。

> 为了使用，我们将使用带有 SVG 表面对象的 get_document_unit
> 
> **语法:** get_document_unit()
> 
> **论证:**不需要论证
> 
> **返回:**返回 SVG 单位，但打印时会显示与之相关的值。

## 蟒蛇 3

```py
# importing pycairo
import cairo

# creating a SVG surface
# here geek95 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek95.svg", 700, 700) as surface:
    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a rectangle(square)
    context.rectangle(100, 100, 100, 100)

    # setting color of the context
    context.set_source_rgba(0.4, 1, 0.4, 1)

    # stroke out the color and width property
    context.stroke()

    # getting the svg unit
    value = surface.get_document_unit()

# printing the SVG unit
print("SVG unit= " + str(value))
```

**输出:**

```py
SVG unit= 7

```