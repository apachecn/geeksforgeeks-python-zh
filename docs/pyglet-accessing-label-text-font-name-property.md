# PYGLET–访问标签文本字体名称属性

> 原文:[https://www . geesforgeks . org/pyglet-access-label-text-font-name-property/](https://www.geeksforgeeks.org/pyglet-accessing-label-text-font-name-property/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中访问标签文本字体属性。Pyglet 易于使用，但它是一个强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了显示文本或消息，我们使用一个 HTML 标签对象。标签是在窗体上显示文本的图形控件元素。它通常是静态控件；没有交互性。在金属排版技术中，字体是一种特殊的字体大小、重量和样式。每种字体都是一组匹配的字体，每种字形都是一个整体(称为“排序”)，字体由一系列共享整体设计的字体组成。

我们可以在下面给出的命令的帮助下创建一个窗口和标签

```py
# creating window
window = pyglet.window.Window(width, height, title)

# creating a label
label = pyglet.text.Label(text, font_name, font_size, x, y)
```

> 为了创建窗口，我们使用带有标签对象的 font_name 属性
> **语法:**标签. font_name
> **参数:**它不需要参数
> **返回:**它返回字符串或列表

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

# creating a label with font = times roman
# font size = 36
# aligning it to the centre
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 28,
                          x = 20, y = window.height//2, )

# accessing color property of the label
# setting new color
label.color = (100, 255, 100, 255)

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

# getting font name of the label
value = label.font_name

# printing value
print("Font Name : " + str(value))

# start running the application
pyglet.app.run()
```

**输出:**

![](img/afff048438e971ea0afe938ee052c376.png)

```py
Font Name : Times New Roman
```