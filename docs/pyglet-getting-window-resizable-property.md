# PYGLET–获取窗口大小可调整属性

> 原文:[https://www . geeksforgeeks . org/pyglet-get-window-resizable-property/](https://www.geeksforgeeks.org/pyglet-getting-window-resizable-property/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获得窗口大小可调的属性。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。如果窗口可以随时调整大小，则可调整大小属性为真，否则为假。
我们可以借助下面给出的命令
创建一个窗口

```
 pyglet.window.Window(width, height, title)
```

> 为了创建窗口，我们在窗口对象中使用了可调整大小的属性
> **语法:**窗口.可调整大小的
> **参数:**它不需要参数
> **返回:**它返回 bool

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
text = "GeeksforGeeks"

# creating a label with font = times roman
# font size = 36
# aligning it to the center
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 36,
                          x = window.width//2, y = window.height//2,
                          anchor_x ='center', anchor_y ='center')

new_label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 10,
                          x = 25, y = 25)

# on draw event
@window.event
def on_draw():   

    # clearing the window
    window.clear()

    # drawing the label on the window
    label.draw()

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

# getting window resizable property
value = window.resizable

# printing the value
print("Window resizable ? : ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/9e2be38c6797e1867619821bd01925e9.png)

```
Window resizable ? : 
False
```