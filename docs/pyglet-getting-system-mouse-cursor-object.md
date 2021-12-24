# PYGLET–获取系统鼠标光标对象

> 原文:[https://www . geesforgeks . org/pyglet-get-system-mouse-cursor-object/](https://www.geeksforgeeks.org/pyglet-getting-system-mouse-cursor-object/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取系统鼠标光标对象。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。我们可以获得一个系统鼠标光标对象，它可以和 set_mouse_cursor 一起使用，使这个方法返回的光标处于活动状态。
我们可以借助下面给出的命令创建一个窗口

```
 pyglet.window.Window(width, height, title)
```

> 为了创建窗口，我们对窗口对象
> **使用 get_system_mouse_cursor 方法语法:**window . get _ system _ mouse _ cursor(Cursor _ name)
> **参数:**它以字符串作为参数
> **返回:**它返回 Cursor 对象

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

        # closing the window
        window.close()

# start running the application
pyglet.app.run()

# cursor name eg "help"
name = "wait"

# getting window size
value = window.get_system_mouse_cursor(name)

# showing value
print("Cursor Object : ", end = "")
print(value)
```

**输出:**

![](img/53c435228e7bd95cfd540ba6777d1940.png)

```
Cursor Object : pyglet.window.win32.Win32MouseCursor object at 0x000001CC009EA7C8
```