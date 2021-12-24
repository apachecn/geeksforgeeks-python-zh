# PYGLET–车窗激活事件

> 原文:[https://www.geeksforgeeks.org/pyglet-window-activate-event/](https://www.geeksforgeeks.org/pyglet-window-activate-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发窗口激活事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。这个事件可以通过点击标题栏来触发，将其带到前台；或者通过一些特定于平台的方法。当窗口处于“活动”状态时，它具有键盘焦点。

我们可以借助下面给出的命令创建一个窗口

```py
pyglet.window.Window(width, height, title)
```

下面是窗口激活事件的语法，当这个事件被触发时，这个方法被调用

```py
@window.event       
def on_activate():
    print("Keyboard focus is on window")
    print("Window activate Event")
```

下面是实现

## 蟒蛇 3

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
# window activate event
def on_activate():

    # printing som message
    print("Keyboard focus is on window")
    print("Window activate Event")

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

![](img/bae2be4d4e49c354503bf77d241f43e9.png)

当我们最小化窗口并点击标题栏时，这个事件被触发

```py
Keyboard focus is on window
Window activate Event
```