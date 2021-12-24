# 皮格莱特–隐藏事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-hide-event/](https://www.geeksforgeeks.org/pyglet-on-hide-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发 hide 事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当窗口最小化或被用户隐藏(在 Mac OS X 上)时，会触发此事件。
我们可以借助下面给出的命令
创建一个窗口

```py
pyglet.window.Window(width, height, title)
```

下面是 on hide 事件的语法，这个方法在这个事件被触发时被调用

```py
@window.event       
def on_hide():
    print("Window is minimised")
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

new_label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 10,
                          x = 25, y = 25)

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

# on hide event
@window.event
def on_hide():

    # printing some message
    print("Window is minimized")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# minimize the window
window.minimize()

# start running the application
pyglet.app.run()
```

**输出:**

```py
Window is minimized
```