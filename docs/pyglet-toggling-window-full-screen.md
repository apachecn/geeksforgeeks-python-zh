# PYGLET–切换窗口全屏

> 原文:[https://www . geesforgeks . org/pyglet-toggling-window-全屏/](https://www.geeksforgeeks.org/pyglet-toggling-window-full-screen/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中切换全屏窗口。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。全屏和最大尺寸是两码事，不全屏也能达到最大尺寸。切换全屏后，总帐上下文应该保留其状态和对象，但是缓冲区需要被清除和重绘。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`set_fullscreen`方法
> 
> **语法:**窗口. set _ 全屏(真)
> 
> **自变量:**它以布尔为自变量
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

    # key "C" get press
    if symbol == pyglet.window.key.C:

        # close the window
        window.close()

# toggling fullscreen
window.set_fullscreen(True)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/6a98b76d2d3dd2e6515f9ad013b32418.png)