# PYGLET–移动事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-move-event/](https://www.geeksforgeeks.org/pyglet-on-move-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发 on move 事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。这个事件在窗口移动时被调用，我们可以借助 set_location 方法改变窗口的位置。

我们可以在下面命令的帮助下创建一个窗口

```
pyglet.window.Window(width, height, title)
```

下面是移动事件的语法，当这个事件被触发时，这个方法被调用

```
@window.event       
def on_move(x, y):
    print("Window Moved")
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
# aligning it to the center
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

# on move event
@window.event
def on_move(x, y):

    # printing some message
    print("Window Move")
    print("New Position : ", end = "")
    print(x, y)

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# moving window
window.set_location(100, 200)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/9abd97b096b03a39dda9fd629418ede8.png)

```
Window Move
New Position : 100 200
```