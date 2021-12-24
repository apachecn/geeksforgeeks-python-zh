# PYGLET–获取窗口标题

> 原文:[https://www . geeksforgeeks . org/pyglet-get-window-caption/](https://www.geeksforgeeks.org/pyglet-getting-window-caption/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取窗口标题。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。窗口标题基本上是窗口的标题，我们可以在创建窗口时设置标题虽然我们可以随时更改标题，但这个标题会出现在窗口的任务栏中。我们使用`set_caption`方法设置字幕。

我们可以在下面命令的帮助下创建一个窗口

```py
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`caption`属性
> 
> **语法:**窗口。标题
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

下面是实现

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

        # closing the window
        window.close()

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# getting window caption
value = window.caption

# printing the value
print("Caption : ", end ="")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/c6c6d907a2af3134d2a5bf7f38ad7eea.png)

```py
Caption : Geeksforgeeks

```