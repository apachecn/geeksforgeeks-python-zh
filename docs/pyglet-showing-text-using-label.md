# PYGLET–使用标签显示文本

> 原文:[https://www . geesforgeks . org/pyglet-showing-text-use-label/](https://www.geeksforgeeks.org/pyglet-showing-text-using-label/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中的窗口上显示文本。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了显示文本或信息，我们使用标签对象。标签是在窗体上显示文本的图形控件元素。它通常是静态控件；没有交互性。标签通常用于标识附近的文本框或其他小部件。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们使用`pyglet.text.Label`方法
> 
> **语法:** pyglet.text.Label(text，font_name，font_size，x，y)
> 
> **参数:**取 5 个参数，第一个是字符串即消息，第二个是字符串即字体名称，第三个是整数即字体大小，第四个和第五个是引用标签位置的整数
> 
> **返回:**返回无

**注意:**为了在窗口上显示这个标签，我们必须使用 draw 事件在窗口中绘制标签

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
text = "Welcome to GeeksforGeeks"

# creating a label with font = times roman
# font size = 36
# aligning it to the centre
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 28,
                          x = 20, y = window.height//2, )

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

        # closing the window
        window.close()

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/cb74fb0224b736913c7d54812f0340f6.png)