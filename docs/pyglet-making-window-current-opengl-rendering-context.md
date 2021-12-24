# PYGLET–使窗口成为当前 OpenGL 渲染上下文

> 原文:[https://www . geesforgeks . org/pyglet-making-window-current-OpenGL-rendering-context/](https://www.geeksforgeeks.org/pyglet-making-window-current-opengl-rendering-context/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中使窗口成为当前的 opengl 渲染上下文。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。一次只能有一个 OpenGL 上下文处于活动状态。此方法将当前窗口的上下文设置为当前的。您应该优先使用此方法，而不是 pyglet.gl.Context.set_current，因为它可能执行额外的初始化功能。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`switch_to`方法
> 
> **语法:** window.switch_to()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

```py
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

# making window current opengl rendering context
window.switch_to()

# start running the application
pyglet.app.run()
```

**输出:**
![](img/c2affdd6d8e77ae1c2b69a8c87226a17.png)