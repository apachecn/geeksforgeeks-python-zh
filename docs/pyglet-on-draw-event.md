# PYGLET–抽奖活动

> 原文:[https://www.geeksforgeeks.org/pyglet-on-draw-event/](https://www.geeksforgeeks.org/pyglet-on-draw-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发 draw 事件上的窗口。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当应该重绘窗口时，事件循环将调度此事件。这将发生在任何窗口事件后的空闲时间和调用任何预定函数后。该窗口将已经有了总帐上下文，因此不需要调用 switch_to。窗口的翻转方法将在此事件后调用，因此您的事件处理程序不应该。

我们可以在下面命令的帮助下创建一个窗口

```
pyglet.window.Window(width, height, title)

```

下面是 window on draw 事件的语法，这个方法在这个事件被触发时被调用

```
@window.event       
def on_draw():
    print("Window Draw Event")

```

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

    # printing some message
    print("Window Draw event called")

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

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/ddd5fab896c9e8d640925301dffa2a53.png)

```
Window Draw event called

```