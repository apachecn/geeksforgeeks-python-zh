# PYGLET–设置窗口大小/调整窗口大小

> 原文:[https://www . geeksforgeeks . org/pyglet-设置-大小-调整窗口大小/](https://www.geeksforgeeks.org/pyglet-setting-size-resizing-of-window/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中设置窗口的大小。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。我们可以在创建窗口时设置窗口的大小，尽管有时需要以编程方式调整窗口的大小。如果窗口不可调整大小，或者当前是全屏显示，则行为未定义。窗口大小不包括边框或标题栏。
我们可以借助下面给出的命令
创建一个窗口

```
pyglet.window.Window(width, height, title)
```

> 为了创建窗口，我们对窗口对象
> **使用 set_size 方法语法:** window.set_size(宽度、高度)
> **参数:**它以两个整数作为参数
> **返回:**它返回 None

下面是实现

## 蟒蛇 3

```
# importing pyglet module
import pyglet
import pyglet.window.key

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# text
text = "GeeksforGeeks"

# creating a label with font = times roman
# font size = 36
# aligning it to the centre
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 36,
                          x = window.width//2, y = window.height//2,
                          anchor_x ='center', anchor_y ='center')

# on draw event
@window.event
def on_draw():

    # clearing the window
    window.clear()

    # drawing the label on the window
    label.draw()

# key press event   
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == pyglet.window.key.C:

        # close the window
        window.close()

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# setting window size
# resizing the window
window.set_size(300, 400)

# hiding mouse
window.set_mouse_visible(False)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/8830e1112e015e929d377e63ee1a9d10.png)