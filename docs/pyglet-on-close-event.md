# PYGLET–关闭事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-close-event/](https://www.geeksforgeeks.org/pyglet-on-close-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发关闭事件窗口。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。这个事件可以通过点击窗口标题栏中的“X”控制框来触发，也可以通过其他平台相关的方式来触发。默认处理程序将 _exit 设置为真。在 pyglet 1.1 中，如果正在使用 pyglet.app.event_loop，也会调用 close，立即关闭窗口。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

下面是窗口关闭事件的语法，这个方法在这个事件被触发时被调用

```py
@window.event       
def on_close():
    print("Window has been closed")

```

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

    print("nn")
    # key "C" get press
    if symbol == pyglet.window.key.C:

        # close the window
        window.close()

@window.event   
# window close event       
def on_close():

    # printing some message
    print("Window has been closed")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/18df6eddadfdef6285f8fe4037816241.png)
当我们关闭该窗口时，该事件被触发

```py
Window has been closed

```