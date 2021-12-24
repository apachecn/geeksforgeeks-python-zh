# pyglet–插入符

> 原文:[https://www.geeksforgeeks.org/pyglet-caret/](https://www.geeksforgeeks.org/pyglet-caret/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中的窗口上使用插入符号对象。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。插入符号基本上是 pyglet . text . layout . incrementaltextlayout 的可见文本插入标记。插入符号在文本布局对象的文档位置绘制为单个竖线。如果标记不是“无”，它将给出当前文本选择的静止结束。布局上的可见文本选择将随标记和位置一起更新。默认情况下，使用布局的图形批次，因此不需要显式绘制插入符号。即使提供了不同的图形批次，插入符号也将在布局中正确定位和剪裁。
我们可以借助下面给出的命令
创建一个窗口

```py
 pyglet.window.Window(width, height, title)
```

> 为了创建窗口，我们使用 pyglet.text.caret.caret 方法
> **语法:** pyglet.text.caret.Caret(布局，颜色=(255，255，255))
> **参数:**它需要 2 个参数，第一个是布局，第二个是颜色
> **返回:**它返回 Caret 对象

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
text = "Welcome to GeeksforGeeks"

# batch object
batch = pyglet.graphics.Batch()

# creating document
document = pyglet.text.document.FormattedDocument(text)

# setting style to the document
document.set_style(0, len(document.text), dict(font_name ='Arial', font_size = 16, color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(document, 400, 50, batch = batch)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color =(255, 255, 255))

# caret to window push handlers
window.push_handlers(caret)

# on draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the batch
    batch.draw()

    # window push handlers
    window.push_handlers(caret)

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

<video class="wp-video-shortcode" id="video-482534-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200908021429/Geeksforgeeks-2020-09-08-02-14-12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200908021429/Geeksforgeeks-2020-09-08-02-14-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200908021429/Geeksforgeeks-2020-09-08-02-14-12.mp4)</video>