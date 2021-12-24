# PYGLET–插入符号可见性属性

> 原文:[https://www . geeksforgeeks . org/pyglet-caret-visibility-property/](https://www.geeksforgeeks.org/pyglet-caret-visibility-property/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中访问插入符号的可见属性。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。插入符号基本上是 pyglet . text . layout . incrementaltextlayout 的可见文本插入标记。插入符号在文本布局对象的文档位置绘制为单个竖线。如果标记不是“无”，它将给出当前文本选择的静止结束。尽管有此属性，但插入符号可能会被隐藏，因为它会定期闪烁，或者如果事件处理程序附加到窗口，它会被 on_deactivate 隐藏。
我们可以借助下面给出的命令创建一个窗口和插入符号

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a caret
caret = pyglet.text.caret.Caret(layout, color=(255, 255, 255))
```

> 为了创建窗口，我们使用带有插入符号对象的可见属性
> **语法:**插入符号可见
> **参数:**它不需要参数
> **返回:**它返回 bool

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

# getting caret visible property
value = caret.visible

# printing the value
print("Caret Visible  : ", end ="")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/3036a152ec2981510b3eae8d4c0e18f2.png)

**输出:**

```py
Caret Visible  : True
```