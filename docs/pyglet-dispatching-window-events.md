# PYGLET–调度窗口事件

> 原文:[https://www . geesforgeks . org/pyglet-dispatching-window-events/](https://www.geeksforgeeks.org/pyglet-dispatching-window-events/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中调度窗口事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。分派窗口事件意味着轮询操作系统事件队列中的新事件，并调用附加的事件处理程序。这种方法是为以 pyglet 1.0 为目标的遗留应用程序以及必须将其事件循环集成到另一个框架中的高级应用程序提供的。

我们可以在下面命令的帮助下创建一个窗口

```py
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们使用`dispatch_events`方法和窗口对象
> **语法:** window.dispatch_events()
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

    # key "E" get press
    if symbol == pyglet.window.key.E:

        # close the window
        window.close()

# dispatching window events
window.dispatch_events()

# start running the application
pyglet.app.run()
```

**输出:**
![](img/0d56b3b6de1f1f517c41e7e1685bc958.png)