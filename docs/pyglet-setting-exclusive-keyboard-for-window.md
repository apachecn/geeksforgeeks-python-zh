# PYGLET–设置窗口专用键盘

> 原文:[https://www . geesforgeks . org/pyglet-setting-exclusive-keyboard-for-window/](https://www.geeksforgeeks.org/pyglet-setting-exclusive-keyboard-for-window/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中为窗口设置专用键盘。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。专用键盘防止用户使用键盘加速器从该窗口切换。启用后，此功能会禁用某些特定于操作系统的组合键，如 Alt+Tab(OS X 上的命令+Tab)。这在某些 kiosk 应用程序中很有用，在一般应用程序或游戏中应该避免。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`set_exclusive_keyboard`方法
> 
> **语法:**窗口. set_exclusive_keyboard(真)
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

# setting excluive keyboard
window.set_exclusive_keyboard(True)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/10b5720cd5cdb58a66696e86edc29647.png)