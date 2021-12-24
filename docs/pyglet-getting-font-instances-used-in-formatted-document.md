# PYGLET–获取格式化文档中使用的字体实例

> 原文:[https://www . geesforgeks . org/pyglet-get-font-instance-in-format-document/](https://www.geeksforgeeks.org/pyglet-getting-font-instances-used-in-formatted-document/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取格式化文档中使用的所有字体。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。格式化文档的布局通常是通过添加结构来增强其可读性，例如标题、缩进、字体变化和其他转换纯文本(未格式化)的设备，以便它们具有与已发布作品相似的外观。在金属排版技术中，字体是一种字体的特定大小、重量和样式。每种字体都是一组匹配的字体，每个字形一个，一种字体由一系列共享整体设计的字体组成。
我们可以借助下面给出的命令
创建一个窗口和格式化文档

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating document
document = pyglet.text.document.FormattedDocument(text)
```

> 为了创建窗口，我们对文档对象使用 get_font_runs 方法
> **语法:**document . get _ font _ runs()
> **参数:**它不需要参数
> **返回:**它返回 AbstractRunIterator

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
document.set_style(0, len(document.text), dict(
            font_name ='Arial', font_size = 16,
            color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(
                document, 400, 350, batch = batch)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color =(150, 255, 150))

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
    if symbol == pyglet.window.key.C:

        # closing the window
        # window.close()
        pass

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# getting all the font in the document
value = document.get_font_runs()

# printing value
print("Fonts : ", end = " ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/cb74f87b2fbed6e931c9eeea7455dd58.png)

```py
Fonts :  pyglet.text.document._FontStyleRunsRangeIterator object at 0x000001E95DC52308
```