# PYGLET–加载纯文本文档

> 原文:[https://www . geesforgeks . org/pyglet-loading-纯文本-document/](https://www.geeksforgeeks.org/pyglet-loading-plain-text-document/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中加载纯文本文件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了加载一个文件即资源，我们使用 pyglet 的资源模块。该模块允许应用程序指定资源的搜索路径。相对路径被认为是相对于应用程序的 __main__ 模块的。纯文本或明文是任何只包含文本的文本、文本文件或文档。与富文本文档不同，纯文本文件不能有粗体文本、字体、较大的字体大小或任何其他特殊的文本格式。图片是纯文本和格式化文本的视觉示例

我们可以在下面给出的命令的帮助下创建一个窗口对象

```py
# creating a window
window = pyglet.window.Window(width, height, title)
```

> 为此，我们对 pyglet.resource
> **使用 text 方法语法:**resource . text(file _ name)
> **参数:**它以字符串即文件名作为参数
> **返回:**它返回未格式化的文档对象

下面是实现

## 蟒蛇 3

```py
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
text = "Welcome to GeeksforGeeks"

# creating label with following properties
# font = cooper
# position = 250, 150
# anchor position = center
label = pyglet.text.Label(text,
                          font_name ='Cooper',
                          font_size = 16,
                          x = 250, 
                          y = 150,
                          anchor_x ='center', 
                          anchor_y ='center')

# creating a batch
batch = pyglet.graphics.Batch()

# loading geeksforgeeks image
image = pyglet.image.load('gfg.png')

# creating sprite object
# it is instance of an image displayed on-screen
sprite = pyglet.sprite.Sprite(image, x = 200, y = 230)

# on draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the label
    label.draw()

    # draw the image on screen
    sprite.draw()

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == key.C:

        # printing the message
        print("Key : C is pressed")

# image for icon
img = image = pyglet.resource.image("gfg.png")

# setting image as icon
window.set_icon(img)

# loading a plain text file
value = pyglet.resource.text("plain.txt")

# setting text  of label
label.text = str(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/8db56dafe5d350d17b83d442cb4bf0a8.png)