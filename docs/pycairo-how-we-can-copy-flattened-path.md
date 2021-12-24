# PyCairo–我们如何复制扁平路径？

> 原文:[https://www . geeksforgeeks . org/py cairo-我们如何复制-展平-路径/](https://www.geeksforgeeks.org/pycairo-how-we-can-copy-flattened-path/)

在本文中，我们将学习如何使用 python 中的 PyCairo 复制对象的扁平路径。该函数类似于 copy_path()方法，不同之处在于路径中的任何曲线都将使用分段线性近似法进行近似。

**PyCairo** : PyCairo 是一个为 cairo 图形库提供绑定的 Python 模块。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件进行查看(只读)最简单快捷的方法是使用现代网络浏览器，如 Chrome、Firefox、Edge 或 Internet Explorer，几乎所有这些浏览器都应该为 SVG 格式提供某种渲染支持。

**SVG** 文件是使用由万维网联盟(W3C)创建的二维矢量图形格式的图形文件。它使用基于 XML 的文本格式描述图像。SVG 文件是作为在网络上显示矢量图形的标准格式开发的。

> 为此，我们将对上下文对象使用 copy_path_flat()方法
> 
> **语法:** context.copy_path_flat()
> 
> **参数:**不需要参数
> 
> **返回:**用分段线性逼近法返回<u>路径</u>

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

    # Gets a flattened copy of the current path
    c = context.copy_path_flat()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(c)
```

**输出:**

```
move_to 340.000000 60.000000
line_to 339.800781 63.953125
line_to 339.218750 67.839844
line_to 338.261719 71.632813
line_to 336.949219 75.312500
line_to 335.277344 78.835938
line_to 333.269531 82.199219
line_to 330.929688 85.355469
line_to 328.273438 88.292969
line_to 325.332031 90.945313
line_to 322.175781 93.285156
line_to 318.812500 95.289063
line_to 315.285156 96.960938
line_to 311.609375 98.273438
line_to 307.816406 99.226563
line_to 303.929688 99.800781
line_to 299.976563 100.000000
line_to 296.011719 99.796875
line_to 292.125000 99.214844
line_to 288.332031 98.253906
line_to 284.660156 96.941406
line_to 281.128906 95.265625
line_to 277.773438 93.253906
line_to 274.617188 90.914063
line_to 271.687500 88.257813
line_to 269.027344 85.316406
line_to 266.691406 82.152344
line_to 264.683594 78.789063
line_to 263.023438 75.261719
line_to 261.710938 71.582031
line_to 260.761719 67.789063
line_to 260.187500 63.902344
line_to 260.000000 59.949219
close path
move_to 340.000000 60.000000

```