# PYGLET–翻转窗口缓冲区

> 原文:[https://www . geeksforgeeks . org/pyglet-翻转-窗口-缓冲区/](https://www.geeksforgeeks.org/pyglet-flipping-window-buffer/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中翻转窗口缓冲区。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。翻转意味着交换 OpenGL 前后缓冲区。双缓冲窗口上的翻转方法，用后缓冲更新可见显示。此操作后，后台缓冲区的内容未定义。默认情况下，Windows 是双缓冲的。在 on_draw()事件之后，翻转由 EventLoop 自动调用。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`flip`方法
> 
> **语法:**窗口.翻转()
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

    # key "F" get press
    if symbol == pyglet.window.key.F:

        # flipping the window buffer
        window.flip()

# start running the application
pyglet.app.run()
```

**输出:**
按下“F”键时窗口翻转，基本刷新屏幕

<video class="wp-video-shortcode" id="video-481456-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200905034424/Geeksforgeeks-2020-09-05-03-43-38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200905034424/Geeksforgeeks-2020-09-05-03-43-38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200905034424/Geeksforgeeks-2020-09-05-03-43-38.mp4)</video>