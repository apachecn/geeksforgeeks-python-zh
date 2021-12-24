# PYGLET–车窗停用事件

> 原文:[https://www . geeksforgeeks . org/pyglet-window-deactivate-event/](https://www.geeksforgeeks.org/pyglet-window-deactivate-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发窗口停用事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。单击另一个应用程序窗口可以触发此事件。当窗口被停用时，它不再具有键盘焦点。

我们可以在下面命令的帮助下创建一个窗口

```
pyglet.window.Window(width, height, title)

```

下面是窗口停用事件的语法，当这个事件被触发时，这个方法被调用

```
@window.event       
def on_deactivate():
    print("Window Deactivated")

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
# window deactivate event      
def on_deactivate():

    # printing message
    print("Switched to another app")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/461947f48974ccfc94ced0cfa89b3962.png)
当我们切换到另一个 app 时，会触发此事件

```
Switched to another app

```