# PYGLET–获取车窗高度

> 原文:[https://www.geeksforgeeks.org/pyglet-getting-window-height/](https://www.geeksforgeeks.org/pyglet-getting-window-height/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获得窗口高度。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。窗口高度可由用户随时更改，也可借助`set_size`方法编程更改。

我们可以在下面命令的帮助下创建一个窗口

```
 pyglet.window.Window(width, height, title)

```

> 为了创建窗口，我们对窗口对象使用`height`属性
> 
> **语法:**窗口.高度
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

# getting window height
value = window.height

# printing the value
print("Window Height : ")
print(value)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/c64062aae62db2e17961376ca459db0e.png)

```
Window Height : 
500

```