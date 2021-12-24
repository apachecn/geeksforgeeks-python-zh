# PYGLET–获取窗口上下文

> 原文:[https://www . geeksforgeeks . org/pyglet-get-window-context/](https://www.geeksforgeeks.org/pyglet-getting-window-context/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取窗口上下文。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。窗口上下文是附加到此窗口的 OpenGL 上下文。这是一个只读文件。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`context`属性
> 
> **语法:**窗口.上下文
> 
> **论证:**不需要论证
> 
> **返回:**返回 Win32Context 对象

下面是实现

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

# getting window context
value = window.context

# printing the value
print("Window context : ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/4e13857289d30858a59726f37b39597c.png)

```
Window context : 
Win32Context()

```