# PYGLET–文本事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-text-event/](https://www.geeksforgeeks.org/pyglet-on-text-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发文本事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。通常这是在 on_key_press()之后和 on_key_release()之前调用的，但如果按住该键(键重复)，也可能调用多次；或者如果使用了另一种输入方法(例如，笔输入)，则在没有按键的情况下调用。我们应该始终使用这种方法来解释文本，因为关键符号通常有到其 unicode 表示的复杂映射，这个事件会处理这些映射。
我们可以借助下面给出的命令
创建一个窗口

```
pyglet.window.Window(width, height, title)
```

下面是 on text 事件的语法，当这个事件被触发
时，这个方法被调用

```
@window.event       
def on_text(text):
    print("On text event")
```

下面是实现

## 蟒蛇 3

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

    # key "C" get press
    if symbol == pyglet.window.key.C:

        print("Key C is pressed")

# on text event
@window.event
def on_text(text):

    # printing some message
    print("You are entering : " + text)

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/19733b0edbd86fbf8890bcf0de30873c.png)

```
You are entering : g
You are entering : e
You are entering : e
You are entering : k
```