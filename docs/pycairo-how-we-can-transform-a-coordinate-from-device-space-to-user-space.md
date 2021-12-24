# PyCairo–我们如何将坐标从设备空间转换到用户空间？

> 原文:[https://www . geesforgeks . org/py cairo-我们如何能够将一个坐标从设备空间转换到用户空间/](https://www.geeksforgeeks.org/pycairo-how-we-can-transform-a-coordinate-from-device-space-to-user-space/)

在本文中，我们将学习如何使用 python 中的 PyCairo 将坐标从设备空间转换到用户空间。通过给定点乘以当前变换矩阵的倒数(CTM)，将坐标从设备空间变换到用户空间。

Pycairo 是一个 Python 模块，为 cairo 图形库提供绑定。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器。几乎所有的网络浏览器都支持某种 SVG 格式的渲染。

SVG 代表可缩放矢量图形。它基本上以 XML 格式定义基于矢量的图形。如果缩放或调整大小，SVG 图形不会失去任何质量。SVG 文件中的每个元素和每个属性都可以被动画化。

为此，我们将对上下文对象使用 device_to_user()方法。

> **语法**:context . device _ to _ user()
> 
> **参数:**取 x，y
> 
> **返回:**返回 x，y 两个浮点数

**例:**

## 蟒 3

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

    # making close path
    context.close_path()

    # convert device co-ordinate to user co-ordinate
    a = context.device_to_user(10, 10)

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

```py
(10.0, 10.0)
```