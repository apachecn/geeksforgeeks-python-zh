# PYGLET–文本运动选择事件

> 原文:[https://www . geesforgeks . org/pyglet-on-text-motion-select-event/](https://www.geeksforgeeks.org/pyglet-on-text-motion-select-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发文本运动选择事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。用户在扩展选择的同时移动文本输入光标。通常，这是在 on_key_press()之后和 on_key_release()之前调用的，但是如果该键被按下(键重复)，也可能被调用多次。我们应该始终使用这种方法来响应文本选择事件，而不是原始的 on_key_press()，因为不同的平台有不同的默认键盘映射，并且正确处理了按键重复。

我们可以借助下面给出的命令创建一个窗口

```py
pyglet.window.Window(width, height, title)
```

下面是 on text motion 的语法，当触发此事件时会调用此方法

```py
@window.event       
def on_text_motion_select(motion):
    print("Motion Selected")
```

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
text = "GeeksforGeeks"

# creating a label with font = times roman
# font size = 36
# aligning it to the centre
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

        print("Key C is pressed")

# on text motion select event
@window.event
def on_text_motion_select(motion):

    # printing message
    print("Motion Selected")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/6444fbc14941b3d9a7eeb674a7d057c8.png)