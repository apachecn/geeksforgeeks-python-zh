# PYGLET–添加字体作为资源

> 原文:[https://www . geeksforgeeks . org/pyglet-add-font-as-resource/](https://www.geeksforgeeks.org/pyglet-adding-font-as-resource/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中添加字体作为程序资源。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了加载一个文件即资源，我们使用 pyglet 的资源模块。该模块允许应用程序指定资源的搜索路径。相对路径被认为是相对于应用程序的 __main__ 模块的。系统中未安装的字体必须先添加到 pyglet 中，然后才能与 font.load 一起使用。虽然字体是使用此功能添加文件名的，但它是通过指定其系列名称来加载的。

我们可以借助下面给出的命令创建一个窗口对象

```py
# creating a window
window = pyglet.window.Window(width, height, title) 
```

> 为了创建窗口，我们对 pyglet.resource
> **使用 add_font 方法语法:**resource . add _ font(name)
> **参数:**它将字符串作为参数
> **返回:**它返回 None

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

# adding new_font adding as recource
pyglet.resource.add_font('new_font.ttf')

# setting font name of label
label.font_name = "new_font"

# setting text to the label
label.text = label.font_name

# start running the application
pyglet.app.run()
```

**输出:**

![](img/68cf58b9b1d1a3aa607b76c25d80b646.png)