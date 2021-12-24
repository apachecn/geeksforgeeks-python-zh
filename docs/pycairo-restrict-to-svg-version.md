# PyCairo–仅限 SVG 版本

> 原文:[https://www . geesforgeks . org/py cairo-restrict-to-SVG-version/](https://www.geeksforgeeks.org/pycairo-restrict-to-svg-version/)

在本文中，我们将看到如何使用 Python 在 pycairo 中限制到 SVG 文件版本。

**Pycairo** 是一个为 cairo 图形库提供绑定的 Python 模块。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

SVG 规范在 2011 年更新为 1.1 版。有两种“移动 SVG 配置文件”，SVG Tiny 和 SVG Basic，是为计算和显示能力降低的移动设备设计的。

> 为了使用，我们将对 SVG 表面对象使用 restrict_to_version
> 
> **语法:** restrict_to_version()
> 
> **自变量:**以 SVG 版本为自变量
> 
> **返回:**返回非

## 蟒蛇 3

```py
# importing pycairo
import cairo

# getting all the svg versions available
versions = surface.get_versions()

# Selecting version from list
version = versions[1]

# creating a SVG surface
# here geek95 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek95.svg", 700, 700) as surface:

    # Restriction to version
    surface.restrict_to_version(version)

    # creating a cairo context object
    context = cairo.Context(surface)

    # creating a rectangle(square)
    context.rectangle(10, 10, 100, 100)

    # setting color of the context
    context.set_source_rgba(0.4, 1, 0.4, 1)

    # stroke out the color and width property
    context.fill()

# printing
print("SVG version")
```

**输出:**

```py
 SVG version
```

**注意**:该功能只能在给定曲面上进行任何绘制操作之前调用。最简单的方法是在创建曲面后立即调用该函数。