# PYGLET–获取给定范围内格式化文档的样式

> 原文:[https://www . geeksforgeeks . org/pyglet-获取给定范围的格式化文档样式/](https://www.geeksforgeeks.org/pyglet-getting-style-of-formatted-document-for-given-range/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获得格式化文档中给定范围的样式。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。格式化文档的布局通常是通过添加结构来增强其可读性，例如标题、缩进、字体变化和其他转换纯文本(未格式化)的设备，以便它们具有类似于已发布作品的外观。样式基本上是文本的外观，例如颜色、字体或大小。
我们可以借助下面给出的命令
创建一个窗口和格式化文档

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating document
document = pyglet.text.document.FormattedDocument(text)
```

> 为了创建窗口，我们对文档对象使用 get_style_range 方法
> **语法:** document.get_style_range(属性，开始，结束)
> **参数:**它以字符串和两个整数作为参数
> **返回:**它返回给定范围内的属性的样式集，如果设置了多个值
> ，则返回 STYLE _ understand

下面是实现

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
text = "Welcome to GeeksforGeeks Have a nice day"

# batch object
batch = pyglet.graphics.Batch()

# creating a formatted document
document = pyglet.text.document.FormattedDocument(text)

# setting style to the document
document.set_style(0, len(document.text), dict(font_name ='Arial', font_size = 16, color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(document, 400, 350, batch = batch)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color =(150, 255, 150))

# caret to winow push handlers
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

    # caret to winow push handlers
    window.push_handlers(caret)

# key press event   
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == pyglet.window.key.C:

        # closing the window
        # window.close()
        pass

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# getting color for given range
value = document.get_style_range("color", 10, 20)

# printing value
print("Color for given range : ", end = " ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/13d27e1cc8ad352a0e36fd695a4491f6.png)

**给定范围的颜色:(255，255，255，255)**