# PYGLET–为窗口绘制鼠标光标

> 原文:[https://www . geesforgeks . org/pyglet-drawing-mouse-cursor-for-window/](https://www.geeksforgeeks.org/pyglet-drawing-mouse-cursor-for-window/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中为窗口绘制鼠标光标。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。如果当前鼠标光标设置了可绘制，则在翻转缓冲区进行渲染之前，会调用此绘制方法。绘图方法总是将 GL_MODELVIEW 矩阵保留为当前矩阵，而不管它以前被设置为什么。其他总帐状态不受影响。

我们可以在下面命令的帮助下创建一个窗口

```py
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`draw_mouse_cursor`方法
> 
> **语法:** window.draw_mouse_cursor()
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

    # drawing cursor for window
    window.draw_mouse_cursor()

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "E" get press
    if symbol == pyglet.window.key.E:

        # close the window
        window.close()

# start running the application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-481468-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200905033218/Geeksforgeeks-2020-09-05-03-32-03.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200905033218/Geeksforgeeks-2020-09-05-03-32-03.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200905033218/Geeksforgeeks-2020-09-05-03-32-03.mp4)</video>