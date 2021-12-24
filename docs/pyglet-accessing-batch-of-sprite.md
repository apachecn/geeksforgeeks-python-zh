# PYGLET–访问雪碧批次

> 原文:[https://www . geeksforgeeks . org/pyglet-access-batch-of-sprite/](https://www.geeksforgeeks.org/pyglet-accessing-batch-of-sprite/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中访问 sprite 的批处理对象。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。精灵是屏幕上显示的图像的实例。多个子画面可以在屏幕的不同位置显示相同的图像。子画面也可以放大或缩小，以任何角度旋转，并以部分不透明度绘制。图像是借助 pyglet 的图像模块加载的。子画面可以从一个批次迁移到另一个批次，或者从其批次中移除(对于单个图形)。请注意，这可能是一项昂贵的操作。

我们可以在下面给出的命令的帮助下创建一个窗口和精灵对象

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a sprite object
sprite = pyglet.sprite.Sprite(img, x, y)
```

> 为了创建窗口，我们将批处理属性用于 sprite 对象
> **语法:** sprite.batch
> **参数:**它不需要参数
> **返回:**它返回批处理对象

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

# setting image as icon
window.set_icon(img)

# getting batch of the first sprite
sprite = sprites[0]
value = sprite.batch

# setting this value to the label
label.text = str(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/626d265d912e8f0d4010086a0189969b.png)