# PYGLET–显示/隐藏鼠标

> 原文:[https://www.geeksforgeeks.org/pyglet-show-hide-mouse/](https://www.geeksforgeeks.org/pyglet-show-hide-mouse/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中显示/隐藏鼠标，即窗口中的光标。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。在计算机用户界面中，光标是一种指示器，用于在计算机监视器或其他显示设备上显示用户交互的当前位置，这些显示设备将响应来自文本输入或定点设备的输入。可以借助`set_mouse_cursor`方法改变或设置光标。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`set_mouse_visible`方法
> 
> **语法:**窗口. set_mouse_visible(真)
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

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# getting help cursor
help_cursor = window.get_system_mouse_cursor("help")

# setting this cursor to the window
window.set_mouse_cursor(help_cursor)

# hiding mouse
window.set_mouse_visible(False)

# start running the application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-481429-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200906003613/Geeksforgeeks-2020-09-06-00-35-42.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200906003613/Geeksforgeeks-2020-09-06-00-35-42.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200906003613/Geeksforgeeks-2020-09-06-00-35-42.mp4)</video>