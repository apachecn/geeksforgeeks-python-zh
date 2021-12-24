# PYGLET–上下文状态丢失事件

> 原文:[https://www . geesforgeks . org/pyglet-on-context-state-lost-event/](https://www.geeksforgeeks.org/pyglet-on-context-state-lost-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发上下文状态丢失事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。当窗口的总帐上下文状态丢失时，会触发此事件。如果窗口被移动到另一个视频设备，或者在全屏或窗口模式之间，pyglet 有时可能需要重新创建窗口的 GL 上下文。在这种情况下，它将尝试在新旧上下文之间共享对象(显示列表、纹理对象、着色器)。如果这是可能的，那么只有 GL 上下文的当前状态会丢失，应用程序应该简单地恢复状态。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

下面是上下文状态窗口丢失事件的语法，这个方法在这个事件被触发时被调用

```py
@window.event       
def on_context_state_lost():
    print("Context State Lost")

```

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

@window.event   
# window on context state lost event       
def on_context_state_lost():

    # printing message
    print("Context State Lost")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/cce010aaf666206464d0dadca8243a93.png)