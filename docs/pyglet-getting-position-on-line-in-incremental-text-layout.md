# PYGLET–在增量文本布局中获得在线位置

> 原文:[https://www . geeksforgeeks . org/pyglet-get-position-online-in-increment-text-layout/](https://www.geeksforgeeks.org/pyglet-getting-position-on-line-in-incremental-text-layout/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取增量文本布局对象的在线位置。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。增量文本布局显示适合交互式编辑和/或滚动大文档的文本。与文本布局和滚动文本布局不同，这个类只为可见的文本行生成顶点列表。随着文档的滚动，视情况删除和创建顶点列表，以将视频内存使用降至最低并提高渲染速度。位置是给定行索引和 X 坐标的最近文档位置。

借助下面给出的命令，我们可以创建一个窗口和增量文本布局

```
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a in
layout = pyglet.text.layout.IncrementalTextLayout(document, width, height)

```

> 为了创建窗口，我们使用`get_position_on_line`方法
> 
> **语法:**布局. get_position_on_line(行，x)
> 
> **自变量:**取两个整数作为自变量
> 
> **返回:**返回整数

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
text = "GeeksforGeeks Learn and Grow, Portal for Geeks"

# batch object
batch = pyglet.graphics.Batch()

# creating a formatted document
# unlike unformatted document it is formatted
document = pyglet.text.document.FormattedDocument(text)

# setting style to the document
document.set_style(0, len(document.text), dict(font_name ='Arial', font_size = 16, color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(document, 400, 350, multiline = True, batch = batch)

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
img = pyglet.resource.image("gfg.png")

# setting image as icon
window.set_icon(img)

# getting position on line
# line 0 and x = 100
value = layout.get_position_on_line(0, 100)

# printing value
print("Position on Line : ", end ="")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/be848e30a7a03cae4b6791207f4b941f.png)

```
Position on Line : 9

```