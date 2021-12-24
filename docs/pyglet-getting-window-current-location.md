# PYGLET–获取窗口当前位置

> 原文:[https://www . geeksforgeeks . org/pyglet-get-window-current-location/](https://www.geeksforgeeks.org/pyglet-getting-window-current-location/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取窗口的当前位置。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当前位置是虚拟桌面上左边缘和上边缘与其各自边缘的距离，以像素为单位。

我们可以在下面命令的帮助下创建一个窗口

```py
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`get_location`方法
> 
> **语法:** window.get_location()
> 
> **论证:**不需要论证
> 
> **返回:**返回元组

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

    # key "E" get press
    if symbol == pyglet.window.key.E:

        # closing the window
        window.close()

# getting current window location
value = window.get_location()

# start running the application
pyglet.app.run()

# showing value
print("Window Location : ", end = "")
print(value)
```

**输出:**
![](img/c8b09e6c8714cad2bfe3784d4778803f.png)

```py
Window Location : (138, 161)

```