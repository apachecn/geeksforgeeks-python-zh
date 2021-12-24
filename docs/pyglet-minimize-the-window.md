# PYGLET–最小化窗口

> 原文:[https://www.geeksforgeeks.org/pyglet-minimize-the-window/](https://www.geeksforgeeks.org/pyglet-minimize-the-window/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中最小化窗口。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。我们可以在手动输入的帮助下改变窗口的大小，尽管有时需要通过编程最小化窗口。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`minimize`方法
> 
> **语法:**窗口.最小化()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

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

    # key "A" get press
    if symbol == pyglet.window.key.A:

        # minimize the window
        window.minimize()

# start running the application
pyglet.app.run()
```

**输出:**
![](img/e5b0fc15de519d1b098fd526beda89de.png)
当按键“A”被按下时窗口被最小化