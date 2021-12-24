# PyCairo–将距离矢量从设备空间转换到用户空间

> 原文:[https://www . geeksforgeeks . org/py cairo-transform-一种从设备空间到用户空间的距离矢量/](https://www.geeksforgeeks.org/pycairo-transform-a-distance-vector-from-device-space-to-user-space/)

在本文中，我们将学习如何使用 python 中的 PyCairo 将距离向量从设备空间转换到用户空间。该函数与 Context.device_to_user()类似，只是在变换(dx，dy)时将忽略逆 CTM 的平移分量。

Pycairo 是一个 Python 模块，为 cairo 图形库提供绑定。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器。几乎所有的网络浏览器都支持某种 SVG 格式的渲染。

SVG 代表可缩放矢量图形。它基本上以 XML 格式定义基于矢量的图形。如果缩放或调整大小，SVG 图形不会失去任何质量。SVG 文件中的每个元素和每个属性都可以被动画化。

为此，我们将对上下文对象使用设备到用户的距离()方法。

> **语法:**context . device _ to _ user _ distance()
> 
> **参数:**需要 dx，dy
> 
> **返回:**它返回 dx，dy 两个浮动

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

    # convert device co-ordinate to user co-ordinate
    a = context.device_to_user_distance(1, 10)

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

```
(1.0, 10.0)

```