# PYGLET–为窗口设置专属鼠标

> 原文:[https://www . geesforgeks . org/pyglet-setting-exclusive-mouse-for-window/](https://www.geeksforgeeks.org/pyglet-setting-exclusive-mouse-for-window/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中为窗口设置独占鼠标。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。独占鼠标隐藏鼠标光标，并将所有鼠标事件指向此窗口。启用时，此功能可防止鼠标离开窗口。它对于某些需要完全控制鼠标的游戏风格非常有用。启用独占鼠标时，后续事件中报告的鼠标位置没有意义；您应该只使用相对运动参数 dx 和 dy。

我们可以在下面命令的帮助下创建一个窗口

```py
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`set_exclusive_mouse`方法
> 
> **语法:**窗口. set_exclusive_mouse(真)
> 
> **自变量:**它以布尔为自变量
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

# setting excluive mouse
window.set_exclusive_mouse(True)

# start running the application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-481440-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200905050643/Geeksforgeeks-2020-09-05-05-06-29.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200905050643/Geeksforgeeks-2020-09-05-05-06-29.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200905050643/Geeksforgeeks-2020-09-05-05-06-29.mp4)</video>