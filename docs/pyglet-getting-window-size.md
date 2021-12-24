# PYGLET–获取窗口大小

> 原文:[https://www.geeksforgeeks.org/pyglet-getting-window-size/](https://www.geeksforgeeks.org/pyglet-getting-window-size/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获得当前的窗口大小。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当前窗口的大小基本上就是窗口的宽度和高度。窗口大小不包括边框或标题栏。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`get_size`方法
> 
> **语法:** window.get_size()
> 
> **论证:**不需要论证
> 
> **返回:**返回元组

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

    # key "E" get press
    if symbol == pyglet.window.key.E:

        # closing the window
        window.close()

# getting window size
value = window.get_size()

# start running the application
pyglet.app.run()

# showing value
print("Window Size : ", end = "")
print(value)
```

**输出:**
![](img/fd92c9e4972712112df38154caec239c.png)

```
Window Size : (500, 500)

```