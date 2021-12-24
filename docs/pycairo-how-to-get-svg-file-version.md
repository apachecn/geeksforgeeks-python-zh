# PyCairo–如何获取 SVG 文件版本。

> 原文:[https://www . geesforgeks . org/py cairo-如何获取-svg-file-version/](https://www.geeksforgeeks.org/pycairo-how-to-get-svg-file-version/)

在本文中，我们将看到如何使用 Python 在 pycairo 中获取 SVG 文件版本。

**Pycairo** 是一个为 cairo 图形库提供绑定的 Python 模块。该库用于创建 **SVG** ，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

SVG 规范在 2011 年更新为 1.1 版。有两种“移动 SVG 配置文件”，SVG Tiny 和 SVG Basic，是为计算和显示能力降低的移动设备设计的。

> 为了使用，我们将使用带有 SVG 表面对象的 get_versions
> 
> **语法:** get_versions()
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

## 计算机编程语言

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

    # getting all the svg versions available
    versions = surface.get_versions()

# printing the versions
print("Value= " + str(versions))
```

**输出:**

> 价值=[开罗。开罗 SVGVersion.VERSION_1_1。SVGVersion.VERSION_1_2]