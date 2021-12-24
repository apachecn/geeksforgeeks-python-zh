# PYGLET–鼠标状态处理器

> 原文:[https://www.geeksforgeeks.org/pyglet-mouse-state-handler/](https://www.geeksforgeeks.org/pyglet-mouse-state-handler/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中创建鼠标状态处理程序对象。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。鼠标状态处理程序类是一个简单的处理程序，从鼠标跟踪按钮的状态。如果一个按钮被按下，那么这个处理程序为它保存一个真值。

我们可以在下面命令的帮助下创建一个窗口

```
# creating a window
window = pyglet.window.Window(width, height, title) 
```

> 为了创建窗口，我们使用了带有 pyglet.window.mouse
> **语法:**鼠标的 MouseStateHandler 方法。moussestathandler()
> **参数:**不需要参数
> **返回:**返回 moussestathandler 对象

下面是实现

## 蟒蛇 3

```
# importing pyglet module
import pyglet
import pyglet.window.key as key

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# text 
text = "Welcome to GeeksforGeeks Have a nice day"

# batch object
batch = pyglet.graphics.Batch()

# creating document
document = pyglet.text.document.FormattedDocument(text)

# setting style to the document
document.set_style(0, len(document.text), dict(
                         font_name ='Arial', font_size = 16, 
                         color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(
               document, 400, 350, batch = batch)

# making layout to display multiline
layout.multiline = True

# creating a caret
caret = pyglet.text.caret.Caret(layout, color =(255, 255, 255))

# caret to window push handlers
window.push_handlers(caret)

# setting caret style
caret.set_style(dict(font_name ="Arial"))

# on draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the batch
    batch.draw()

    # caret to window push handlers
    window.push_handlers(caret)

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == key.C:

        # printing the message
        print("Key : C is pressed")

# image for icon
img = image = pyglet.resource.image("gfg.png")

# creating a mouse state handler
mouse_handler = pyglet.window.mouse.MouseStateHandler()

value = mouse_handler

# creating text from the value
text = "Mouse State Handler : " + str(type(value))

# setting this text to the document
document.text = text

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/932deaa0b5f44f69d17861302ad75a66.png)