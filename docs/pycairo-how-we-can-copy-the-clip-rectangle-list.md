# PyCairo–我们如何复制剪辑矩形列表？

> 原文:[https://www . geeksforgeeks . org/py cairo-我们如何复制剪辑矩形列表/](https://www.geeksforgeeks.org/pycairo-how-we-can-copy-the-clip-rectangle-list/)

在本文中，我们将学习如何使用 Python 中的 PyCairo 复制剪辑矩形列表。Pycairo 是一个 Python 模块，为 cairo 图形库提供绑定。这个库用于创建 SVG，即 python 中的矢量文件。打开 SVG 文件的最简单快捷的方法是使用现代网络浏览器查看它(只读)。几乎所有的网络浏览器都支持某种 SVG 格式的渲染。

SVG 代表可缩放矢量图形。它基本上以 XML 格式定义基于矢量的图形。如果缩放或调整大小，SVG 图形不会失去任何质量。SVG 文件中的每个元素和每个属性都可以被动画化。

为此，我们将对上下文对象使用 copy_clip_rectangle_list()方法

> **语法:**context . copy _ clip _ rectangle _ list()
> 
> **争论**:不需要争论
> 
> **返回:**当前剪辑区域基本上作为用户坐标中的矩形列表，返回矩形列表

**示例:**

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

    # copying the clip rectangle list
    a = context.copy_clip_rectangle_list()

    # stroke the context to remove the moved pen
    context.stroke()

# printing message when file is saved
print(a)
```

**输出:**

> [开罗。矩形(x=0.0，y=0.0，宽=700.0，高=700.0)]