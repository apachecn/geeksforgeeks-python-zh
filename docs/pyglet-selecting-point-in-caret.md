# PYGLET–在插入符号中选择点

> 原文:[https://www . geeksforgeeks . org/pyglet-选择插入符号点/](https://www.geeksforgeeks.org/pyglet-selecting-point-in-caret/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中选择插入符号中的点。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。插入符号基本上是 pyglet . text . layout . incrementaltextlayout 的可见文本插入标记。插入符号在文本布局对象的文档位置绘制为单个竖线。如果标记不是“无”，它将给出当前文本选择的静止结束。对于给定点插入符号，尝试选择离给定点最近的点
我们可以借助下面给出的命令
创建一个窗口和插入符号

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color=(255, 255, 255))
```

> 为了创建窗口，我们使用 select_to_point(x，y)方法和插入符号对象
> **语法:**插入符号. select_to_point(x，y)
> **参数:**它以两个整数作为参数
> **返回:**它返回 None

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

# creating document
document = pyglet.text.document.FormattedDocument(text)

# setting style to the document
document.set_style(0, len(document.text), dict(
            font_name ='Arial', font_size = 16,
            color =(255, 255, 255, 255)))

# creating a incremental text layout
layout = pyglet.text.layout.IncrementalTextLayout(
                  document, 400, 350, batch = batch)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color =(255, 255, 255))

# caret to window push handlers
window.push_handlers(caret)

# moving caret to point
# editable mark
value = caret.move_to_point(100, 30)

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

# selecting point which is nearest to 100, 100
caret.select_to_point(100, 100)

# start running the application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-483151-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200909000258/Geeksforgeeks-2020-09-09-00-02-34.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200909000258/Geeksforgeeks-2020-09-09-00-02-34.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200909000258/Geeksforgeeks-2020-09-09-00-02-34.mp4)</video>