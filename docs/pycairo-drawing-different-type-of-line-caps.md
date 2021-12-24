# PyCairo–绘制不同类型的线帽

> 原文:[https://www . geesforgeks . org/py cairo-drawing-differential-type-line-caps/](https://www.geeksforgeeks.org/pycairo-drawing-different-type-of-line-caps/)

在本文中，我们将学习如何在 python 中使用 PyCairo 绘制不同的线帽类型。线帽是线条的端点。

实施步骤:

1.  导入 Pycairo 模块。
2.  创建一个 SVG 表面对象并向其添加上下文。
3.  设置上下文的颜色和线宽
4.  使用 set_line_cap()设置线帽样式
5.  创建一条线。

**PyCairo 有三种不同类型的线帽样式。**

**1。** set_line_cap(开罗。线帽对接)

**示例:**

## 蟒蛇 3

```
# importing pycairo
import cairo

# creating a SVG surface
# here geek94 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek94.svg", 700, 700) as surface:

    # creating a cairo context object for SVG surface
    # useing Context method
    context = cairo.Context(surface)
    context.set_source_rgba(0, 0, 0, 1)
    context.set_line_width(12)

    context.set_line_cap(cairo.LINE_CAP_BUTT)
    context.move_to(30, 50)
    context.line_to(150, 50)

    # stroke out the color and width property
    context.stroke()

    # printing message when file is saved
    print("File Saved")
```

**输出:**

![](img/abb7b32953afe449076ceff2f8fda8dc.png)

**2。** set_line_cap(开罗。线帽圆)

**示例:**

## 蟒蛇 3

```
# importing pycairo
import cairo

# creating a SVG surface
# here geek94 is file name & 700, 700 is dimension
with cairo.SVGSurface("geek94.svg", 700, 700) as surface:

    # creating a cairo context object for SVG surface
    # useing Context method
    context = cairo.Context(surface)
    context.set_source_rgba(0, 0, 0, 1)
    context.set_line_width(12)

    context.set_line_cap(cairo.LINE_CAP_ROUND)
    context.move_to(30, 50)
    context.line_to(150, 50)

    # stroke out the color and width property
    context.stroke()

    # printing message when file is saved
    print("File Saved")
```