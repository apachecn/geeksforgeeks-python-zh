# PYGLET–形状高度/半径

> 原文:[https://www.geeksforgeeks.org/pyglet-shape-height-radius/](https://www.geeksforgeeks.org/pyglet-shape-height-radius/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中访问形状的高度。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。形状是对象或其外部边界、轮廓或外部表面的形式，与颜色、纹理或材质类型等其他属性相反。许多形状都是借助 pyglet 的形状模块绘制的。高度是垂直距离的量度，要么是垂直范围(某物或某人有多高)，要么是垂直位置(一个点有多高)。对于像圆形高度为 2 *半径这样的形状，圆形将没有属性高度
我们可以借助下面给出的命令
创建一个窗口

```
# creating a window
window = pyglet.window.Window(width, height, title)
```

> 为了创建窗口，我们使用高度或半径属性和形状
> **语法:**形状.高度或形状.半径
> **参数:**它不需要参数
> **返回:**它返回整数

下面是实现

## 蟒蛇 3

```
# importing pyglet module
import pyglet

# importing shapes from the pyglet
from pyglet import shapes

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# creating a batch object
batch = pyglet.graphics.Batch()

# properties of rectangle
# co-ordinates of rectangle
co_x = 150
co_y = 150

# width of rectangle
width = 250

# height of rectangle
height = 150

# color = green
color = (50, 225, 30)

# creating a rectangle
rec = shapes.Rectangle(co_x, co_y, width, height, color = color, batch = batch)

# changing opacity of the rect1
# opacity is visibility (0 = invisible, 255 means visible)
rec.opacity = 180

# creating another rectangle with properties
# x, y co ordinate : 50, 250
# width, height of rectangle : 300, 200
# color = red
color = (255, 25, 25)

# properties of circle
# co-ordinates of circle
circle_x = 200
circle_y = 300

# size of circle
# color = green
size_circle = 100

# creating a circle
circle = shapes.Circle(circle_x, circle_y, size_circle, color =(250, 22, 30), batch = batch)

# changing opacity of the circle1
# opacity is visibility (0 = invisible, 255 means visible)
circle.opacity = 170

# window draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the batch
    batch.draw()

# accessing height of rectangle
value_rec = rec.height

# printing value
print("Rectangle : ", end = "")
print(value_rec)

# accessing radius of circle
value_cir = circle.radius

# printing value
print("Circle : ", end = "")
print(value_cir)

# run the pyglet application
pyglet.app.run()
```

**输出:**

![](img/e5b716e5def438d422ab049956e29969.png)

```
Rectangle : 150
Circle : 100
```