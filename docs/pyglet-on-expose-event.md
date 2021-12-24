# PYGLET–曝光事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-expose-event/](https://www.geeksforgeeks.org/pyglet-on-expose-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发 expose 事件。Pyglet 易于使用，但它是一个强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。该事件在窗口第一次出现时触发，并且任何时候窗口的内容由于另一个窗口遮挡而无效。没有办法确定窗口的哪个部分需要重画。请注意，这种方法的使用越来越不常见，因为较新的窗口管理器会自动合成窗口，并保留窗口内容的后备存储。
我们可以借助下面给出的命令
创建一个窗口

```
pyglet.window.Window(width, height, title)
```

下面是 on expose 事件的语法，这个方法在这个事件被触发时被调用

```
@window.event       
def on_expose():
    print("On Expose Event")
```

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
# aligning it to the centre
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 36,
                          x = window.width//2, y = window.height//2,
                          anchor_x ='center', anchor_y ='center')

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

    print("nn")
    # key "C" get press
    if symbol == pyglet.window.key.C:

        # close the window
        window.close()

# on expose event
@window.event
def on_expose():

    # printing some message
    print("On Expose event")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/df6f8a0ef6ac84b03e67af26262d1699.png)