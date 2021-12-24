# PYGLET–上下文丢失事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-context-lost-event/](https://www.geeksforgeeks.org/pyglet-on-context-lost-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发上下文丢失事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当上下文丢失时，在重新创建之前，不能再调用 GL 方法。这是一个罕见的事件，可能是由用户切换到不兼容的视频模式触发的。当它发生时，应用程序将需要重新加载所有对象(显示列表、纹理对象、着色器)以及恢复总帐状态。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

下面是上下文丢失事件窗口的语法，这个方法在这个事件被触发时被调用

```py
@window.event       
def on_context_lost():
    print("Please wait, reloading")

```

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

    print("nn")
    # key "C" get press
    if symbol == pyglet.window.key.C:

        # close the window
        window.close()

@window.event   
# window close event       
def on_context_lost():

    # printing message
    print("Please wait, reloading")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/7219632b263b51b2f89cf59186904591.png)