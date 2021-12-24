# PYGLET–按键事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-key-press-event/](https://www.geeksforgeeks.org/pyglet-on-key-press-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发按键事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。按下(并按住)键盘上的一个键。在 pyglet 1.0 中，如果按下 ESC 键，默认处理程序会将 has_exit 设置为 True。按键事件是处理键盘输入的主要事件。
我们可以借助下面给出的命令创建一个窗口

```py
pyglet.window.Window(width, height, title)
```

以下是按下 on 键事件的语法，当触发此事件时，将调用此方法:

```py
@window.event       
def on_key_press(symbol, modifiers):
    print("Key is pressed")
```

**示例:**下面是实现

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

    print("Some key is pressed")

    # key "C" get press
    if symbol == pyglet.window.key.C:

        print("Key C is pressed")

# on hide event
@window.event
def on_hide():

    # printing some message
    print("Window is minimized")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/c4cd7ef5f3680a3fe2c811215b0e76ae.png)

```py
Some key is pressed
Key C is pressed
```