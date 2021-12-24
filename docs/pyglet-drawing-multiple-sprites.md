# PYGLET–绘制多个精灵

> 原文:[https://www . geeksforgeeks . org/pyglet-drawing-multi-sprites/](https://www.geeksforgeeks.org/pyglet-drawing-multiple-sprites/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中在窗口上绘制多个 spries。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。精灵是屏幕上显示的图像的实例。多个子画面可以在屏幕的不同位置显示相同的图像。子画面也可以放大或缩小，以任何角度旋转，并以部分不透明度绘制。图像是借助 pyglet 的图像模块加载的。
精灵可以一起批量绘制，比单独调用它们的每种绘制方法更快。以下示例创建一百个小精灵，并将它们添加到一个批处理中。然后在一次调用中绘制整批精灵

借助下面给出的命令，我们可以创建一个窗口、批处理和精灵

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a batch 
batch = pyglet.graphics.Batch()

# creating a sprite object
pyglet.sprite.Sprite(img, x, y)
```

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

# creating a list of sprites object
sprites = []

# position of images
pos_x = 10
pos_y = 230

for i in range(5):

    # temporary sprite object
    temp = pyglet.sprite.Sprite(image, pos_x, pos_y, batch = batch)

    # append the sprite object to the list
    sprites.append(temp)

    # increment the x co-ordinate
    pos_x = pos_x + 100

# on draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the label
    label.draw()

    # draw the batch
    batch.draw()

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == key.C:

        # printing the message
        print("Key : C is pressed")

# image for icon
img = image = pyglet.resource.image("gfg.png")

# getting mouse button string
value = pyglet.window.mouse.buttons_string(2 | 5)

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/4bbfd05a127424a4c93b1b8a35856d79.png)