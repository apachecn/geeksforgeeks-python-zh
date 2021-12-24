# PYGLET–在给定位置获取格式化文档的样式

> 原文:[https://www . geeksforgeeks . org/pyglet-获取给定位置的格式化文档样式/](https://www.geeksforgeeks.org/pyglet-getting-style-of-formatted-document-at-given-position/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获得格式化文档中给定位置的样式。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。格式化文档的布局通常是通过添加结构来增强其可读性，例如标题、缩进、字体变化和其他转换纯文本(未格式化)的设备，以便它们具有与已发布作品相似的外观。样式基本上是文本的外观，例如颜色、字体或大小。
我们可以借助下面给出的命令
创建一个窗口和格式化文档

```
# creating a window
window = pyglet.window.Window(width, height, title)

# creating document
document = pyglet.text.document.FormattedDocument(text)
```

> 为了创建窗口，我们对文档对象
> **使用 get_style(属性，pos)方法语法:** document.get_style(属性，pos)
> **参数:**它以字符串和整数作为参数
> **返回:**它根据属性
> 返回对象

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

# getting color at position 10
value = document.get_style("color", 10)

# printing value
print("Color at position 10 : ", end = " ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/6ef5cf5970b26a727a90d780685f1297.png)

```
Color at position 10 :  (255, 255, 255, 255)
```